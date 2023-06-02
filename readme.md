# guitar-tone-matcher

Make your guitar tone sound like a given record.

## Jupyter notebook

To launch Jupyter, run this at the command line:

```bash
jupyter-notebook
```

## Pipeline

1. Inputs: two audio files, one of own guitar (clean), other is target recording.
1. Find the time window in the recording that is most closely matched by the clean signal.
1. (Optional?) apply [dynamic time warping](https://www.audiolabs-erlangen.de/resources/MIR/FMP/C3/C3S2_DTWbasic.html) to the clean signal to correct for rhthym inaccuracies in playing.
1. Define parameter space for modifying tone of clean signal to output wet signal. (WaveNet? PedalNet?)
1. Define loss function as distance between wet signal and target. 
1. Optimise (Adam optimiser?)

## Useful links

* [WaveNet](https://www.deepmind.com/blog/wavenet-a-generative-model-for-raw-audio)
* PedalNet:
    * [repo](https://github.com/teddykoker/pedalnet)
    * [paper](https://www.mdpi.com/2076-3417/10/3/766/htm)
    * [blog post](https://teddykoker.com/2020/05/deep-learning-for-guitar-effect-emulation/)
* [Guitar dataset](https://www.idmt.fraunhofer.de/en/publications/datasets/guitar.html)
* [Librosa](https://librosa.org/): audio and music processing in Python

## TODO

* Start with simple song, clean tone, just find matching section.
* Quantify distance between matching section and matching section.
* Apply effect e.g. pronounced distortion, then measure distance and verify it is larger.
* Dynamic time warping: align input, plot and play audio to confirm closer match to target.
* Read WaveNet and PedalNet papers closely.
* Define tone parameter space (as network architecture?).
