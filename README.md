# Finance HPC Lab

This repository contains materials for the **Finance HPC Lab**, including a tutorial and a lab exercise focused on performance computing in finance using **R** and **Python**.

## 📂 Project Structure
```
├── README.md             # This file - setup and instructions
├── lab01-hpc.Rproj       # RStudio project file
├── lab01.qmd             # Lab Exercise: Monte Carlo Simulation in R
├── setup.R               # R dependency installer
├── tutorial01.qmd        # Tutorial: Performance Computing in Finance
```

## 🚀 Quick Setup Guide

### **1. Clone the Repository in Posit IDE**
1. **Open Posit IDE (RStudio).**
2. Go to **File > New Project > Version Control > Git**.
3. Enter the repository URL:
   ```
   https://github.com/YOUR-USERNAME/finance-hpc-lab.git
   ```
4. Click **Create Project**.

### **2. Set Up the Conda Environment**
1. Open the built-in **Terminal** in Posit IDE.
2. Run the following commands:
   ```sh
   conda env create -f environment.yml
   conda activate finance_hpc_lab
   ```

### **3. Configure Python in Posit IDE**
1. Go to **Tools > Global Options > Python**.
2. Select **Use Conda Environment:** `finance_hpc_lab`.
3. Click **Apply**.

### **4. Install R Dependencies**
In R Console, run:
```r
source("setup.R")
```

---

## 📖 Tutorial: Performance Computing in Finance (`tutorial01.qmd`)
- Introduces **Monte Carlo simulation** in Python.
- Covers performance optimization techniques in Python (NumPy, Numba).
- Explains how **R and Python interact** using `reticulate`.

To run the tutorial:
1. Open `tutorial01.qmd` in Posit IDE.
2. Click **"Render"** to generate the output.

---

## 🏆 Lab Exercise: Monte Carlo Simulation in R (`lab01.qmd`)
- Students **implement a Monte Carlo simulation in R**.
- Compare performance with Python implementations.
- Submit their findings.

To complete the lab:
1. Open `lab01.qmd` in Posit IDE.
2. Implement the R Monte Carlo simulator.
3. Compare execution time with Python.
4. Summarize findings at the end of the document.
5. Submit your completed `lab01.qmd`.

---

## 🛠️ Troubleshooting
- If `conda` is not recognized, restart Posit IDE and try again.
- If dependencies fail, manually install in R:
  ```r
  install.packages("tidyverse")
  ```
- If Quarto does not work, install via Conda:
  ```sh
  conda install -c conda-forge quarto
  ```

