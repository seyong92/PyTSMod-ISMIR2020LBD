---
layout: home
title: "PyTSMod: A Python Implementation of Time-Scale Modification Algorithms"
---
<style>
.main-content table {
    display: inline-table;
}
table {
    table-layout:fixed;
    width: 100%;
    overflow: hidden;
}
#player{
    width: 100%;
}
</style>

## Overview

Time-scale modification (TSM) is a digital audio effect that adjusts the length of an audio signal while preserving its pitch. The TSM audio effect is widely used in not only sound production but also music and audio research such as for data augmentation. In this paper, we present PyTSMod, an open-source Python library that implements several different classical TSM algorithms. We expect that PyTSMod can help MIR and audio researchers easily use the TSM algorithms in the Python-based environment.

## Available TSM algorithms

* Overlap-Add (OLA)
    * OLA is the most simple TSM algorithm that changes the length of the signal through modifying the hop size between analysis frame and synthesis frame.
* Pitch Synchronous Overlap-Add (TD-PSOLA)
    * TD-PSOLA is the algorithm that analyzes the orignal waveforms to create pitich-synchronous analysis windows and synthesize the output signal both for modifying time-scale and pitch-scale.
* Waveform Similarity Overlap-Add (WSOLA)
    * WSOLA maximizes the waveform similarity by allowing timing tolerance to analysis frame to find the most similar position through cross correlation.
* Phase Vocoder (PV)
* TSM based on harmonic-percussive source separation (HPTSM)

## Installation

PyTSMod is hosted on PyPI. To install, run the following command in your Python environment:
```bash
$ pip install pytsmod
```

## Examples

### Singing Voice

#### Original

<audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-original.flac"></audio>

#### TSM Results

| Algorithm | α=0.5 | α=1.2 | α=1.5 |
| OLA | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-ola-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-ola-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-ola-150.flac"></audio> |
| TD-PSOLA [^1] | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-tdpsola-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-tdpsola-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-tdpsola-150.flac"></audio> |
| WSOLA | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-wsola-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-wsola-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-wsola-150.flac"></audio> |
| PV | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-pv-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-pv-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-pv-150.flac"></audio> |
| PV (with phase lock) | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-pvlock-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-pvlock-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-pvlock-150.flac"></audio> |
| HPTSM | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-hp-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-hp-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/singing-hp-150.flac"></audio> |

### Music Clip

#### Original

<audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-original.flac"></audio>

#### TSM Results

| Algorithm | α=0.5 | α=1.2 | α=1.5 |
| OLA | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-ola-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-ola-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-ola-150.flac"></audio> |
| WSOLA | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-wsola-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-wsola-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-wsola-150.flac"></audio> |
| PV | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-pv-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-pv-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-pv-150.flac"></audio> |
| PV (with phase lock) | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-pvlock-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-pvlock-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-pvlock-150.flac"></audio> |
| HPTSM | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-hp-050.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-hp-120.flac"></audio> | <audio controls id="player" onplay="pauseOthers(this);"><source src="assets/audio/sunny-hp-150.flac"></audio> |

For more audio examples, please visit the [GitHub repo](https://github.com/KAIST-MACLab/PyTSMod) of PyTSMod.

[^1]: [CREPE](https://github.com/marl/crepe) is used for extracting pitch of the audio source.

## References

[1] Jonathan Driedger, Meinard Müller. "TSM Toolbox: MATLAB Implementations of Time-Scale Modification Algorithms", *Proceedings of the 17th International Conference on Digital Audio Effects (DAFx-14).* 2014.

[2] Jonathan Driedger, Meinard Müller. "A review of time-scale modification of music signals", *Applied Sciences, 6(2), 57.* 2016.

[3] Udo Zölzer. "DAFX: digital audio effects", *John Wiley & Sons.* 2011.