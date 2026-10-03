# Incongruent Colour-Word Stroop Task

This PsyToolkit implementation was used as a post-reading outcome measure of self-control fatigue in the accompanying study. Participants identify the ink colour of colour words while ignoring the word meaning.

## Task Procedure

The task presents four ink colours with keyboard responses: `r` for red, `g` for green, `b` for blue, and `y` for yellow. It includes congruent and incongruent colour-word trials, a fixation point, and correctness feedback. The experiment contains instruction screens, a training block, and a real-test block.

The Stroop effect is calculated as reaction time on incongruent trials minus reaction time on congruent trials. A larger difference indicates greater response interference. In the study, the task was administered after the 30-minute reading session so it would serve as an outcome measure rather than an inducer of fatigue.

## Files

- `experiment_codes.txt`: PsyToolkit experiment definition, including trial conditions, response mappings, blocks, and saved response data.
- `newinstruction1.jpg`, `newinstruction2.jpg`, `newinstruction3.jpg`, and `newinstructiongetready.jpg`: instruction and transition screens.
- `fixpoint.webp`, `correct.webp`, and `mistake.webp`: fixation and feedback images.
- The remaining colour-word `.webp` files are the word/ink-colour stimuli used in the trial table.
- `stimuli.svg`: vector artwork used for stimuli or task graphics.

## Provenance and Reuse

This task is adapted from the PsyToolkit Stroop example. The adaptation adds instruction screens and changes task settings. The source example and downloadable experiment are available at:

- [PsyToolkit Stroop task description and demo](https://www.psytoolkit.org/experiment-library/stroop.html)
- [PsyToolkit Stroop experiment source](https://www.psytoolkit.org/doc_exp/stroop.html)
- [Downloadable PsyToolkit experiment](https://www.psytoolkit.org/doc_exp/stroop.zip)

PsyToolkit's [copyright terms](https://www.psytoolkit.org/copyright.html) state that PsyToolkit code and lessons may be used for non-commercial research and educational purposes when Professor Gijsbert Stoet and PsyToolkit are acknowledged. The terms require formal permission for commercial use. Check the terms for any separately authored material included in the source package, especially graphics, before redistributing those files or using them commercially.

## References

The Stroop paradigm and PsyToolkit platform are described in:

- Stroop, J. R. (1935). Studies of interference in serial verbal reactions. *Journal of Experimental Psychology, 18*, 643–662.
- MacLeod, C. M. (1991). Half a century of research on the Stroop effect: An integrative review. *Psychological Bulletin, 109*, 163–203.
- Stoet, G. (2010). PsyToolkit: A software package for programming psychological experiments using Linux. *Behavior Research Methods, 42*, 1096–1104.
- Stoet, G. (2017). PsyToolkit: A novel web-based method for running online questionnaires and reaction-time experiments. *Teaching of Psychology, 44*(1), 24–31.