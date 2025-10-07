### ⚙️ Installation & Setup for Windows Users
---
- gpaw does not have a valid 25.1.0 release for Windows. One simple and efficient way is using WSL and Ubuntu

```powershell
# powershell terminal
# Install WSL2 with Ubuntu
wsl --install -d Ubuntu-22.04

# Or if WSL is already installed but you want Ubuntu
wsl --install -d Ubuntu-22.04
```

- Good to restart your computer after installation
- It may ask a username and password while installing. While you type your password, nothing will be seen in the terminal even though it accepts your password. Don't worry

```powershell
# Update system
sudo apt update && sudo apt upgrade -y

# Install essential build tools (for compiling if needed)
sudo apt install -y build-essential gfortran

# Install Miniconda
cd ~
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
bash Miniconda3-latest-Linux-x86_64.sh -b -p $HOME/miniconda3

# Initialize conda
~/miniconda3/bin/conda init bash
source ~/.bashrc
```

- Check whether git installed

```powershell
# Check if git is installed
git --version

# If not installed:
sudo apt update
sudo apt install git -y

# Set your name and email
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"

# Check configuration
git config --list
```

- Clone the git

```powershell
# Navigate to where you want to clone
cd ~

# Clone using HTTPS
git clone https://github.com/DennisWayo/Q-UCSpec.git

# Navigate into cloned folder
cd Q-UCSpec
```

- Set the environment

```powershell
conda env create -f env-gpaw-linux.yml
conda activate gpaw-tddft-legacy
```

- Check the environment
```powershell
# Verify installation
python -c "import gpaw, ase, qiskit; print('YES')"

# Test installation
python -c "import gpaw; import ase; import qiskit; print('YES')"
```
