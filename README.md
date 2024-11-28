# Irchel Geoparser Workshop

This repository contains materials for the Irchel Geoparser workshop.

For more information about the **Irchel Geoparser**, visit the project website: [geoparser.app](https://docs.geoparser.app/)

---

## Setup Instructions

Please follow the instructions below to set up your environment for the workshop.

### 1. Python Installation

#### Check if Python is Installed

First, verify that you have Python installed on your system. Open a terminal (Command Prompt, PowerShell, Terminal, etc.) and run:

- **Windows:**

  ```cmd
  python --version
  ```

- **macOS/Linux:**

  ```bash
  python3 --version
  ```

This command should output the version of Python installed. For this workshop, you need Python **3.9** or higher but not higher than **3.12**.

**Important:** We recommend having Python installed directly on your system, rather than using Anaconda or other virtual environments. This will ensure compatibility with the workshop instructions and make it easier for us to assist you in case of any issues.

#### Install Python (If Needed)

1. Go to the [Python Downloads](https://www.python.org/downloads/) page.
2. Download the latest supported version (up to Python 3.12).
   - **Do not** download versions higher than 3.12, as they are not supported yet.
3. Run the installer:
   - **Windows Users:**
     - During installation, make sure to check the box that says **"Add Python to PATH"**.
   - **macOS/Linux Users:**
     - Follow the standard installation procedure for your system.

After installation, verify the installation:

- **Windows:**

  ```cmd
  python --version
  ```

- **macOS/Linux:**

  ```bash
  python3 --version
  ```

You should see the installed Python version in the output.

### 2. Set Up the Workshop Directory

Create a directory for the workshop files and navigate to it.

#### Create a Folder

- **Windows (Command Prompt):**

  Open **Command Prompt** and run:

  ```cmd
  mkdir %USERPROFILE%\geoparser-workshop
  ```
  
  ```cmd
  cd %USERPROFILE%\geoparser-workshop
  ```

- **Windows (PowerShell):**

  Open **PowerShell** and run:

  ```powershell
  mkdir $Env:UserProfile\geoparser-workshop
  ```
  
  ```powershell
  cd $Env:UserProfile\geoparser-workshop
  ```

- **macOS/Linux (Terminal):**

  Open **Terminal** and run:

  ```bash
  mkdir ~/geoparser-workshop
  ```
  
  ```bash
  cd ~/geoparser-workshop
  ```

### 3. Create and Activate a Virtual Environment

We'll create a virtual environment to isolate the workshop's dependencies and avoid conflicts with other installations on your system.

#### Create the Virtual Environment

- **Windows:**

  ```cmd
  python -m venv geoparser-env
  ```

- **macOS/Linux:**

  ```bash
  python3 -m venv geoparser-env
  ```

This command creates a virtual environment named `geoparser-env` in your current directory (`geoparser-workshop`).

#### Activate the Virtual Environment

- **Windows:**

  ```cmd
  geoparser-env\Scripts\activate
  ```

- **macOS/Linux:**

  ```bash
  source geoparser-env/bin/activate
  ```

You should now see `(geoparser-env)` at the beginning of your command prompt, indicating that the virtual environment is active.

### 4. Install Required Packages

With the virtual environment activated, you can now install the necessary Python packages.

#### Install Geoparser

```bash
pip install geoparser
```

Verify the installation and version:

```bash
pip show geoparser
```

Ensure that the version of `geoparser` is **0.2.0**. If an older version is installed or you encounter issues, please reach out to us.

#### Install Jupyter and Folium

We will use Jupyter for running the notebooks and Folium for mapping:

```bash
pip install jupyter folium
```

Even if you have Jupyter installed elsewhere, it's important to install it in this virtual environment.

### 5. Install spaCy Models

In the tutorial, we will use two spaCy models for English texts.

1. Install the small model:
   ```bash
   python -m spacy download en_core_web_sm
   ```

2. Install the transformer-based model:
   ```bash
   python -m spacy download en_core_web_trf
   ```

### 6. Set Up the Gazetteer

For this workshop, we'll use the GeoNames gazetteer:

```bash
python -m geoparser download geonames
```

**Note:** The last step of the setup process involves some database operations that are not reflected using progress bars but are still executing in the background. It may appear that the setup is stuck, but it isn't. Please wait until you see:

```
Database setup complete.
```

### 7. Download Workshop Materials

Download the following files from this repository and save them in your `geoparser-workshop` directory:

1. Tutorial Notebooks:
  - `01_Geoparser_Basics.ipynb`
  - `02_Geoparser_FineTuning.ipynb`

2. Annotation Data:
- `training_annotations_incomplete.json`
- `test_annotations.json`

### 8. Launch Jupyter Lab

With all the files in place and the virtual environment still active, launch Jupyter Lab (still within the same `geoparser-workshop` directory):

```bash
jupyter lab
```

This will open Jupyter Lab in your default web browser, showing the contents of your `geoparser-workshop` directory.

You are now ready to start the workshop!

---

## Data Source

During this workshop we will use data from **GeoCorpora** for training and testing models:

Wallgrün, J. O., Karimzadeh, M., MacEachren, A. M., & Pezanowski, S. (2017). GeoCorpora: building a corpus to test and train microblog geoparsers. *International Journal of Geographical Information Science*, 32(1), 1–29. https://doi.org/10.1080/13658816.2017.1368523
