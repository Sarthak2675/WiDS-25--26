# Bridging Language and Personalization
This repository contains all the resources for WiDS'25-'26.

Below guide details how to set up an environment on Windows using the **Anaconda Prompt**.
Install the suitable anaconda distribution available for your system at https://www.anaconda.com/download

### **Step 1: Open Anaconda Prompt**
1.  Search for **"Anaconda Prompt"**.
2.  Right-click it and select **"Run as Administrator"** (recommended to avoid permission issues).

### **Step 2: Create the Virtual Environment**
We will use **Python 3.10**, which is currently the most stable version for the latest PyTorch and Transformers libraries (Python 3.11/3.12 can sometimes cause compatibility issues with specific CUDA builds).

Run the following command to create an environment named "bert_wids":

```bash
conda create -n bert_wids python=3.10
```

*Type `y` and press Enter when prompted to proceed.*

Once created, activate the environment using the command:

```bash
conda activate bert_wids
```

Please note that all the work for you project should be done in this environment only so whenever you have to execute any code you will have to activate the environment using above command.

### **Step 3: Install PyTorch with CUDA (GPU Support)**
This is the most critical step. We will install PyTorch along with the CUDA toolkit.
*Note: This assumes you have an NVIDIA GPU. If you do not, this command will still work but will default to CPU mode, or you can remove `pytorch-cuda`.*
Run this single command to install PyTorch, TorchVision, and the CUDA 12.4 toolkit:
```bash
conda install pytorch pytorch-cuda=12.4 -c pytorch -c nvidia
```

  * `-c pytorch -c nvidia` tells conda to pull specifically from the official PyTorch and NVIDIA channels to ensure you get the correct GPU-enabled versions.


### **Step 4: Install Transformers**
Now we install the libraries for BERT (`transformers`) and standard data tools (`numpy`, `pandas`, `matplotlib`, `scikit-learn`).
Run this command:

```bash
conda install -c conda-forge transformers numpy pandas matplotlib scikit-learn jupyter notebook
```

### **Summary of Commands**
Here is the complete sequence for your reference:

```bash
conda create -n bert_wids python=3.10
conda activate bert_wids
conda install pytorch torchvision torchaudio pytorch-cuda=12.4 -c pytorch -c nvidia
conda install -c conda-forge transformers gensim numpy pandas matplotlib scikit-learn jupyter notebook
```
