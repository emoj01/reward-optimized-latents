# Reward-Optimized Latents

This repository contains the code and experimental work for our team project in **Deep Reinforcement Learning**.

## Project Goal

This project investigates task-specific latent representations for reinforcement learning world models, building on World Models by Ha and Schmidhuber and Learning to Reinforcement Learn by Wang et al.

In the original World Models architecture, a Variational Autoencoder (VAE) learns a compressed representation of visual observations by optimizing a reconstruction objective. However, information that is important for reconstructing an observation is not necessarily relevant for the agent's task. For example, background textures or wall patterns may contribute to reconstruction quality without providing useful information for decision-making.

Our goal is to investigate whether latent representations optimized for task-relevant rewards and predictive dynamics can improve the effectiveness of world models.

We plan to explore the following architectural modifications:

- **Task-specific encoder**: Integrate recurrent processing into the encoder to incorporate temporal information and encourage representations that are useful for the agent's task.
- **Alternative dynamics model**: Investigate whether the recurrent dynamics model (MDN-RNN) can be simplified or replaced with an MLP, potentially with probabilistic outputs, when temporal information is already captured by the encoder.
- **Empirical evaluation**: Compare the modified architecture against a baseline to understand the effects on representation quality, predictive performance, and agent reward.

These modifications are research hypotheses and may evolve as the project progresses.

## Literature
Ha, D. and Schmidhuber, J. (2018). World Models.<br>
Wang, J. X. et al. (2017). Learning to Reinforcement Learn. Paper.

Additional references will be added as the project progresses.
___

## Repository Structure
reward-optimized-latents/<br>
├── notebooks/<br>
├── src/<br>
├── external/<br>
├── models/<br>
├── data/<br>
├── requirements.txt<br>
├── .gitignore<br>
└── README.md<br>

## Folder Descriptions
- **notebooks/** – Jupyter or Colab notebooks for exploratory analysis, experiments, and visualization.
- **src/** – Source code for model implementations, training, evaluation, and utility functions.
- **external/** – External repositories or reference implementations, kept separate from our own code.
- **models/** – Optional local storage for trained model weights and checkpoints. Large files should generally remain outside Git version control.
- **data/** – Dataset references or small sample files. Large datasets should not be committed directly.
- **requirements.txt** – Python dependencies required to run the project.
- **.gitignore** – Specifies generated files, caches, local environments, and other files that Git should ignore.

## Usage

Clone the repository:

git clone https://github.com/<username>/reward-optimized-latents.git
cd reward-optimized-latents


If external repositories are added as Git submodules, initialize them with:

git submodule update --init --recursive


Setup and experiment instructions will be added as the implementation develops.

## Collaboration

For team workflows and collaboration guidelines, see TEAM_GUIDE.md.

## Contributors
Emil Ojo<br>