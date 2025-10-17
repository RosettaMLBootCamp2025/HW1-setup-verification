# HW1: Environment Setup & GitHub Basics

**Due Date:** [Instructor will specify]

## Overview

This assignment ensures you have properly set up your development environment and can use GitHub for version control. By completing this assignment, you will:

1. Install Anaconda (if not already installed)
2. Create a conda environment with all required packages for the bootcamp
3. Verify your installation with a Python script
4. Create a GitHub repository and commit your verification results

## Prerequisites

- A GitHub account
- Basic command line familiarity
- Git installed on your computer

## Instructions

### Step 1: Install Anaconda

If you don't already have Anaconda installed, download and install it from:
https://www.anaconda.com/download

Verify installation by running:
```bash
conda --version
```

### Step 2: Configure the RosettaCommons Conda Channel

PyRosetta requires a special conda channel. Add it to your conda configuration:

```bash
conda config --add channels https://conda.rosettacommons.org
conda config --add channels conda-forge
```

Alternatively, you can manually edit your `~/.condarc` file to include:
```yaml
channels:
  - https://conda.rosettacommons.org
  - conda-forge
  - defaults
```

### Step 3: Create the Conda Environment

In the directory containing this README, run:

```bash
conda env create -f environment.yml
```

This will create an environment named `bootcamp2025_HW1` with all required packages:
- Python 3.11
- PyRosetta (for protein structure manipulation)
- NumPy (numerical computing)
- Pandas (data analysis)
- Matplotlib & Seaborn (visualization)
- Jupyter (interactive notebooks)
- SciPy (scientific computing)
- scikit-learn (machine learning)
- Biopython (bioinformatics tools)

### Step 4: Activate the Environment

```bash
conda activate bootcamp2025_HW1
```

You should see `(bootcamp2025_HW1)` in your terminal prompt.

### Step 5: Run the Verification Script

```bash
python verify_setup.py
```

This script will:
- Check that all required packages are installed
- Display version information for each package
- Generate a `verification_result.json` file

If all checks pass, you should see:
```
🎉 SUCCESS! All packages are installed correctly!
```

If some checks fail, the script will provide guidance on what went wrong.

### Step 6: Update the Verification File

Open `verification_result.json` in a text editor and replace `"REPLACE_WITH_YOUR_NAME"` with your actual name.

### Step 7: Create Your HW1 Repository on GitHub

1. Go to https://github.com
2. Click the "+" icon in the top right and select "New repository"
3. Name the repository **exactly** `HW1`
4. Make it **private** (or public if you prefer)
5. Do **NOT** initialize with README, .gitignore, or license
6. Click "Create repository"

### Step 8: Initialize Git and Push Your Verification

In the directory containing `verification_result.json`, run:

```bash
# Initialize a git repository
git init

# Add the verification file
git add verification_result.json

# Create your first commit
git commit -m "Add environment verification"

# Add your GitHub repository as the remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/HW1.git

# Push to GitHub
git branch -M main
git push -u origin main
```

**Replace `YOUR_USERNAME` with your actual GitHub username!**

### Step 9: Verify Your Submission

Go to your GitHub repository at `https://github.com/YOUR_USERNAME/HW1` and verify that:
- The `verification_result.json` file is present
- It contains your name (not "REPLACE_WITH_YOUR_NAME")
- The `verification_passed` field is `true`

## Submission

Submit the URL to your HW1 GitHub repository (e.g., `https://github.com/YOUR_USERNAME/HW1`) through the course submission system.

## Troubleshooting

### PyRosetta Installation Issues

If PyRosetta fails to install:
1. Verify the RosettaCommons channel is configured: `conda config --show channels`
2. Try installing PyRosetta separately: `conda install -c https://conda.rosettacommons.org pyrosetta`
3. Check that you're using a compatible Python version (3.11 is specified in environment.yml)

### Import Errors

If packages are installed but imports fail:
1. Make sure you've activated the environment: `conda activate bootcamp2025_HW1`
2. Try reinstalling the problematic package: `conda install --force-reinstall <package-name>`

### Git Issues

If you have trouble with git:
- Make sure git is installed: `git --version`
- Configure your git identity if needed:
  ```bash
  git config --global user.name "Your Name"
  git config --global user.email "your.email@example.com"
  ```

### Authentication with GitHub

If you have trouble pushing to GitHub, you may need to set up authentication:
- Use GitHub's personal access token: https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token
- Or set up SSH keys: https://docs.github.com/en/authentication/connecting-to-github-with-ssh

## Questions?

Contact the instructor or post on the course discussion forum.

## Grading

- [ ] Conda environment created successfully (20%)
- [ ] All packages installed correctly (40%)
- [ ] verification_result.json contains student name (10%)
- [ ] HW1 repository created on GitHub (10%)
- [ ] verification_result.json committed and pushed (20%)

**Total: 100 points**
