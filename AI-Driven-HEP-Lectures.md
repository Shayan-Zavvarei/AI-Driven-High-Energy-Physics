# AI-Driven High Energy Physics (HEP)
## Session 1: Lost in the Forest

### Defining High Energy Physics (HEP)
HEP involves studying fundamental particles and forces, drawing data from various sources and experiments.
### Key Sources and Facilities in HEP: 
HEP phenomena are explored using multiple methods and locations, including:
- Accelerators and Colliders: A notable example is the LHC (Large Hadron Collider).
- Reactors : An example mentioned is KamLand. Beam Dump experiments.
- Astroparticles originating from sources such as the Sun and Cosmic Rays.
- Specific related projects mentioned include Fermi LAT, Super-K, and Borexino.
- Observations related to the Earth.
- Cosmology:Planck-Gravitational Waves-LIGO-Virgo.
#### Exe 1-1: Design a detector for banana cargo at port? (Background free)
### How to use Catalog:
![How to use Catalog](photos/How%20to%20use%20Catalog.png)
### Classic Example:
A classic example in HEP is the SLAC-MIT DIS (Deep Inelastic Scattering) experiment

![Classic Example](photos/Classic%20Example:.png)

Steps in the Traditional Experiment: The traditional experiment requires several distinct processing steps:
Pre-process:
1. Readout.
2. Veto.
3. Trigger.

Post-Process:

4. Parameter Estimation.
5. Hypothesis Testing.

![Process](photos/process.png)

### Modern Example:
A modern example is referenced via the arXiv paper link: https://arxiv.org/abs/1308.044

![Modern Example](photos/modern%20example.png)

 In this detector setup, a scintillator is used such that when a neutrino interacts with it, a burst of photons is produced. These photons are then detected by the photosensors inside the detector.

Surrounding the central scintillator volume is a layer of water. This outer water shield helps absorb external radiation—such as cosmic muons—that might otherwise create background signals. When these incoming particles (e.g., muons) enter the water and travel faster than the speed of light in water, they produce Cherenkov radiation. This Cherenkov light can be detected and used to veto events originating from outside the central target volume. In this way, we can effectively distinguish between internal signals (from neutrino interactions) and external background events.

For example, in the observed signal waveform, the first peak corresponds to the initial positron deposit from the neutrino interaction. Approximately 10 microseconds later, the positron annihilates, producing a second peak followed by a characteristic tail—this decay profile reflects the time evolution and completion of the physical process.

Machine learning can leverage this physical understanding to classify events. By using features such as the interaction signature of the positron and the temporal shape of the signal (e.g., peak timing, presence of a delayed tail, pulse width), a model can effectively separate true neutrino-induced events from background or external events.
### Summary of Traditional Experiment Pipeline:
![Tradition Pipeline](photos/tradition%20pipleline.png)

### Bridging Tech of SBI
The core idea is to provide a model or neural network not only with observational data (the "observables") but also with the underlying physical principles. We then train the model to learn the mapping between these observables and the corresponding physical parameters or processes.

Importantly, by "observables" we do not mean raw detector data. Instead, we feed the model higher-level, processed representations—such as full sky maps of the CMB—rather than derived summary statistics like the CMB power spectrum (e.g., the \( C_\ell \) correlation function). The model learns to infer the underlying physics directly from these rich, spatially resolved inputs, and its output is an estimate of the physical parameters or conditions that generated the observed signal.

In essence, the network is trained to answer: “Given this observable map, what physical scenario produced it?”—bypassing traditional intermediate steps and leveraging the full information content of the data.

![SBI](photos/sbi.png)
### What if we reach to the physics directly from raw Data
What if we feed the network the full raw data directly? Could this approach enable the discovery of new physics?

By bypassing traditional preprocessing, feature engineering, or summary statistics—and instead giving the model access to the complete, unfiltered dataset—we allow it to identify subtle, non-linear, or previously unrecognized patterns that might be lost in conventional analysis pipelines. If the underlying physical laws leave imprints in the raw data that don’t conform to our current models, a sufficiently expressive and well-trained network might detect these anomalies and point toward physics beyond the standard paradigm.

In other words, end-to-end learning from raw observables could serve not just as a tool for parameter estimation, but as a hypothesis-free probe for new physics.



## Session 2: Towaed the Summit