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

This material summarizes **Session 2** of the **AI-Driven HEP Introduction**, presented by S. A. Fard from the School of Physics (IPM). The session is titled **"Toward The Summit"**.

### 1. The Chess Analogy: Finding the Simplest Architecture

Session 2 begins by framing the discussion around artificial intelligence using the game of chess: **"Let's play chess"**.

The initial challenge posed is: **"Find the simplest architecture for a machine playing chess?"**.
![Chess](photos/chess.png)
#### 1.1 Brute-Force Optimization (MiniMax)

The foundational architectural concept introduced is **Brute-force MiniMax optimisation**.

However, implementing brute-force search quickly reveals complexity challenges:

- To **predict 5 moves ahead**, the number of possible positions falls within the **order of** $\sim 30^{10} \sim 10^{14}$.
- The sources comment that this brute-force method, while simple, is **"made it as simple as possible, but not simplest"**.

#### 1.2 Increasing Complexity: Optimization Techniques

The next step is to **"take one step forward and make the architecture more complex?"**.

The optimization technique introduced is **Alpha–beta pruning**. This technique is described as cutting off **"branches that cannot possibly affect the final decision"**.

The complexity reduction achieved by Alpha–beta pruning is significant, reducing the required calculation order to **order of** $\sim 10^{7}$.

#### 1.3 Incorporating Human Strategy and Cost

Further development involves integrating human-like strategic knowledge, such as **Opening tips** and **Ending Moves**.

The cost of computing power over time is briefly compared:

- **1990**: Computing costs were around $\sim 10^6\ \$$.
- **2020**: Computing costs dropped significantly to around $\sim 10^3\ \$$.

This comparison leads to **Exe 2-1: Estimate GPU cost in the near future**.

### 2. The Go Analogy and Modern AI

The session then moves to applying a **"similar procedure for playing Go!"**.

The complexity of Go far exceeds that of chess:

- The required calculation order for Go is estimated at **order of** $\sim 200^{10} \sim 10^{23}$.

