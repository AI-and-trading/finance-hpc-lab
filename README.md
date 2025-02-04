# Finance HPC Lab

This repository contains materials for the **Finance HPC Lab**, including a tutorial and a lab exercise focused on performance computing in finance using **R** and **Python** within **Quarto documents**.

## 📂 Project Structure
```
├── README.md             # This file - setup and instructions
├── lab01-hpc.Rproj       # RStudio project file
├── lab01.qmd             # Lab Exercise: Monte Carlo Simulation in R
├── setup.R               # R dependency installer
├── tutorial01.qmd        # Tutorial: Performance Computing in Finance
├── environment.yml       # Conda environment file
```

## 🚀 Quick Setup Guide

### **1. Clone the Repository in Posit IDE**
1. **Open Posit IDE (RStudio).**
2. Go to **File > New Project > Version Control > Git**.
3. Enter the repository URL:

```
https://github.com/AI-and-trading/finance-hpc-lab.git
```
4. Click **Create Project**.

### **2. Set Up the Conda Environment for Python**
Since **Quarto supports both R and Python**, we will use **Conda only for Python dependencies**, while R will be managed system-wide.

1. Install **Miniconda** (if not already installed).
2. Run the following command to create the environment:
```sh
 conda env create -f environment.yml
 conda activate finance_hpc_lab
 ```

### **3. Configure Reticulate in R**
Ensure **reticulate** is set to use the Conda Python environment by adding the following to your `.Rprofile` file:

```r
library(reticulate)
use_condaenv("finance_hpc_lab", required = TRUE)
```

### **4. Install Quarto in R**
If Quarto is not already installed, run:
```r
install.packages("quarto")
```

---

## 📖 Tutorial: Performance Computing in Finance (`tutorial01.qmd`)
- Introduces **Monte Carlo simulation** in Python.
- Covers performance optimization techniques in Python (NumPy, Numba).
- Explains how **R and Python interact** using `reticulate` within Quarto.

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
- **If `conda` is not recognized**, restart Posit IDE and try again.
- **If dependencies fail, manually install in R**:
  ```r
  install.packages("tidyverse")
  ```
- **If Quarto does not work, install via Conda**:
  ```sh
  conda install -c conda-forge quarto
  ```

## 🔧 Fixing Conda Not Recognized in Posit IDE

Some students may encounter an issue where **Conda is available in their system terminal** but **not recognized inside Posit IDE (RStudio).** This is due to the fact that Posit IDE does not always inherit the same shell environment as the system terminal.

Follow these steps to resolve the issue.

---

## **✅ Step 1: Check if Conda is Installed and Available in the System Terminal**
### **1. Open a Terminal (Outside of Posit IDE)**
- **Windows:** Open **Command Prompt** (cmd) or **PowerShell**.
- **Mac/Linux:** Open **Terminal**.

### **2. Run the Following Command**
```sh
conda --version
```
If Conda is installed, you should see an output similar to:
```
conda 23.x.x
```
If **you see an error**, Conda is not installed or not properly set up. Install **Miniconda** from [here](https://docs.conda.io/en/latest/miniconda.html) and try again.

---

## **✅ Step 2: Check if Conda is Available in Posit IDE’s Terminal**
1. Open **Posit IDE (RStudio)**.
2. Go to **Tools > Terminal > New Terminal**.
3. Run:
 ```sh
 conda --version
 ```
4. If you get an error like `command not found`, continue to Step 3.

---

## **✅ Step 3: Find Conda’s Installation Path**
Go back to your **system terminal** and run:
```sh
command -v conda  # macOS/Linux
where conda        # Windows
```
This should return the path where Conda is installed. For example:
- **Mac/Linux:** `/Users/yourname/miniconda3/bin/conda`
- **Windows:** `C:\Users\yourname\miniconda3\Scripts\conda.exe`

If this command **does not return a path**, Conda is not installed correctly. Reinstall **Miniconda**.

---

## **✅ Step 4: Add Conda to the PATH in Posit IDE**
If Conda is installed but not recognized in Posit IDE, manually add it to the environment.

### **Mac/Linux Users**
1. Open a terminal (outside Posit IDE) and edit your shell profile:
 ```sh
 nano ~/.bashrc   # If using Bash (is the default for Posit IDE on all operating systems)
 nano ~/.zshrc    # If using Zsh (default on macOS)
   ```
2. Add the following line at the end (replace with your actual Conda path):
 ```sh
 export PATH="/Users/yourname/miniconda3/bin:$PATH"
 ```
3. Save and exit (`Ctrl + X`, then `Y`, then `Enter`).
4. Apply the changes:
 ```sh
 source ~/.bashrc  # or source ~/.zshrc for Zsh
 ```
5. Restart **Posit IDE** and check if Conda is now recognized in the terminal:
 ```sh
 conda --version
 ```

---

### **Windows Users**
1. Open **PowerShell (not Posit IDE)** and run:
 ```powershell
 [System.Environment]::SetEnvironmentVariable("Path", "$env:Path;C:\Users\yourname\miniconda3\Scripts", "User")
 ```
2. Restart your computer.
3. Open **Posit IDE**, go to **Tools > Terminal > New Terminal**, and check if Conda is recognized:
 ```sh
 conda --version
 ```

---

## **✅ Step 5: Force Posit IDE to Use the Correct Shell**
If Conda is still not recognized in Posit IDE:
1. Open **Posit IDE**.
2. Go to **Tools > Global Options > Terminal**.
3. Under **New Terminals open with:**, select **Custom** and enter:
 ```sh
 /bin/bash --login
 ```
4. Click **Apply** and restart Posit IDE.
5. Open a new terminal inside Posit IDE and test:
 ```sh
 conda --version
 ```

---

## **✅ Step 6: Manually Activate Conda in Posit IDE**
If none of the above solutions work, manually activate Conda every time you open a terminal in Posit IDE:
- **Mac/Linux:**
```sh
/Users/yourname/miniconda3/bin/conda activate finance_hpc_lab
```
- **Windows:**
```sh
C:\Users\yourname\miniconda3\Scripts\conda.exe activate finance_hpc_lab
```

---

## **🎯 Final Check**
After applying the fixes, test the following in **Posit IDE’s terminal**:
```sh
conda --version
which conda   # macOS/Linux
where conda   # Windows
conda info | grep 'base environment'
```
If these return expected results, Conda is correctly set up! 🚀

---

## **💡 Summary of Fixes**
| **Issue**  | **Solution**  |
|--------------|----------------|
| Conda is installed but not found in Posit IDE | Add Conda to PATH in `.bashrc`, `.zshrc`, or Windows PATH settings |
| Conda is available in system terminal but not Posit IDE | Change Posit IDE’s shell to **`/bin/bash --login`** |
| Conda is not found at all | Reinstall **Miniconda** and restart your computer |
| Conda is still not working | Manually activate Conda in every Posit IDE session |

Following these steps should resolve Conda recognition issues inside Posit IDE. If you continue to have issues, reach out for **support via Canvas Discussions or office hours**! 🚀
