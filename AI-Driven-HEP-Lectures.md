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
