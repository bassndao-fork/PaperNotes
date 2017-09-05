## [WaveNet: A Generative Model for Raw Audio](https://arxiv.org/abs/1609.03499)
Aaron van den Oord et al., Submitted on 12 Sep 2016

TLDR; Deep neural network for generating raw audio waveforms.

### Key Points
* Model: fully probabilistic and autoregressive, with the predictive distribution for each audio sample conditioned on all previous ones
* Dilated Causal Convolution: large receptive fields
* Applications: text-to-speech (TTS), music generation
  * Can be conditioned on speaker's identity:style associated with each speaker
  * Generates novel and often highly realistic musical fragments
* Natural sounding in English and Mandarin
* 8-bit quantization, 16k


### Notes / Questions
* Prediction/inferencing
  * DeepMind reported that 1 second of audio generation takes about 90 minutes to generate: prohibitive for real-time applications
  * Later Wavenet authors said the "90 minutes per second" claim is [false](https://www.reddit.com/r/MachineLearning/comments/53ilcr/fast_wavenet_an_efficient_wavenet_generation/). With a receptive field of 16k, an efficient implementation takes ~2 minutes per second (GPU, older 6GB Titan). So 45 times faster than reported.
  * There have been reports of 1 minute being generated in [2](https://www.reddit.com/r/MachineLearning/comments/53ilcr/fast_wavenet_an_efficient_wavenet_generation/) or [6](https://www.reddit.com/r/MachineLearning/comments/51sr9t/deepmind_wavenet_a_generative_model_for_raw_audio/d7f6ejp/) hours
* Learning/training
  * Training wise, some people [reported](https://github.com/ibab/tensorflow-wavenet/issues/193) okay results after a week of training (500K steps) on TitanXP
  * NSynth (WaveNet-based autoencoder for synthesizing audio): about 10 days to train on 32 K40 GPUs (worth 72k or 5k USD on Google Cloud)
