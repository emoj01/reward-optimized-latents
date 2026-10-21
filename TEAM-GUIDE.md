# Team Guide: Reward-Optimized Latents

This guide describes how to collaborate on our Deep Reinforcement Learning project using GitHub, Git, and optionally Google Colab.

## 1. Accessing the Repository
1. Make sure you have access to the GitHub repository. Accept the collaborator invitation if necessary.
2. Clone the repository locally or into your development environment.
git clone https://github.com/<username>/reward-optimized-latents.git
cd reward-optimized-latents


If the repository contains Git submodules, initialize them with:

git submodule update --init --recursive

### Authentication

Use GitHub CLI, SSH, or a credential manager for authentication.

If you work in Google Colab, you can use Colab Secrets to store credentials securely. Never commit access tokens, passwords, or other credentials to the repository, and avoid embedding tokens in repository URLs or notebook cells.

## 2. Repository Structure
reward-optimized-latents/<br>
├── notebooks/       # Exploratory analysis and experiments<br>
├── src/             # Model implementations, training, evaluation<br>
├── external/        # External repositories or reference implementations<br>
├── models/          # Local model checkpoints (not tracked by Git)<br>
├── data/            # Local datasets and generated data (not tracked by Git)<br>
├── requirements.txt # Python dependencies<br>
├── .gitignore<br>
└── README.md<br>


Keep source code separate from exploratory notebooks whenever practical. Large datasets, generated outputs, and model checkpoints should not be committed directly to Git.

## 3. Development Workflow
### Step 1: Synchronize with main

Before starting new work, update your local repository:

git switch main
git pull --ff-only origin main

### Step 2: Create a feature branch

Use a separate branch for each feature, experiment, or architectural modification.

git switch -c feature/<short-description>


Examples:

- feature/task-specific-encoder
- feature/latent-dynamics-predictor
- experiment/reward-optimized-latents
### Step 3: Develop and experiment

Work locally or in Google Colab.

- Implement reusable model and training code in src/.
- Use notebooks/ for exploratory analysis, visualizations, and experiment workflows.
- Keep configurations, random seeds, and evaluation metrics documented.
- Avoid committing temporary files, generated datasets, or large checkpoints.
### Step 4: Commit changes

Make small, focused commits with descriptive messages.

git add <files>
git commit -m "Add task-specific encoder"


Avoid git add . when you have not checked which files have changed. Review the staged changes first:

git status
git diff --cached

### Step 5: Push your branch
git push -u origin HEAD

### Step 6: Open a Pull Request
1. Open GitHub and create a Pull Request from your feature branch into main.
2. Describe the purpose of the change and summarize the implementation.
3. For architectural changes, explain the motivation and relevant assumptions.
4. Include relevant evaluation results when available.
5. Ask a teammate to review the changes before merging.

Discuss merge conflicts with the team and resolve them carefully.

### Step 7: Update your local repository

After your Pull Request has been merged:

git switch main
git pull --ff-only origin main


Delete the feature branch when it is no longer needed.

## 4. Best Practices
- Keep main in a working state.
- Use descriptive branch names and commit messages.
- Keep Pull Requests focused and reviewable.
- Track tasks and open questions using GitHub Issues.
- Document experimental configurations, random seeds, and evaluation metrics.
- Do not commit credentials, large model weights, or generated datasets.
- Coordinate changes to shared notebooks to avoid merge conflicts.
- Record the source and license of external code.
## 5. Experimental Reproducibility

For experiments, document at least:

- Model architecture and relevant modifications
- Training configuration and hyperparameters
- Random seed, where applicable
- Dataset and environment
- Evaluation metrics and results

Keep a clear distinction between the baseline implementation and modified architectures so that experimental comparisons remain interpretable.
___

This workflow helps us collaborate safely, review architectural changes, and keep our experiments reproducible throughout the project.