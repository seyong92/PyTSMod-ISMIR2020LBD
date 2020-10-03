---
layout: home
title: "PyTSMod: A Python Implementation of Time-Scale Modification Algorithms"
---

## Overview

Time-scale modification (TSM) is a digital audio effect that adjusts the length of an audio signal while preserving its pitch. The TSM audio effect is widely used in not only sound production but also music and audio research such as for data augmentation. In this paper, we present PyTSMod, an open-source Python library that implements several different classical TSM algorithms. We expect that PyTSMod can help MIR and audio researchers easily use the TSM algorithms in the Python-based environment.

## Available TSM algorithms

* Overlap-Add (OLA)
* Pitch Synchronous Overlap-Add (TD-PSOLA)
* Waveform Similarity Overlap-Add (WSOLA)
* Phase Vocoder (PV)
* TSM based on harmonic-percussive source separation (HPTSM)

## Installation

PyTSMod is hosted on PyPI. To install, run the following command in your Python environment:
```bash
$ pip install pytsmod
```

## Examples

| Algorithm | Original | α=0.5 | α=1.2
| OLA |
| TD-PSOLA [^1] |
| WSOLA |
| PV |
| PV (with phase lock) |
| HPTSM |

[^1]: [CREPE](https://github.com/marl/crepe) is used for pitch tracking of the audio source.

## References

[1] Jonathan Driedger, Meinard Müller. "TSM Toolbox: MATLAB Implementations of Time-Scale Modification Algorithms", *Proceedings of the 17th International Conference on Digital Audio Effects (DAFx-14).* 2014.

[2] Jonathan Driedger, Meinard Müller. "A review of time-scale modification of music signals", *Applied Sciences, 6(2), 57.* 2016.

[3] Udo Zölzer. "DAFX: digital audio effects", *John Wiley & Sons.* 2011.