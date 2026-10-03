# Category Switch Task

An online category-switching experiment created in PsychoPy. In the study, it measured divided attention. Created by Kelly Cotton on 30 March 2022; modified by Yiting Cheah and Seck-Wei Lim.

## Task Design

Participants classify words using one of two category judgments, indicated by a cue:

| Cue | Judgment | Right arrow | Left arrow |
| --- | --- | --- | --- |
| Heart | Living / nonliving | Living | Nonliving |
| Cross | Big / small | Big | Small |

The cue appears for 350 ms before the target word. Trials are separated by a 350 ms response-to-cue interval.

Trials vary by category congruency and task transition:

| Dimension | Conditions |
| --- | --- |
| Congruency | Congruent: living/big; incongruent: nonliving/small |
| Transition | Switch: category differs from the previous trial; nonswitch: same category |

These factors produce four trial types: congruent-switch, congruent-nonswitch, incongruent-switch, and incongruent-nonswitch. Trial sequences are specified in `trialtypes.xlsx`.

## Procedure

1. Participants receive instructions and practice each category judgment separately, then practice switching between the two. Practice provides feedback; an incorrect response must be corrected before the next cue.
2. Separate living/nonliving and big/small practice blocks provide feedback on error count and mean reaction time, rounded to one decimal place. Combined practice does not provide this block feedback.
3. Participants complete the main task, receiving reminders of the key mappings before each block.

The current main task contains 132 trials: four blocks of 33 trials. The first trial is handled separately because it must be a nonswitch trial.

## Configuration

- Practice trials are supplied by `stimuli_prac_1.xlsx` (living/nonliving), `stimuli_prac_2.xlsx` (big/small), and `stimuli_prac_3.xlsx` (combined practice). Edit these spreadsheets to change practice content or trial counts. The corresponding PsychoPy loops are named `prac_trials_1`, `prac_trials_2`, and `prac_trials_3`.
- Change `block_total` in the setup code to adjust the number of main-task blocks; the current value is four.
- Edit `trialtypes.xlsx` to change the main-task trial sequence. The current task has 33 trials per block: one initial nonswitch trial followed by the remaining sequence.
- Edit `code_prac_1` to change the instruction text.

## Files

- `category_switch.psyexp`: PsychoPy Builder experiment.
- `category_switch.py` and `category_switch_lastrun.py`: Python experiment scripts.
- `category_switch.js`, `category_switch-legacy-browsers.js`, and `index.html`: browser build and entry point.
- `trialtypes.xlsx`: main-task trial sequence.
- `stimuli_prac_1.xlsx`, `stimuli_prac_2.xlsx`, and `stimuli_prac_3.xlsx`: practice trial materials.
- `whiteheart.png` and `arrowcross.png`: task cues.
- `arrows.png`: arrow-key reminder image.
- `stimuli.csv`: stimulus list.

## Data Output

PsychoPy records trial responses and response times. The task also calculates switch and nonswitch accuracy and reaction-time summaries, including `acc_switch_cost` and `rt_switch_cost`. Response times are recorded in milliseconds for the task's `resp_milli` measure; `mt_qualtrial` marks trials with a response time of at least 100 ms.

## Running the Browser Version

Serve the folder through a web server rather than opening `index.html` directly. The generated JavaScript imports `./lib/psychojs-2022.2.5.js`, and the HTML references other PsychoJS files in `lib/`; this folder does not include that runtime directory. Add the matching runtime files from a complete PsychoPy export before running the browser build.

## References

The task is based on the Category Switch Task described in:

- Friedman, N. P., Miyake, A., Altamirano, L. J., Corley, R. P., Young, S. E., Rhea, S. A., & Hewitt, J. K. (2016). Stability and change in executive function abilities from late adolescence to early adulthood: A longitudinal twin study. *Developmental Psychology, 52*(2), 326–340. https://doi.org/10.1037/dev0000075
- Friedman, N. P., Miyake, A., Young, S. E., DeFries, J. C., Corley, R. P., & Hewitt, J. K. (2008). Individual differences in executive functions are almost entirely genetic in origin. *Journal of Experimental Psychology: General, 137*(2), 201–225. https://doi.org/10.1037/0096-3445.137.2.201

These studies adapted the task from:

- Mayr, U., & Kliegl, R. (2000). Task-set switching and long-term memory retrieval. *Journal of Experimental Psychology: Learning, Memory, and Cognition, 26*(5), 1124–1140. https://doi.org/10.1037/0278-7393.26.5.1124