The concept of modern, data-driven Go AI is referenced, citing the Google DeepMind project:  
[https://deepmind.google/research/projects/alphago/](https://deepmind.google/research/projects/alphago/).

Key elements of this AI approach include calculating probability:

- **The probability of moves $a$ at position $s$: $p_{\sigma}(a \mid s)$**.
- Referenced probability orders include **order of 50%**, **order of 80%**, and **order of 20%**.

This discussion sets up **Exe 2-2: Implement the MCTS via a simple Python code**.

### 3. The Core Idea of AI

The session concludes by defining the **Core idea of AI**.

The primary goal of AI is to **"make machine behave like human"**. This goal can be achieved through two primary approaches:

1. **Rule-based**  
2. **Data-based**

In other words, AI involves **"solving tasks that require intelligence, sometimes beyond human style"**.

The sources offer a direct comparison between the advancement of traditional Science and the advancement of AI:
![Core Idea](photos/coreidea.png)
| Field    | Advancement Method                                                                 |
|----------|------------------------------------------------------------------------------------|
| Science  | Advanced by inventing new experimental techniques to build theories from data.     |
| AI       | Advanced by inventing new learning algorithms to extract knowledge from data.      |


## AI-Driven HEP Introduction: Session 3 - Instrument

### References

The material covered in this session draws upon foundational texts in detector physics and astronomy instrumentation:

- Grupen, Claus, and Boris Shwartz. *Particle detectors*. Cambridge University Press, 2008.  
- Ade, Peter A. R., Matthew J. Griffin, and Carole E. Tucker. *Physical principles of astronomical instrumentation*. CRC Press, 2021.  
- Karttunen, Hannu, et al., eds. *Fundamental astronomy*. Berlin, Heidelberg: Springer Berlin Heidelberg, 2007.

---

### 1. Introduction: Interaction and Medium

The concept of a physical instrument, particularly a detector, fundamentally starts with **Interaction & medium**.

#### Key Principle
Every interaction process that occurs between a particle and matter can be utilized as the basis for a detector concept.

#### Main Interactions
The main interaction processes used in detector physics are:

1. **Ionisation**  
2. **Excitation**  
3. **Bremsstrahlung**

#### Particle Detection Requirement
- **Charged particles** (e.g., electrons) can be detected **directly** via these interactions.  
- **Neutral particles** (e.g., photons, neutrinos) must **produce charged particles** through an interaction to be detected.

---

### 2. Detection Regimes: Electromagnetic Waves

Detectors are designed based on the properties of the incoming flux, particularly its **wavelength** and **energy**.

#### A. Radio Photon Regime (Long Wavelength)

- **Energy**: $$( E \sim 10^{-3} \, \text{eV} )$$  
- **Wavelength**: $$( \lambda \sim 1 \, \text{mm} )$$

##### Interaction Medium
Radio photons interact primarily with:
- Conducting material (metal)  
- Plasma (Earth’s ionosphere)

##### Ionospheric Limitation
Ground-based radio astronomy is **not possible** for wavelengths longer than the Earth’s ionospheric plasma wavelength ($(\sim 24 \, \text{m}$), or frequency $(\sim 13 \, \text{MHz}$)).

The **plasma frequency** ($(\nu_p$)) relates to electron number density ($(n_e$)) by:  
$$[
\nu_p \sim 9 \sqrt{n_e}
]$$

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/radio-photon.png?raw=true" alt="Radio Photon" width="600"/>
</center>

##### Coherent vs. Incoherent Detection
- **Coherent detection**: Used for radio/microwaves; measures **amplitude and phase**.  
- **Incoherent (direct) detection**: Used at shorter wavelengths; measures only **intensity (power)**, ignoring phase.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/incoherent-detection.png?raw=true" alt="Incoherent Detection" width="600"/>
</center>
---

#### B. IR–Optical–UV Regime (Mid-Range Wavelength)

- **Photon energy**: $( E \sim 1 \, \text{eV} )$ to $( 10 \, \text{eV} )$

##### Interaction
Detection relies on **photon absorption**.

##### Material Response
High-conductivity materials act as **mirrors** in this energy range.

##### Bolometric Detectors
- Measure energy by detecting a **temperature rise** in a resistive material.

##### Photodetectors
- Use absorbed photon energy to create **charge carriers** (electrons/holes) under an electric field.  
- Common materials: **InSb** (Indium Antimonide), **InP** (Indium Phosphide), **GaAs** (Gallium Arsenide).

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/photodetector.png?raw=true" alt="Photodetector" width="600"/>
</center>

---

### 3. Photodetector Characteristics and the Photoelectric Effect

#### Detector Responsivity
Responsivity quantifies **current output per unit incident power**, depending on:

- $( \eta_d )$: Probability an incident photon liberates an electron  
- $( g )$: Photoconductive gain (material- and field-dependent)
* The Ideal of this part is that the Responsivity becomes high.

### The Photoelectric Effect
Electrons are emitted from a metal surface when exposed to light of sufficient frequency:

$[
K_{\text{max}} = h\nu - W
]$

- $( h\nu )$: Photon energy  
- $( W )$: Work function of the material  
- Requires $( h\nu \geq W )$

#### Interaction Probability
Photoabsorption probability per unit mass scales as:

$[
\propto \frac{Z^5}{E^{7/2}}
]$

**Implications**:
1. **High-Z materials** are far more efficient absorbers.  
2. Absorption probability **drops rapidly** with increasing photon energy.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/photoelectric-effect.png?raw=true" alt="Photoelectric Effect" width="600"/>
</center>

---

### 4. The Photomultiplier Tube (PMT)

A **PMT** converts low-intensity light into a measurable current via electron multiplication.

- A single photon on the **photocathode** can generate $(\sim 10^5)$ electrons through **dynode stages** (secondary emission).

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/pmt.png?raw=true" alt="PMT" width="600"/>
</center>

#### Dark Current
Unwanted internal current due to:
- Thermal electron emission from the photocathode  
- Spurious ionizing events

#### Dark Current Mitigation

1. **Optimal Voltage Selection $((V_{\text{opt}})$)**  
   - Below $(V_{\text{opt}})$: signal too weak  
   - Above $(V_{\text{opt}})$: dark current dominates

2. **Cooling**  
   - Typical ly cooled to **−20°C**  
   - Exponentially suppresses thermal emission

3. **Pulse Discrimination**  
   - Use **pulse height analysis** to reject noise events\


## AI-Driven HEP Introduction: Session 4 – Instrument II

### References

This session builds on foundational texts in detector physics and astronomical instrumentation:

- Grupen, Claus, and Boris Shwartz. *Particle detectors*. Cambridge University Press, 2008.  
- Ade, Peter A. R., Matthew J. Griffin, and Carole E. Tucker. *Physical principles of astronomical instrumentation*. CRC Press, 2021.  
- Karttunen, Hannu, et al., eds. *Fundamental astronomy*. Springer Berlin Heidelberg, 2007.


---

### I. General Detector Principles

The foundation of all detector instrumentation lies in **Interaction & medium**.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/photon-energy-range.png?raw=true" alt="Photon Energy Range" width="600"/>
</center>

#### Core Principle
> **Every interaction process between a particle and matter can serve as the basis for a detector concept.**

#### Primary Interaction Mechanisms
- **Ionisation**  
- **Excitation**  
- **Bremsstrahlung**

#### Detection of Neutral Particles
- **Charged particles** (e.g., electrons) interact directly and are detectable.  
- **Neutral particles** (e.g., photons, neutrinos) **must produce charged secondary particles** through an interaction to be observed.

---

### II. High-Energy Photon Interactions

At higher energies, photons interact via three key processes:

#### 1. Compton Scattering
- **Energy range**: $( \sim 10 \, \text{keV} )$ to $( 10 \, \text{MeV} )$  
- A high-energy photon (X-ray or γ-ray) **scatters off a free or loosely bound electron**, losing energy and increasing in wavelength.  
- The wavelength shift is given by:  
  $[
  \Delta \lambda = \frac{h}{m_e c} (1 - \cos \theta)
  ]$

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/compton-scattering.png?raw=true" alt="Compton Scattering" width="600"/>
</center>

#### 2. Inverse Compton Scattering
- A **low-energy photon** (e.g., microwave or optical) **gains energy** by scattering off a **relativistic electron**.

#### 3. Pair Production
- Occurs at photon energies **$( \gtrsim 100 , \text{MeV} )$**.  
- The photon converts into an **electron–positron pair** in the Coulomb field of a nucleus.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/pairproduction.png?raw=true" alt="Pair Production" width="600"/>
</center>

Note: Photons above a certain energy threshold are no longer stable and therefore cannot be observed.

#### Detection Strategy
The **charged particles** produced in these interactions (e.g., recoil electrons from Compton scattering, e⁺e⁻ pairs from pair production) are detected via their **ionisation** in the detector’s sensitive volume.

---

### III. Energy Loss by Charged Particles

As charged particles traverse matter, they lose kinetic energy through several mechanisms:

#### 1. Ionisation and Excitation
- The **dominant energy loss mechanism** at non-relativistic and moderately relativistic energies.  
- Caused by Coulomb interactions with atomic electrons, leading to excitation or ejection (ionisation).

#### 2. Electromagnetic Radiation
- Any **accelerated charged particle** emits radiation. Key examples:
  - **Cherenkov radiation**: emitted when particle velocity exceeds light speed in the medium.  
  - **Synchrotron radiation**: emitted by relativistic particles in magnetic fields (curved trajectories).

#### 3. Example: Energy Transfer by a Muon
- A muon with mass $( m_\mu = 106 \, \text{MeV}/c^2 )$ and Lorentz factor $( \gamma = 10 )$ (total energy $( E = 1.06 \, \text{GeV} )$) can transfer up to **$( \sim 100 \, \text{MeV} )$** to an atomic electron in a single collision.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/energyloss.png?raw=true" alt="Energy Loss" width="600"/>
</center>

Note: The position of the trough indicates the point beyond which the particle becomes relativistic. However, it should be noted that while the output plot shown has been smoothed, the raw data may exhibit some fluctuations.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/different-energyloss.png?raw=true" alt="Different Energy Loss" width="600"/>
</center>

Note: The heavier the particle, the more the relativistic transition trough shifts to the right. 

# Selected Particle Masses and Properties in Particle Physics

The table below lists well-known elementary and composite particles in the Standard Model and beyond, along with their approximate rest masses and key properties. Masses are given in energy units (MeV/$c^2$ or GeV/$c^2$), as is conventional in high-energy physics.

| Particle        | Symbol | Mass (MeV/$c^2$) | Electric Charge ($e$) | Spin | Type             | Notes |
|-----------------|--------|------------------|------------------------|------|------------------|-------|
| Electron        | $e^-$  | 0.511            | $-1$                  | 1/2  | Lepton           | Stable; lightest charged lepton |
| Muon            | $\mu^-$| 105.7            | $-1$                  | 1/2  | Lepton           | Decays via weak interaction ($\tau \approx 2.2\,\mu$s) |
| Tau             | $\tau^-$| 1777            | $-1$                  | 1/2  | Lepton           | Heaviest lepton; short-lived |
| Electron Neutrino | $\nu_e$ | < 0.8 eV       | 0                      | 1/2  | Lepton           | Extremely light; only interacts weakly |
| Muon Neutrino   | $\nu_\mu$ | < 0.3 eV       | 0                      | 1/2  | Lepton           | Mass not precisely known |
| Tau Neutrino    | $\nu_\tau$| < 18 eV        | 0                      | 1/2  | Lepton           | Heaviest neutrino (still very light) |
| Up quark        | $u$    | $\sim 2.2$       | $+2/3$                | 1/2  | Quark            | Constituent of protons/neutrons |
| Down quark      | $d$    | $\sim 4.7$       | $-1/3$                | 1/2  | Quark            | Constituent of protons/neutrons |
| Strange quark   | $s$    | $\sim 96$        | $-1/3$                | 1/2  | Quark            | Found in kaons, hyperons |
| Charm quark     | $c$    | $\sim 1275$      | $+2/3$                | 1/2  | Quark            | Discovered 1974; forms $J/\psi$ |
| Bottom quark    | $b$    | $\sim 4180$      | $-1/3$                | 1/2  | Quark            | Key in CP-violation studies |
| Top quark       | $t$    | $\sim 172{,}500$ | $+2/3$                | 1/2  | Quark            | Heaviest known elementary particle; decays before hadronizing |
| Photon          | $\gamma$| 0                | 0                      | 1    | Gauge boson      | Mediator of EM force; stable |
| $W$ boson       | $W^\pm$| 80{,}400         | $\pm 1$               | 1    | Gauge boson      | Mediator of weak force; short-lived |
| $Z$ boson       | $Z^0$  | 91{,}200         | 0                      | 1    | Gauge boson      | Neutral weak current mediator |
| Gluon           | $g$    | 0                | 0                      | 1    | Gauge boson      | Mediator of strong force; confined |
| Higgs boson     | $H^0$  | 125{,}100        | 0                      | 0    | Scalar boson     | Gives mass via Higgs mechanism |
| Proton          | $p$    | 938.3            | $+1$                  | 1/2  | Baryon (composite)| Stable (lifetime > $10^{34}$ yr) |
| Neutron         | $n$    | 939.6            | 0                      | 1/2  | Baryon (composite)| Free neutron decays in $\sim 880$ s |
| Pion (charged)  | $\pi^\pm$| 139.6           | $\pm 1$               | 0    | Meson (composite)| Lightest meson; mediates nuclear force |
| Pion (neutral)  | $\pi^0$| 135.0            | 0                      | 0    | Meson (composite)| Decays to photons ($\tau \sim 8 \times 10^{-17}$ s) |

> **Notes**:
> - Quark masses are *current quark masses* in the $\overline{\text{MS}}$ scheme at scale $\mu \approx 2$ GeV.
> - Neutrino masses are upper limits from oscillation and cosmological data; absolute values are not yet known.
> - Composite particles (e.g., proton, pion) are made of quarks bound by gluons.
> - All masses are approximate and may vary slightly depending on measurement or convention.

#### 4. Landau Distribution
- Describes the **statistical fluctuations** in energy loss for thin absorbers.  
- Characterizes the **asymmetric distribution** of energy deposition, with a long tail toward higher energy losses.  
- The **most probable energy loss** (not the mean) is often used as a reference in detector calibration.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/landau.png?raw=true" alt="Landau Distribution" width="600"/>
</center>

## AI-Driven HEP Introduction: Session 5 – Electronic

### References

This session continues the "AI-Driven HEP Introduction" series by **S. A. Fard** (School of Physics, IPM), drawing on foundational texts:

- Grupen, Claus, and Boris Shwartz. *Particle detectors*. Cambridge University Press, 2008.  
- Ade, Peter A. R., Matthew J. Griffin, and Carole E. Tucker. *Physical principles of astronomical instrumentation*. CRC Press, 2021.  
- Karttunen, Hannu, et al., eds. *Fundamental astronomy*. Springer Berlin Heidelberg, 2007.

---

### I. Measurement of a Physical Parameter

The essence of physical measurement is the **conversion of an input quantity into an easily measurable output quantity**.  
Example:  
$[
\text{Photon} \rightarrow \text{voltage or current}
]$

#### Detector Types and Their Output Quantities

| Detector Type               | Input / Principle                                | Output Quantity                                      |
|----------------------------|--------------------------------------------------|------------------------------------------------------|
| **Photoconductive**        | Photon rate incident on detector                | **Current** ∝ photon rate                           |
| **Photovoltaic**           | Photon rate                                     | **Voltage** ∝ photon rate                           |
| **Radio antenna**          | Amplitude of incident electric field            | **Current** ∝ field amplitude                       |
| **Bolometric detector**    | Absorbed electromagnetic power                  | **Temperature change** ∝ power (often converted to voltage) |
| **Charge Coupled Device (CCD)** | Number of incident photons during exposure | **Charge** ∝ number of photons                      |

> The **Ionisation Chamber** is also mentioned as a fundamental detector type in this context.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/ionisationchamber.png?raw=true" alt="Ionisation Chamber" width="600"/>
</center>

---

### II. The Signal, the Background, and the Noise

Three essential components define any measurement system:

#### A. Signal
- The **desired output** of the measurement.
- Two roles:
  1. **Known signal**: Used to calibrate and establish **sensitivity**.
  2. **Unknown signal**: Represents a potential **anomaly** or new physics.

#### B. Background
- An **unavoidable accompaniment** to the signal.
- Often **much larger in magnitude** than the signal itself.
- Typically has a **known functional form and variation** (e.g., cosmic rays, ambient radiation).

#### C. Noise
- **Unwanted random fluctuations** that introduce **uncertainty** in measurements.
- Affects both sensitivity (known signal) and anomaly detection (unknown signal).
- **Sources of noise**:
  1. **Signal** (intrinsic statistical fluctuations, e.g., Poisson noise)
  2. **Detector** (e.g., thermal noise, dark current)
  3. **Electronics** (e.g., amplifier noise, Johnson–Nyquist noise)

> Noise is fundamentally a **stochastic (random) process**.
Noise is the square root of the number of signals per unit time.
$$
\text{Noise} = \sqrt{N}
$$
where N is the number of signal events in a given time interval.
---

### III. Noise Management and Electronic Processing

#### Noise Handling Strategies

| Noise Source                          | Mitigation Strategy                                                                 |
|--------------------------------------|--------------------------------------------------------------------------------------|
| **Signal fluctuations**              | **Cannot be eliminated**—inherent to quantum/statistical nature of the signal.        |
| **Background fluctuations**          | **Minimized by reducing background** (shielding, coincidence cuts, etc.).            |
| **Detector & electronics noise**     | **Reduced via**: low-noise components, cooling, optimized circuit design, grounding. |

This noise primarily arises from:
- **Detector readout electronics**
- **Amplifiers and signal-processing circuits**

#### Key Electronic Concepts

#### 1. Responsivity
- Defined as output current per unit incident power (from Session 3).
- **High responsivity is desirable**, but **does not guarantee high sensitivity** if noise is large.
$$
S = \frac{\text{Change in output quantity}}{\text{Change in input quantity}}
$$

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/responsivity.png?raw=true" alt="Responsivity" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/lp-hp-filter.png?raw=true" alt="LP-HP Filter" width="600"/>
</center>

If the incoming frequency is much larger than the circuit’s characteristic frequency, the denominator becomes effectively infinite, so \( V_{\text{out}} \to 0 \)—meaning no response, i.e., a **low-pass filter** behavior.

Conversely, if the frequency is much smaller than the circuit’s time scale, the signal passes through unaffected—i.e., **high-pass filter** behavior.

#### 2. Signal-to-Noise Ratio (SNR)
- Noise $( f(t) )$ is modeled as a **random variable** with:
  - Mean = 0  
  - Variance = $( \sigma^2 )$ (called **noise power**)
- Example: $( \text{SNR} = 20 )$ indicates the signal is 20 times stronger than the RMS noise.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/snr.png?raw=true" alt="SNR" width="600"/>
</center>

In the ideal case, the amplitude follows a Gaussian distribution, and the noise power is equal to the variance of that Gaussian amplitude, as illustrated in Figure B.
#### 3. Filtering and Signal Shaping
- **Low-pass filters**: suppress high-frequency noise.
- **High-pass filters**: remove slow drifts or DC offsets.
- **Integration–differentiation techniques** are used to:
  - **Integrate** slow (low-frequency) components for energy measurement.
  - **Differentiate** fast (high-frequency) components for timing or pulse detection.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/signal-integration.png?raw=true" alt="Signal Integration" width="600"/>
</center>


## Comprehensive Analysis of Statistical Concepts: Tutorial 2- Dr.Jalali's presentation

### Slide 1: Data Modeling, Parameter Estimation, and Optimization

This initial slide sets the stage for scientific inference by posing the core methodological challenges:

<center>
  <img src=photos/parameter-estimation.png
</center>

1. **Data Modeling:** The key objective is to determine **"How can this observation be described using a given physical model M with free parameters $\theta$?"**. The parameters ($\theta$) are the unknown variables of interest within the model.
2. **Criterion:** To assess the validity of the model, a **"criterion for assessing the similarity between data and model"** must be established. This metric quantifies **"How well the model predicts the observed data?"**.
3. **Optimization:** The ultimate goal is **Optimization**, which aims to find the **"Best Value"** for the parameters $\theta$ by optimizing the defined criterion (e.g., maximizing similarity or minimizing a loss function).
4. **Error Estimation:** After the best parameter value is found, **Error Estimation** is required to quantify the uncertainty associated with the determined values of $\theta$.
5. **Probabilistic Approach Introduction:** The solution framework begins with the **Probabilistic Approach**. This approach is founded on the concept of the **Likelihood**, which is defined as the **"Probability of observing the data given a specific parameter value"**.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/parameter-estimation-app.png?raw=true" alt="Parameter Estimation App" width="600"/>
</center>

center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/estimating-resistance-1.png?raw=true" alt="Estimating Resistance 1" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/estimating-resistance-2.png?raw=true" alt="Estimating Resistance 2" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/estimating-resistance-3.png?raw=true" alt="Estimating Resistance 3" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/estimating-resistance-4.png?raw=true" alt="Estimating Resistance 4" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/error-estimation-1.png?raw=true" alt="Error Estimation 1" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/error-estimation-2.png?raw=true" alt="Error Estimation 2" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/error-estimation-3.png?raw=true" alt="Error Estimation 3" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/error-estimation-4.png?raw=true" alt="Error Estimation 4" width="600"/>
</center>

### Slide 2: Probabilistic Approach, Central Limit Theorem, and Machine Learning

The second segment expands on the probabilistic foundation and links it to computational methods.

- **Likelihood and CLT:** The **Likelihood**—the probability $P(\text{Data} \mid \theta)$—is the central tool in the probabilistic approach. The **Central Limit Theorem** (CLT) is mentioned in this context, often serving as the theoretical justification for assuming a **Gaussian Likelihood** when dealing with errors resulting from the sum of many independent random effects.
- **Machine Learning as Optimization:** The source clearly states that **"Machine Learning Is Nothing But Optimization"**. In training a model, the goal is to optimize a **Loss Function** using **"Training Data + Labels"**. The data flows through **Input** components and **Hidden Layers** to generate **Outputs** which are compared against the **Labels**.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/machine-learning.png?raw=true" alt="Machine Learning" width="600"/>
</center>

### Slides 2–4: Frequentist Approach vs. Bayesian Approach Comparison

The subsequent slides delineate the fundamental philosophical and practical differences between the two major schools of statistical inference:

| Aspect | Frequentist Approach | Bayesian Approach |
| :--- | :--- | :--- |
| **Philosophy** | **Parameters ($\theta$) are fixed but unknown constants**; randomness stems exclusively from the data. | **Parameters are random variables** characterized by probability distributions. |
| **Probability Interpretation** | Defined as the **"Long-run frequency of outcomes over repeated experiments"**. | Represents the **"Degree of belief or uncertainty about parameters,"** which is noted to align better with intuitive understanding. |
| **Parameters ($\theta$)** | Treated as **fixed, unknown quantities**. | Treated as **random variables with prior distributions**. |
| **Prior Information** | **Not used**; inference is based **solely on data**. | **Explicitly included** in the analysis. |
| **Core Objective** | To **"Estimate $\theta$ using data only"**. | To **"Update prior distribution to posterior using data"**. |
| **Hypothesis Testing** | Based on **p-values and rejection of null hypotheses**. | Based on **posterior probabilities and model comparison** (e.g., Bayes factor). |
| **Common Tools** | **MLE** (Maximum Likelihood Estimation), **confidence intervals, p-values, likelihood ratio tests**. | **Bayes’ theorem, priors, posteriors, MCMC, variational inference**. |
| **Computation** | Often **simpler and faster**; analytic solutions available for many problems. | Can be **computationally intensive, especially in high dimensions**. |
| **Typical Use Cases** | **Classical experiments, large-sample statistics, regulated fields** (e.g., pharma). | **Complex models, small datasets, simulation-based inference, hierarchical models**. |

### Slide 5: The Bayesian Approach and Bayes' Theorem

This slide formalizes the structure of Bayesian inference. The process involves **Observation, Adopting Model, and Estimating Parameters**.

Bayes' theorem defines the relationship between the three core probabilistic components:

$$
\text{Posterior} \propto \text{Likelihood} \times \text{Prior}
$$

1. **Prior Distribution (Prior):** This represents **"Your initial belief about a parameter before seeing any data"**.
2. **Likelihood:** This is the **"Probability of observing the data given a specific parameter value"** ($P(\text{Data} \mid \theta)$).
3. **Posterior Distribution (Posterior):** This represents **"Your updated belief about the parameter after seeing the data"** ($P(\theta \mid \text{Data})$).

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/bayesian-inference.png?raw=true" alt="Bayesian Inference" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/likelihood-scheme.png?raw=true" alt="Likelihood Scheme" width="600"/>
</center>

### Slide 6: Traditional Bayesian Inference and Analytical Solutions

This section addresses the requirements and initial methods of calculating the posterior.

- **Traditional Requirement:** Classical Bayesian methods (Traditional Bayesian Inference) necessitate **"an explicit analytical form of how the data depends on the parameters $\theta$ in order to compute the likelihood"**.
- **Analytical Solution:** This is a **"closed-form approach to compute the posterior distribution exactly"**. It is only applicable when both the **prior and likelihood are mathematically tractable**.
- **Grid-based Methods:** These involve **discretizing the parameter space into a grid** and **evaluating the posterior at each point**. They are considered **simple and intuitive** and **useful for low-dimensional problems**, but they are **computationally expensive in high dimensions**.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/bayesian-limitation.png?raw=true" alt="Bayesian Limitation" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/bayesian-limitation2.png?raw=true" alt="Bayesian Limitation 2" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/bayesian-limitation3.png?raw=true" alt="Bayesian Limitation 3" width="600"/>
</center>

### Slide 7: Approximate and Sampling Methods

When analytical or grid-based solutions are infeasible, approximate and sampling methods are utilized:

1. **Variational Inference (VI):** This is an **approximate Bayesian inference method**. It works by **replacing a complex posterior distribution with a simpler, parameterized distribution** and then **optimizing that approximation**.
2. **Sampling-Based Methods:** These methods aim to **approximate the posterior distribution by generating a large number of representative samples from it**.
    - Sub-categories include **Rejection Sampling**, **Importance Sampling**, and **MCMC Methods** (Markov Chain Monte Carlo).
    - Key MCMC algorithms are listed: **Metropolis-Hastings**, **Gibbs Sampling**, **Hamiltonian Monte Carlo (HMC)**, and **NUTS (No-U-Turn Sampler)**.
<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/metropolis.png?raw=true" alt="Metropolis" width="600"/>
</center>


### Slides 8–9: Simulation-Based Inference (SBI) Framework

The final concept introduced is the **Simulation-Based Inference (SBI) Framework**, designed for models where the likelihood cannot be computed explicitly.

- **Gaussian Likelihood Justification:** The **Gaussian likelihood** is often justified by the **Central Limit Theorem**. The **Metropolis-Hastings Markov Chain Monte Carlo (MCMC)** method is noted as a core tool for sampling the **Estimated Posterior**.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/gaussian-likelihood.png?raw=true" alt="Gaussian Likelihood" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/metro-fig1.png?raw=true" alt="Metro Fig 1" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/metro-fig2.png?raw=true" alt="Metro Fig 2" width="600"/>
</center>

- **Forward Modeling:** This is the starting point for SBI. It describes the process of generating data $D$ (or a **summary statistic**) given a set of parameters $\theta$, represented as $D(\theta)$.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/forward-modeling.png?raw=true" alt="Forward Modeling" width="600"/>
</center>

- **Emulators (Surrogate Models):** These models are used to mimic or replace the complex forward model $D(\theta)$. They take the parameter $\theta$ as **Input** and typically involve **Hidden Layers** to produce the simulated **Outputs**.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/emulators.png?raw=true" alt="Emulators" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/emulators2.png?raw=true" alt="Emulators 2" width="600"/>
</center>

- **Inference Pipeline:** In SBI, parameters are first sampled from the **Prior**. The parameters are fed into the **Forward Modeling** or **Emulators** to generate a **summary statistic**. This summary statistic is then compared to the **Observation** using an **Inference** technique (e.g., **MCMC**) to yield a **Posterior sample**.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/sbi-framework.png?raw=true" alt="SBI Framework" width="600"/>
</center>

- **Conclusion:** The process concludes with an acknowledgment of the **Assumed Likelihood** used in the analysis.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/sbi-starting.png?raw=true" alt="SBI Starting" width="600"/>
</center>

## AI-Driven HEP: Session 6 - Statistical Learning

### Title Slide

This session, titled **"Statistical Learning"**, is part of the **AI-Driven High Energy Physics (HEP)** lecture series. It is presented by **S. A. Fard** from the **School of Physics, Institute for Research in Fundamental Sciences (IPM)**.

---

### Core References (Part 1)

The session builds upon foundational and modern textbooks in statistical and machine learning:

- **James, Gareth, et al.** *An Introduction to Statistical Learning: With Applications in Python.* (2023)  
- **Hastie, Trevor, et al.** *The Elements of Statistical Learning: Data Mining, Inference, and Prediction.* (2009)  
- **Bishop, Christopher M.** *Pattern Recognition and Machine Learning.* Springer, (2006)  
- **Chollet, François.** *Deep Learning with Python.* (2021)

These texts provide the theoretical and practical backbone for statistical learning methodologies used across scientific domains, including HEP.

---

### Additional References (Part 2)

Further references include theoretical machine learning resources and domain-specific documents from the **DUNE collaboration**:

- **Shalev-Shwartz, Shai, and Shai Ben-David.** *Understanding Machine Learning: From Theory to Algorithms.* (2014)  
- **Tingjun Yang,** *A Brief Description of Data Products,* ProtoDUNE Analysis Workshop, CERN (January 27, 2019)  
- **Gabriela Vitti Stenico,** *Development of the Computing Framework for Monitoring the Quality of ProtoDUNE Off-line Data,* DUNE Collaboration Meeting (2025)

These materials bridge general machine learning theory with real-world applications in particle physics experiments.

---

### hanging the Mindset

Before diving into technical content, a conceptual reset is encouraged:

1. **Take a deep breath**  
2. **Forget everything you’ve heard so far**  
3. **“You are going to be a data scientist from now on.”**

This mindset shift emphasizes adopting a data-centric, model-driven perspective essential for modern scientific analysis.

---

### What Is Statistical Learning?

Statistical Learning explores the relationship among three core elements:

- **(Input) $X$**  
- **(Uncertainty) $\epsilon$**  
- **(Output) $Y$**

This is often framed as modeling the underlying function $f$ such that:
$$
Y = f(X) + \epsilon
$$

#### Terminology:
- **Output ($Y$)**: Also known as the **response**, **dependent variable**, or **target**.  
- **Input ($X$)**: Referred to as **predictors**, **independent variables**, or **features**.

---

### Formal Definition and Learning Framework

**Statistical learning** is formally defined as:
> “A set of approaches for estimating $f$.”

To operationalize this estimation, a complete learning framework consists of six interconnected components:

1. **Input** – The data fed into the system (e.g., features, measurements)  
2. **Architecture** – The structure of the model (e.g., neural network, decision tree)  
3. **Output** – The prediction or result produced by the model  
4. **Supervision** – Whether labels are provided (supervised vs. unsupervised)  
5. **Task** – The objective (e.g., classification, regression, clustering)  
6. **Optimization** – The method used to adjust model parameters (e.g., gradient descent)

These components collectively define how a statistical learning system is designed, trained, and evaluated.

---

### Input Structure

A key practical consideration is: **“What does an input look like?”**

In computational implementations—especially in deep learning—the input is typically represented as a **multidimensional array** (tensor).

Common shapes include:

- `(n, m, l, k)` — General 4D tensor (e.g., batch × height × width × channels)  
- `(n, 1, 1, k)` — Simplified spatial dimensions (e.g., tabular data reshaped for CNNs)  
- `kn` — Flattened representation (e.g., vectorized input of length $k \times n$)  
- `(n, 1, l, k)` — Partially structured input (e.g., time-series or 1D signals with channel depth)

Here:
- `n` often denotes the **number of samples** (batch size)  
- Other dimensions (`m`, `l`, `k`) represent spatial, temporal, or feature axes depending on context

Understanding input geometry is crucial for selecting appropriate architectures and preprocessing pipelines.

## AI-Driven HEP: Session 7 - Statistical Learning II

## Title Slide

This session, titled **"Statistical Learning II"**, is the continuation of the **AI-Driven High Energy Physics (HEP)** lecture series. It is presented by **S. A. Fard** from the **School of Physics, Institute for Research in Fundamental Sciences (IPM)**.

---

### References

The session builds on the same foundational literature as Session 6, including both general machine learning texts and HEP-specific resources:

- **James, Gareth, et al.** *An Introduction to Statistical Learning: With Applications in Python.* (2023)  
- **Hastie, Trevor, et al.** *The Elements of Statistical Learning: Data Mining, Inference, and Prediction.* (2009)  
- **Bishop, Christopher M.** *Pattern Recognition and Machine Learning.* Springer, (2006)  
- **Chollet, François.** *Deep Learning with Python.* (2021)  
- **Shalev-Shwartz, Shai, and Shai Ben-David.** *Understanding Machine Learning: From Theory to Algorithms.* (2014)  
- **Tingjun Yang,** *A Brief Description of Data Products,* ProtoDUNE Analysis Workshop, CERN (January 27, 2019)  
- **Gabriela Vitti Stenico,** *Development of the Computing Framework for Monitoring the Quality of ProtoDUNE Off-line Data,* DUNE Collaboration Meeting (2025)

---

### What Does an Input Look Like? — Beyond Regular Grids

While traditional inputs are often represented as dense arrays with shape `(n, m, l, k)` (e.g., images or structured tensors), **real-world scientific data frequently violates this assumption**.

Key challenges arise when:
- **The organized `(m, l, k)` data format no longer works**  
- Data becomes **sparse**, **irregular**, or **non-Euclidean**

Examples of such data include:
- **Sparse images** (e.g., particle detector hits with mostly empty space)  
- **Sequences of words** (e.g., natural language or symbolic event logs)  
- **Graphs** (e.g., particle interaction networks, detector geometries)

---

### Graph Format as Input

In many HEP applications, data is naturally represented as a **graph**:
- **Nodes** represent entities (e.g., detector channels, particles)  
- **Edges** represent relationships or interactions

A graph is typically described by:
- **Node feature matrix** `X` (e.g., `X = [47, 18, 13, 56, 36, 32, 99, 54, 2]`)  
- **Adjacency matrix** `A`, indicating connections between nodes  
- **Edge attributes** `E`, possibly weighted (e.g., `(11,12): w₂`)

This representation relaxes the rigid grid assumption and allows modeling of **complex relational structures**.

---

### Text Format as Input

Another important input modality is **text**, which appears in metadata, logs, or symbolic representations of events.

Key questions in text modeling:
- **How much does word order affect understanding?**  
- **How are word similarities captured?**  
- **How does context influence meaning?**

Challenges include:
- **Vocabulary size**: ~10⁵ unique English words vs. ~10¹⁵ total word occurrences on the web  
- **Semantic similarity**: Words like “electron” and “muon” may be functionally similar in HEP despite different surface forms  
- **Context dependence**: The same word may have different meanings in different experimental contexts

Text must be transformed from **natural language** into **machine-readable representations** (e.g., embeddings).

---

### Domain of the Data

Regardless of format (array, graph, or text), all inputs are assumed to originate from a **data domain** characterized by:

- **Distribution**: The underlying probability distribution from which data is drawn  
- **Uncertainty**: Inherent noise or variability in observations  
- **I.I.D. assumption**: Data points are often assumed to be **Independent and Identically Distributed**—though this may not hold in HEP (e.g., correlated detector noise, systematic shifts)

---

### Prediction (Inference) and Model Evaluation

The ultimate goal of statistical learning is **prediction** (or **inference**): using a learned model to make accurate predictions on new, unseen data.

Key theoretical concepts include:
- **Maximum Likelihood Estimation (MLE)**: Under Gaussian noise assumptions, MLE reduces to **minimizing the squared error loss**  
- **Bias-Variance Tradeoff**: A fundamental tension between:
  - **Bias**: Error from oversimplifying the model  
  - **Variance**: Error from overfitting to training data

Balancing this tradeoff is essential for **generalization**—ensuring models perform well beyond the training set.

---

### Incompleteness and Generalization

Real-world datasets are often:
- **Incomplete** (missing features, partial observations)  
- **Non-stationary** (domain shifts over time or between experiments)

Thus, robust statistical learning in HEP requires:
- Careful validation strategies  
- Domain adaptation techniques  
- Uncertainty quantification in predictions

These considerations ensure that models remain **reliable, interpretable, and physically meaningful** in high-stakes scientific contexts.

# Session 8: Linear Regression  
**AI-Driven High Energy Physics (HEP)**  
*S. A. Fard – School of Physics (IPM)*

## References
1. James, Gareth, et al. *An Introduction to Statistical Learning: With Applications in Python* (2023)  
2. Hastie, Trevor, et al. *The Elements of Statistical Learning: Data Mining, Inference, and Prediction* (2009)  
3. Bishop, Christopher M. *Pattern Recognition and Machine Learning* (2006)  
4. Chollet, François. *Deep Learning with Python* (2021)  
5. Shalev-Shwartz, Shai, and Shai Ben-David. *Understanding Machine Learning: From Theory to Algorithms* (2014)

---

## Why Use Linear Regression?

- **Baseline Model for Comparison**: Serves as a simple, interpretable benchmark.
- **Fast and Computationally Efficient**: Closed-form solution enables rapid fitting.
- **Good Approximation of Local Relationships**: Works well when the true relationship is approximately linear in the region of interest.

---

## Simple Linear Regression

The model assumes a linear relationship between one predictor $X$ and response $Y$:

$$
Y = \beta_0 + \beta_1 X + \varepsilon
$$

- $\beta_0$: intercept  
- $\beta_1$: slope  
- $\varepsilon$: random error term (often assumed $\varepsilon \sim \mathcal{N}(0, \sigma^2)$)

### Estimating the Coefficients

Two standard approaches:
- **Least Squares Estimation (LSE)**: Minimizes the sum of squared residuals.
- **Maximum Likelihood Estimation (MLE)**: Equivalent to LSE under Gaussian noise.

### Difference Between Least Squares and Maximum Likelihood

Least Squares (LS) and Maximum Likelihood Estimation (MLE) are two fundamental parameter estimation methods in statistics that, while sometimes yielding identical results, have different underlying philosophies and applications.

#### Least Squares Method

The least squares method is an estimation approach that aims to **minimize the sum of squared errors**—the difference between observed and predicted values. In this method, parameters are chosen to minimize the quantity:

$$
\sum_{i=1}^{N} (y_i - \hat{y}_i)^2
$$

where:
- $y_i$ represents observed values,
- $\hat{y}_i$ represents predicted values.

This method:
- Does **not require assumptions** about any specific probability distribution,
- Focuses purely on minimizing **geometric distance** (in the space of outputs),
- Is traditionally associated with **regression line fitting**,
- Is **computationally simple** and historically easier to calculate by hand.

#### Maximum Likelihood Estimation

Maximum Likelihood Estimation operates by **maximizing the probability** (likelihood) of observing the given data under a **specified probability distribution**. This method:
- Requires defining a **probabilistic model** for the data (e.g., Gaussian, Poisson),
- Selects parameters that **maximize the likelihood function** $ \mathcal{L}(\theta \mid \text{data}) $.

MLE is **asymptotically optimal**: as the sample size grows large, it achieves the lowest possible variance among consistent estimators (under regularity conditions).

#### Relationship and Key Differences

- **Equivalence under Gaussian noise**:  
  Least squares estimation is **equivalent to MLE** when the errors are assumed to follow a **normal (Gaussian) distribution** with **zero mean and constant variance** ($ \varepsilon_i \sim \mathcal{N}(0, \sigma^2) $).

- **Philosophical difference**:  
  - **Least squares** is a **geometric/deterministic** method focused on minimizing prediction error.
  - **Maximum likelihood** is a **probabilistic/statistical** method that requires a **distributional assumption**.

- **Performance considerations**:  
  - For **small sample sizes**, MLE can outperform LS **if the distributional assumption is correct**.
  - For **non-normal errors** or **heteroscedasticity**, MLE (with an appropriate likelihood model) is more **flexible and robust** than LS.
  - LS remains popular due to its **simplicity and computational efficiency**, even when distributional assumptions are not strictly met.

> **Summary**: LS is distribution-free and intuitive; MLE is model-based and statistically principled. They coincide under Gaussian errors—but diverge in philosophy and applicability beyond that.

### Residual Sum of Squares (RSS)

$$
\text{RSS} = \sum_{i=1}^n (y_i - \hat{y}_i)^2 = \sum_{i=1}^n (y_i - \hat{\beta}_0 - \hat{\beta}_1 x_i)^2
$$

Define:
- $S_{xx} = \sum_i (x_i - \bar{x})^2$
- $S_{xy} = \sum_i (x_i - \bar{x})(y_i - \bar{y})$
- $S_{yy} = \sum_i (y_i - \bar{y})^2$

Then:
$$
\hat{\beta}_1 = \frac{S_{xy}}{S_{xx}}, \quad \hat{\beta}_0 = \bar{y} - \hat{\beta}_1 \bar{x}
$$

---

## Multiple Linear Regression

Extends simple regression to $p-1$ predictors:

$$
Y = \beta_0 + \beta_1 X_1 + \cdots + \beta_{p-1} X_{p-1} + \varepsilon
$$

In matrix form:
$$
\mathbf{Y} = \mathbf{X} \boldsymbol{\beta} + \boldsymbol{\varepsilon}
$$

Where:
- $\mathbf{Y}$: $n \times 1$ response vector  
- $\mathbf{X}$: $n \times p$ design matrix (first column = 1s for intercept)  
- $\boldsymbol{\beta}$: $p \times 1$ coefficient vector  
- $\boldsymbol{\varepsilon}$: $n \times 1$ error vector, $\varepsilon_i \overset{\text{iid}}{\sim} \mathcal{N}(0, \sigma^2)$

### Residual Vector and RSS

$$
\mathbf{e}(\boldsymbol{\beta}) = \mathbf{Y} - \mathbf{X}\boldsymbol{\beta}
$$
$$
\text{RSS}(\boldsymbol{\beta}) = \mathbf{e}^\top \mathbf{e}
$$


### Normal Equations and Solution

Minimizing RSS gives:
$$
\frac{\partial \text{RSS}}{\partial \boldsymbol{\beta}} = -2\mathbf{X}^\top \mathbf{Y} + 2\mathbf{X}^\top \mathbf{X} \boldsymbol{\beta} = 0
$$

Solving yields the **ordinary least squares (OLS)** estimator:
$$
\hat{\boldsymbol{\beta}} = (\mathbf{X}^\top \mathbf{X})^{-1} \mathbf{X}^\top \mathbf{Y}
$$

> **Note**: This requires $\mathbf{X}^\top \mathbf{X}$ to be invertible (i.e., full column rank).

---

## Error Estimation and Uncertainty

### Unbiased Estimate of $\sigma^2$

**Exercise 1**: Show that
$$
\hat{\sigma}^2 = \frac{\text{RSS}(\hat{\boldsymbol{\beta}})}{n - p}
$$
is an unbiased estimator of $\sigma^2$, assuming $\varepsilon_i \overset{\text{iid}}{\sim} \mathcal{N}(0, \sigma^2)$.

> **Explanation**: The denominator $n - p$ accounts for the $p$ estimated parameters (degrees of freedom correction).

### Distribution of RSS

If $\sigma^2$ is known, then:
$$
\frac{\text{RSS}(\hat{\boldsymbol{\beta}})}{\sigma^2} \sim \chi^2_{n - p}
$$

This underpins hypothesis tests and confidence intervals.

> **Comment from slides**: *"The nightmare of 'model the uncertainty'"* — highlights that quantifying uncertainty (not just prediction) is often the hardest part in scientific applications like HEP.

---

## Generalized Least Squares (Weighted Case)

**Exercise 2**: Starting from the weighted residual sum of squares:
$$
\text{RSS}_\Sigma(\boldsymbol{\beta}) = \mathbf{e}^\top \Sigma^{-1} \mathbf{e}
$$
show that the minimizer is:
$$
\hat{\boldsymbol{\beta}} = (\mathbf{X}^\top \Sigma^{-1} \mathbf{X})^{-1} \mathbf{X}^\top \Sigma^{-1} \mathbf{Y}
$$

> **Explanation**: This is the **Generalized Least Squares (GLS)** estimator, used when errors have known covariance $\Sigma$ (e.g., heteroscedastic or correlated errors). OLS is recovered when $\Sigma = \sigma^2 I$.

---

## Challenges

> **"How to generalize to cover more complicated functions?"**

Linear models are limited to linear relationships in the parameters. Real-world data often require:
- Nonlinear basis expansions (polynomials, splines)
- Kernel methods
- Neural networks
- Regularization (ridge, lasso) for high-dimensional settings

In HEP, linear regression is often a starting point before applying more flexible (but less interpretable) models.

---
# Session 9: Neural Networks  
**AI-Driven High Energy Physics (HEP)**  
*S. A. Fard – School of Physics (IPM)*

## References
1. James, Gareth, et al. *An Introduction to Statistical Learning: With Applications in Python* (2023)  
2. Hastie, Trevor, et al. *The Elements of Statistical Learning: Data Mining, Inference, and Prediction* (2009)  
3. Bishop, Christopher M. *Pattern Recognition and Machine Learning* (2006)  
4. Chollet, François. *Deep Learning with Python* (2021)  
5. Shalev-Shwartz, Shai, and Shai Ben-David. *Understanding Machine Learning: From Theory to Algorithms* (2014)

---

## Motivation

> **Recall the challenge from Session 8**:  
> *"How to generalize linear regression to cover more complicated (nonlinear) functions?"*

Goals:
- Find optimal values for model parameters.
- Extend modeling capacity beyond linear relationships.

> **Explanation**: Linear models cannot capture complex patterns (e.g., interactions, nonlinearities). Neural networks address this through composition of simple nonlinear transformations.

---

## Optimization: From Linear Regression to Gradient-Based Learning

Consider a simple linear model:
$$
y = a x + b
$$

### Loss Function (Squared Error)
$$
L = \sum_i (y_i - a x_i - b)^2
$$

This measures how poorly the current parameters $(a, b)$ fit the data.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/neural_linear_optimization.png?raw=true" alt="Linear Optimization" width="600"/>
</center>

> **Note**: Minimizing this loss is equivalent to ordinary least squares (OLS) in linear regression—but now we’ll use iterative optimization instead of a closed-form solution.

---

## Gradient Descent

Update rules:
$$
a_{\text{new}} = a_{\text{old}} - \eta \frac{\partial L(a_{\text{old}},b_{\text{old}})}{\partial a_{\text{old}}}, \quad
b_{\text{new}} = b_{\text{old}} - \eta \frac{\partial L(a_{\text{old}},b_{\text{old}})}{\partial b_{\text{old}}}
$$

- $\eta$: **learning rate** (step size controlling how fast we update parameters)
- $\frac{\partial L}{\partial a}, \frac{\partial L}{\partial b}$: gradients indicating the direction of steepest increase in loss

> **Example given in slides**:  
> Data: $(x_1=1, y_1=1), (x_2=2, y_2=2), (x_3=3, y_3=2)$  
> Start with $a=1, b=1$, then iteratively update using gradient descent.

---

## Stochastic Gradient Descent (SGD)

Instead of computing gradients over the **entire dataset**, SGD uses:
- A **single data point** (pure stochastic), or
- A **mini-batch** (small random subset)

Benefits:
- Faster per-iteration updates
- Can escape local minima due to noise
- Scales to large datasets

> **Note**: Most deep learning uses mini-batch SGD. Advanced variants (e.g., **Adam**, RMSProp) adapt the learning rate per parameter.

---

## Generalization: Adding Complexity

### 1. **More Features (Higher Dimensions)**
$$
y = a_1 x_1 + a_2 x_2 + b
$$
Extends to multivariate linear models (as in multiple linear regression).

### 2. **Capturing Non-Linearity**
Apply a **nonlinear activation function** $A(\cdot)$:
$$
y = A(a_1 x_1 + a_2 x_2 + b)
$$

* In which here A is the **activation** function
Common activation functions:
- **Heaviside step**: binary threshold (rarely used in practice)
- **Sigmoid**: $\sigma(z) = \frac{1}{1 + e^{-z}}$ → outputs in $(0,1)$; useful for probability-like outputs
- **ReLU (Rectified Linear Unit)**: $\text{ReLU}(z) = \max(0, z)$  
  - Simple derivative
  - Fast computation
  - Avoids vanishing gradients (compared to sigmoid)

> **Explanation**: Activation functions introduce nonlinearity, enabling neural networks to approximate arbitrary continuous functions (Universal Approximation Theorem).
photo of generalization 1
photo of generalozation

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/neural_generalization.png?raw=true" alt="Generailization of nn" width="600"/>
</center>

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/neutal_relu_compare.png?raw=true" alt="Relu" width="600"/>
</center>

---

## Building Deeper Models: Hidden Layers

Example with two hidden units:
- Hidden unit 1: $z_1 = a_{11} x_1 + a_{12} x_2 + b_1$
- Hidden unit 2: $z_2 = a_{21} x_1 + a_{22} x_2 + b_2$
- Output: $y = A_1(z_1) + A_2(z_2) + b_3$

> **Slide example values**:
> ```
> a11 = a12 = 1,  a21 = -1, a22 = 1
> b1 = b2 = b3 = 0
> A1 = 1, A2 = -1
> ```

This simple network can already represent piecewise-linear functions (e.g., a "V" shape), which a single linear model cannot.

> **Key idea**: By stacking layers of such units, neural networks build **hierarchical representations** of data—starting from simple features to complex abstractions.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/neural_generalization_2.png?raw=true" alt="Deeper Model" width="600"/>
</center>
---

## Neural Network Architecture

A typical feedforward neural network consists of:
- **Input layer**: raw features (e.g., $x_1, x_2$)
- **Hidden layer(s)**: intermediate representations (with activation functions)
- **Output layer**: final prediction (e.g., class probability or regression value)

> **Note**: Despite the name, the "network" is just a composition of parametric functions:
> $$
> \text{Output} = f_L \circ f_{L-1} \circ \cdots \circ f_1(\text{Input})
> $$

---

## Softmax: For Multi-Class Classification

Given a vector of **logits** (unnormalized scores) $\mathbf{z} = [z_1, z_2, \dots, z_C]$ for $C$ classes:

$$
\text{softmax}(z_i) = \frac{e^{z_i}}{\sum_{j=1}^C e^{z_j}}
$$

Properties:
- Outputs are **positive** and **sum to 1** → can be interpreted as **class probabilities**
- Amplifies larger logits (due to exponential)
- Logits $z_i$ can be any real number (positive or negative)

> **Physics connection**: This is mathematically identical to the **Boltzmann (Gibbs) distribution** in statistical mechanics, where $z_i$ plays the role of negative energy $(-E_i / kT)$.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/neural_network.png.png?raw=true" alt="Neural Network" width="600"/>
</center>

---

## Cross-Entropy Loss

For classification with true labels $y_{n,i} \in \{0,1\}$ (one-hot encoded) and predicted probabilities $\hat{y}_{n,i} = \text{softmax}(z_i)$, the loss is:

$$
L = -\frac{1}{N} \sum_{n=1}^N \sum_{i=1}^C y_{n,i} \log(\hat{y}_{n,i})
$$

> **Exercise 3 (from slides)**: *Prove that, assuming the Boltzmann distribution, this loss function arises naturally as the negative log-likelihood.*

> **Explanation**: Minimizing cross-entropy is equivalent to maximizing the likelihood of the correct class under the softmax model—standard in multi-class deep learning.

---

## Summary

- Neural networks generalize linear models by:
  - Using **nonlinear activation functions** (e.g., ReLU, sigmoid)
  - Stacking **layers** to learn hierarchical features
- Optimization is done via **(stochastic) gradient descent**
- For classification, **softmax + cross-entropy** form a probabilistically grounded output layer
- Strong connections exist between machine learning and physics (e.g., Boltzmann distribution ↔ softmax)
---
# Session 10: Neural Networks II  
**AI-Driven High Energy Physics (HEP)**  
*S. A. Fard – School of Physics (IPM)*

## References
1. Bishop, Christopher M., and Hugh Bishop. *Deep Learning: Foundations and Concepts*. Springer Nature, 2023.  
2. [Optimizing Gradient Descent – Sebastian Ruder](https://www.ruder.io/optimizing-gradient-descent/)

---

## Extensions to Neural Networks

Neural networks can map:
- Inputs of shape $(n, k)$ → Outputs of shape $(n, 1)$ (e.g., regression)
- Or $(n, k)$ → $(n, k')$ (e.g., multi-output regression or classification)

> **Note**: Here, $n$ is the batch size (number of samples), and $k$, $k'$ are input/output feature dimensions.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/extension_to_nn.png?raw=true" alt="extension to nn" width="600"/>
</center>
---

## Deep Neural Networks (Deep Learning)

- **Deep NNs** stack many layers between input and output.
- Each layer transforms the representation, enabling learning of **hierarchical features**.
- Data flows **forward** through the network: this is called a **feedforward architecture**.

> **Key idea**: Depth allows the network to automatically **extract features** from raw inputs—critical when inputs have complex structure (e.g., images, particle jets, time series).


---

## Fundamental Computational Unit: The Neuron

A single neuron computes:
$$
H = A(\mathbf{a}^\top \mathbf{X} + b)
$$

Where:
- $\mathbf{X} \in \mathbb{R}^m$: input vector ($x_1, x_2, \dots, x_m$)
- $\mathbf{a} \in \mathbb{R}^m$: weight vector ($a_1, a_2, \dots, a_m$)
- $b \in \mathbb{R}$: bias term
- $A(\cdot)$: activation function (e.g., ReLU, sigmoid)

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/single_neuron.png?raw=true" alt="Structure of single Neuron" width="600"/>
</center>

This is the core building block of all feedforward networks.

A common classroom example is the **Fourier transform**, which demonstrates that any function can be expanded in terms of **sine** and **cosine** basis functions. In this analogy, the sine and cosine functions serve as activation functions. The equation above performs essentially the same operation—it decomposes functions using a set of basis functions, similar to how Fourier analysis expands signals into sinusoidal components.

---

## Optimization: Backpropagation

- **Forward pass**: Compute predictions by propagating input through layers.
- **Backward pass**: Use **error backpropagation** to compute gradients of the loss w.r.t. all parameters.
  - Information flows **backward** from output to input.
  - Enables efficient gradient computation via the chain rule.

Parameter update (e.g., via SGD):
$$
\mathbf{a}_{\text{new}} = \mathbf{a}_{\text{old}} - \eta \nabla_{\mathbf{a}} \mathcal{L}
$$

Regularized loss example:
$$
\mathcal{L} \sim \sum \left[\tilde{y} - f(\mathbf{x}; \mathbf{a})\right]^2 + \lambda \|\mathbf{a}\|^2
$$
> This is **ridge (L2) regularization**, which penalizes large weights to reduce overfitting.

<center>
  <img src="https://github.com/Shayan-Zavvarei/AI-Driven-High-Energy-Physics/blob/main/photos/nn_comp_unit.png?raw=true" alt="NN fundumental computation uni" width="600"/>
</center>
---

## Optimization Algorithms: Two Main Approaches

### 1. **Search-Based Methods**
- Explore the loss landscape **without derivatives** (e.g., genetic algorithms, random search).
- Useful when the function is non-differentiable or noisy.
- Generally slower and less efficient for smooth, high-dimensional problems.

### 2. **Gradient-Based Methods**
- Use derivative information to move **opposite the gradient** (direction of steepest ascent).
- Update rule (1D example):
  $$
  a_{\text{new}} = a_{\text{old}} - \eta f'(a_{\text{old}})
  $$
- Justified by Taylor expansion:

$[
f(a_{new}) = f(a_{old}) + f'(a_{old})(a_{new} - a_{old}) + \frac{1}{2}f''(a_{old})(a_{new} - a_{old})^2
]$

$[
f(a_{new}) - f(a_{old}) \leq \eta(f'(a_{old}))^2\left(\frac{\eta}{2}f'(a_{old}) - 1\right)
]$

- **Requirement**: The loss must be differentiable (or sub-differentiable).

> **Note**: Nearly all modern deep learning relies on gradient-based optimization due to its scalability and efficiency.

---

## Automatic Differentiation in PyTorch

- PyTorch provides **Autograd**, an automatic differentiation engine.
- Tracks operations on tensors with `requires_grad=True`.
- Computes gradients via `.backward()`.

> **Typical workflow**:
> 1. Define model and loss
> 2. Forward pass → compute loss
> 3. Call `loss.backward()` → computes gradients
> 4. Update parameters manually or via optimizer (e.g., `torch.optim.Adam`)

> **Why it matters**: Autograd eliminates the need to derive and code gradients by hand—essential for complex models.

---

## Simple Neural Network in PyTorch

While the slide only shows placeholder visuals, a minimal PyTorch NN typically includes:
- `torch.nn.Module` subclass
- Layer definitions (e.g., `nn.Linear`)
- Forward method
- Loss function and optimizer

> Example concepts illustrated in class likely include:
> - Building a 1- or 2-hidden-layer network
> - Training loop with forward/backward passes
> - Using `torch.autograd` for gradient computation

---
## Derivative in pytorch
```python
x = torch.tensor(2.0, requires_grad=True)
y = (x ** 2 + 3* x + 1)
y.backward()
print(x.grad)
```
### General form of the derivatuion in PyTorch 
```python
def forward(x1,x2):
  return x1 * x2 + x2

def compute_gradiants(x1_value, x2_value):
  x1 = torch.tensor(x1_value, requires_grad=True)
  x2 = torch.tensor(x2_value, requires_grad=True)

  # --- Forward : z = x1 *x2 + x2
  z = forward(x1,x2)

  # Backward : Compute gradiants
  z.backward()
```


## Simple NN in PyTorch 
```python
class SimpleNN(nn.Module):
  def __init__(self, input_size, hidden_size, output_size):
    super(simpleNN, self).__init__()
    self.hidden = nn.Linear(input_size, hidden_size)
    self.relu = nn.ReLU()
    self.output = nn.Linear(hidden_size, output_size)

  def forward(self, x):
    x = self.hidden(x)
    x = self.relu(x)
    x = self.output(x)
    return x

model = simpleNN(input_size = 2, hidden_size = 4, output_size = 2)
criterion = nn.MSELoss()
optimizer = optim.SGD(model.parameters(), lr= 0.1)
#above, lr stands for Learning Rate

x = torch.tensor([[1.0, 2.0], [2.0,3.0], [3.0,4.0]], requires_grad = False)
y = torch.tensor([[3.0,4.0], [5.0,6.0], [7.0,8.0]])

# Now we begin the learning loop
for epoch in range (1000):
  # Forward pass 
  y_pred = model(x)
  loss = criterion(y_pred, y)

  # Backward pass
  optimizer.zero_grad()
  loss.backward()
  optimizer.step()

# --- Fix the weights and biased ---
with totch.no_grad():

  model.hidden.weight.copy_(torch.tensor([[0.1,0.2].[0.3,0.4],[0.5,0.6],[0.7,0.8]]))
  
  # Output layer
  model.output.weight.copy_(torch.tensor([0.2,0.3,0.4,0.5], [0.5,0.4,0.3,0.2]))
  model.output.bias.copy_(torch.tensor([0.1, -0.1]))

x = torch.tensor([[1.0,2.0], [2.0,3.0],[3.0,4.0]]), requires_grad = True)

# --- Forward pass ---
y = model(x)

# --- Backward pass ---
grad_outputs = torch.tensor([[1.0, 0.0], [0.0,0.1], [1.0,1.0]], dtype = torch.float32)

# --- Compute gradiants of y with respect to x 
gradiants = torch.autograd.grad(outputs = y, inputs = x, grad_outputs = grad_outputs)
```
## Summary

- **Deep neural networks** generalize shallow models by stacking layers to learn rich representations.
- The **neuron** is a linear transformation + nonlinear activation.
- **Backpropagation** efficiently computes gradients for millions of parameters.
- **Optimization** relies on gradient-based methods, enabled by frameworks like **PyTorch Autograd**.
- This foundation supports applications in HEP—from jet tagging to simulation-based inference.