# Design Principles

Below are the general principles adopted in the architecture design of NUTS Technology Platform.

## Instrument-Centered

The goal of NUTS Platform is to serve FSPs and help them build marketplace that serves makers and takers. Each marketplace is built on top of one financial instrument, so NUTS Platform should be centered on financial instrument.

* Each financial instrument should form an isolated management domain.
  * All data and assets of one financial instrument are kept and managed in its domain;
  * No cross-domain operation\(if any\) should be allowed without going through NUTS Platform;
  * Each domain might evolve into an autonomous zone in the future; 
* The NUTS Platform, minus the isolated domain for individual financial instrument,  should be thin and flexible.



