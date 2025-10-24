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