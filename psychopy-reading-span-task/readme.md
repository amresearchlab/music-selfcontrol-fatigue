# Reading Span Task

This modified Reading Span Task was created in PsychoPy. In the study, it measured participants' baseline verbal working memory capacity by combining sentence judgments with serial letter recall.

## Task Design

The task has three practice phases followed by the main test:

1. Letter practice presents sets of letters for later recall.
2. Sentence practice presents sentences for sensibility judgments and estimates participants' average reading duration.
3. Joint practice combines sentence judgments with letter recall.
4. The main test presents sentence-letter sets and records span and sentence-task performance.

## Procedure

Participants judge whether each sentence makes sense and recall the letters presented between sentences in their original order. In the main test, set sizes vary and participants complete multiple repetitions of the set-size sequence.

## Configuration

Settings for joint practice and the main test are in the `code_20` component's **Begin Routine** code in the `pre_big_loop_init` routine:

- Joint practice uses `practice_sentences/sentences.csv`, set sizes `[2, 2, 2]`, and `BIG_LOOP_REPS = 100000` (effectively an open-ended practice loop).
- The main test uses `main_test/sentences.csv`, set sizes `[4, 5, 6]`, and `BIG_LOOP_REPS = 2`.
- Edit `POSSIBLE_SET_SIZES` to change the set-size sequence. The number of sizes determines the number of sets in each big loop.
- `avg_read_duration` is calculated during sentence practice. If sentence practice is skipped, a duration in seconds can be hardcoded in `code_20`; without a value, sentence prompts will not auto-skip.
- To skip letter practice, set the `practice_until_perfect` loop's `nReps` to `0`. Restore it with a large value such as `100000`.
- To skip sentence practice, set the `sentence_practice_until_perfect` loop's `nReps` to `0`. Restore it with a large value such as `100000`.
- Edit `practice_letters/block.csv` to change letter-practice sets. Each row defines a set, and `no_of_letters` gives the number of letters in it.

## Files

- `reading_span.psyexp`: PsychoPy Builder experiment.
- `reading_span.py` and `reading_span_lastrun.py`: Python experiment scripts.
- `reading_span.js`, `reading_span-legacy-browsers.js`, and `index.html`: generated browser build and entry point.
- `practice_letters/`: letter-practice conditions and letter stimuli.
- `practice_sentences/sentences.csv`: sentence-practice items.
- `main_test/sentences.csv`: main-test sentence items.
- `data/`: participant CSV data.

## Data Output

The experiment writes CSV data. Selected derived fields include:

- `avg_read_duration`: average sentence-reading duration measured during sentence practice.
- `rspan_score`: absolute span score, recorded during the main test.
- `rspan_pcu`: partial-credit-unit score, recorded at the end of the main test.
- `total_correct_letters`: cumulative correctly recalled letters.
- `sent_speed_error`, `sent_acc_error`, and `sent_total_error`: sentence-response speed, accuracy, and total errors.
- `total_number_of_sentences` and `sent_percent_correct`: sentence-task totals and accuracy.

Several measures are recorded after each main-test loop, so they may occur on multiple rows in a participant's CSV file. `rspan_pcu` is recorded on the final main-test loop.

## Running the Browser Version

Save changes in PsychoPy and use **Compile to JS Script** before testing the browser build. Serve the folder through a web server rather than opening `index.html` directly. The generated JavaScript imports `./lib/psychojs-2022.2.5.js`, and the HTML references other PsychoJS files in `lib/`; this folder does not include that runtime directory. Add the matching runtime files from a complete PsychoPy export before running the browser build.

## References

The experiment is based on Experiment 2 in:

- Oswald, F. L., McAbee, S. T., Redick, T. S., & Hambrick, D. Z. (2015). The development of a short domain-general measure of working memory capacity. *Behavior Research Methods, 47*, 1343–1355. https://doi.org/10.3758/s13428-014-0543-2

For guidance on test administration, scoring, validity, and reliability, see:

- Conway, A. R. A., Kane, M. J., Bunting, M. F., Hambrick, D. Z., Wilhelm, O., & Engle, R. W. (2005). Working memory span tasks: A methodological review and user's guide. *Psychonomic Bulletin & Review, 12*, 769–786. https://doi.org/10.3758/BF03196772
