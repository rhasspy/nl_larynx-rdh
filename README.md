# Dutch Text to Speech Voice (rdh)

Voice and vocoder models for [larynx](https://github.com/rhasspy/larynx) based on the free [rdh dataset](https://github.com/r-dh/dutch-vl-tts).

Used in [Rhasspy](https://github.com/rhasspy) in the [rhasspy-tts-larynx-hermes](https://github.com/rhasspy/rhasspy-tts-larynx-hermes) service.

[Samples](samples)

## Usage

```sh
$ larynx \
    --model /path/to/tts-checkpoint.pth.tar \
    --vocoder-model /path/to/vocoder-checkpoint.pth.tar \
    --output-file /path/to/output.wav \
    'Hoe laat is het?'
```

## Model Details

* Type: [Glow-TTS](https://arxiv.org/abs/2005.11129)
* Sample rate: 22050 Hz
* Frequency range: 0-8000 Hz

See [configuration](config.json) for details.

## Vocoder Details

* Type: [Multi-band MelGAN](https://arxiv.org/abs/2005.05106)
* Sample rate: 22050 Hz
* Frequency range: 0-8000 Hz

See [configuration](vocoder/config.json) for details.

## Files

Some files are split into multiple parts so that they can be uploaded to GitHub. This is done with the `split` command:

```bash
split -d -b 25M FILE FILE.part-
```

They can be recombined simply with:

```bash
cat FILE.part-* > FILE
```
