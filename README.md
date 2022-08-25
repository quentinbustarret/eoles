# Eoles

Eoles model performs optimization of the investment and operation of the energy system in order to minimize the total cost while satisfying energy demand. \
Here is a presentation of a slightly earlier version of the model: _http://www.centre-cired.fr/quel-mix-electrique-optimal-en-france-en-2050/_ \
This Gitlab is the python translation of the Eoles_elec_pro model originally in GAMS.
You can find it here : _https://github.com/BehrangShirizadeh/EOLES_elec_pro_

---

### Launching the model with Pyomo

---

#### **Installing the dependencies**

In order to run the model you will need to install some dependencies that this program needs to run:

* **Python** :
Python is an interpreted programming language, with Pyomo it will allow us to model Eoles. \
You can download the latest version on the dedicated website : *https://www.python.org/downloads/* \
Then you just have to install it on your computer. \
If you plan to install Conda or if you have Conda installed on your computer, 
Python is likely to be already installed.

* **Conda** ou **Pip** depending on your preference:
Conda and Pip are package managers for Python.
    * **Conda** \
    You can find all the information you need to download and install Conda here:  \
    _https://docs.conda.io/projects/conda/en/latest/user-guide/install/_ \
    __Be careful to choose the version of conda according to the version of Python !!!__ \
    You can install Miniconda which is a minimal version of conda, \
  this allows you to not install all the packages included in conda,
  but you can install only those that you want.
    * **Pip** \
    You can find all the necessary information to download and install pip here: \
    _https://pip.pypa.io/en/stable/installing/_ \
    Pip is installed by default with Conda.

* **Pandas** :
Pandas is a Python library that allows you to manipulate and analyze data easily. \
Pandas is open-source. \
Open a command line and type this to install pandas: \
```conda install pandas```, with Conda \
```pip install pandas```, with Pip \
You can find more information here: _https://pandas.pydata.org/pandas-docs/stable/getting_started/install.html_

* **Pyomo** :
Pyomo is an optimization modeling language based on the Python language. \
Pyomo is open-source.\
Open a command interface and type this to install pyomo : \
```conda install -c conda-forge pyomo```, with Conda \
```pip install pyomo```, with Pip \
You can find more information here: _https://pyomo.readthedocs.io/en/stable/installation.html_

* **Solver** :
The solver that this model uses is the Cbc or _COIN-OR Branch and Cut solver_. \
This solver is open-source. \
We find out that the Gurobi solver is faster than Cbc but Gurobi is not open-source. \
More information about Gurobi here : _https://www.gurobi.com/_ \
You can also use another solver if you wish. \
To download Cbc :
    * Under Linux, CBC is available in the package `coinor-cbc` for Debian or Linux
    or in the coin-or-Cbc package for Fedora distributions.
    * Under Windows, the executable is already included in the GitLab, but you can always download it here : \
    _https://www.coin-or.org/download/binary/CoinAll/_
    * For OS X systems, you can install it with Homebrew : \
    `brew tap coin-or-tools/coinor` \
    `brew install cbc`
    * All information about the Cbc solver is here : \
_https://projects.coin-or.org/Cbc_


#### **How to get the code :**

If you don't have git installed on your computer, you can download the folder on this GitLab. \
Else, you can retrieve the files from this GitLab through the command line : \
``git clone https://gitlab.in2p3.fr/nilam.de_oliveira-gill/eoles`` \
A folder will be created in the current directory with all the files contained in this GitLab.

#### **How to launch the model :**

Continue through a command interface, move to the downloaded directory \
``cd eoles-master`` \
*cd means change directory, it allows you to move in your folders through the command line* \
Then you can solve the model using the command : \
``pyomo solve Eoles_elec_vf.py --solver=cbc.exe`` \
Note that on Windows, the command may only work in an Anaconda Prompt.


---

### Input files

---

You can see the input data in the **inputs** folder.
To modify them, be careful to respect the data format: \
Remember to match the names of the technologies with those in the .py file. \
Case is important, i.e. variables in lower case must remain in lower case and *vice versa*. \
Otherwise it could cause errors and the program could not run. \
For numbers, be careful to separate the integer part from the decimal part with a period and not a comma. \
This could also cause errors.
You can find more information about input data in the file __inputs.txt__.

---

### Output files

---

The program outputs 4 files:  \
**Summary**: This is a small summary of the program, it contains the final objective (the cost) but also other information such as the load curtailment or the storage losses. \
**Hourly Generation**: Contains the hourly generation for each technology as well as other information hour by hour. \
**Elec_Balance**: Contains the electrical balance. That is the generation and the consumption of the model's results. \
**Capacities**: Contains the energy and power capacities for each technology in the model. \
For a better display on Excel, you can do : \
Select column A > Go to the menu: Data > Convert > Select Delimited > Next > Check the box : comma > Finish.

---

### Other

---

If you have any question about the program or the installation you can ask it through an email to : \
_nilam.deoliveiragill@gmail.com_
