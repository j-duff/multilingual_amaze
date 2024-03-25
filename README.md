This is a modified version of the A-Maze script by [Yizhi Tang](https://github.com/tangyizhi2000), [Lucy Yu-Chuan Chiang](https://sites.google.com/a/umich.edu/yu-chuan-chiang/home), [Wei-Jie Zhou](https://github.com/tooweisiannn), [Sohee Chung](https://github.com/soheechung), and [Lisa Levinson](https://lisalevinson.github.io/) at the UMich WordLab. Like [their original](https://github.com/UMWordLab/multilingual_amaze), it uses the `minicons` package to query a HuggingFace-hosted transformer model of your choice in order to generate A-Maze foils. 

Also like the original, it runs smoothly on Google Colab! Just click the Colab icon at the top of the script to run it for yourself, no local software necessary.

Changes from the original:
- Added support for automatically collecting frequency data (for supported languages) through `wordfreq`. See if your language is supported [here](https://pypi.org/project/wordfreq/). Manual CSV upload is still supported if you have it.
- Added script-based filters for naively excluding some words in wordfreq frequency dictionaries.
- Adjusted candidate inclusion filters: until a user-set minimum candidate set size is achieved (or a user-set maximum search space is exceeded), the script will loop through frequency-bin-matching and length-matching words, backing off progressively to laxer inclusion rules if the minimum isn't met.
- Added more details in the output file, including a set of backup foils of user-specified size for each position.
- Added preservation of leading and trailing punctuation akin to Boyce et al. (2020).

Thanks to Mandy Cartner for helping tune this for usable output in Hebrew, and identifying a bunch of useful features. On a few pilot runs, this currently seems to produce OK results for simple Hebrew stimuli. 

Features I hope to implement in the future:
- Including target and foil surprisal and frequency in the output script.
- Generating suitable foils across multiple conditions. (Right now, every sentence in the input may receive a different foil string.)
