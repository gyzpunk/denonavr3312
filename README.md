# denonavr3312
Automate Denon AVR 3312 through telnet control protocol

[![Build Status](https://travis-ci.org/gyzpunk/denonavr3312.svg?branch=master)](https://travis-ci.org/gyzpunk/denonavr3312)
[![Coverage Status](https://coveralls.io/repos/github/gyzpunk/denonavr3312/badge.svg?branch=master)](https://coveralls.io/github/gyzpunk/denonavr3312?branch=master)

This package aims to implement the Denon control protocol described is 
[this document](https://www.denon.fr/uk/downloads/productdownloads?FileName=AVR3312CI_AVR3312_PROTOCOL_V760.pdf) 
for Denon AVR 3312 (but may also be compatible with other devices)

It uses telnet protocol to control the device unlike the [denonavr package](https://github.com/scarface-4711/denonavr) which
aims to use HTTP.

Based on my tests, HTTP seems slower and less efficient than telnet to control Denon AVR but that may come from my model.
 
## Usage

```python
from denonavr3312 import DenonAVR

with DenonAVR('x.x.x.x') as denon_avr:
    denon_avr.power.on()
    denon_avr.master_volume.set(-30)
```

## Test

```bash
pip install tox

tox
```