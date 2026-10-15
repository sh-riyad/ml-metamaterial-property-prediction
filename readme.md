# A Machine-Learning-Based Approach to Expedite Predicting Effective Metamaterial Properties for Electromagnetic Transmission Control

Undergraduate thesis, Department of Computer Science & Engineering, International Islamic University Chittagong (IIUC)

## Reports

- Thesis book: [docs/undergraduate_thesis.pdf](docs/undergraduate_thesis.pdf)
- Short report (IEEE format): [docs/short_report.pdf](docs/short_report.pdf)
- Dataset (CSV): [Kaggle](https://www.kaggle.com/datasets/a4b5c603f9d4023b9ec9ab443860386304f38e3112758ffd0cf1cf1bdaddb580?select=simulation_parameters.csv)

## Team

**Submitted by**<br>
Sarawar Hossain (C211068)<br>
Md. Tasbiul Karim Tahsin (C211078)<br>
Yakub Ali (C211079)

**Supervised by**<br>
Prof. Mohammed Shamsul Alam<br>
Professor<br>
Dept. of Computer Science & Engineering<br>
International Islamic University Chittagong

**Co-Supervised by**<br>
Dr. Touhidul Alam<br>
Research Fellow<br>
Universiti Kebangsaan Malaysia


Thesis exam date: 26 October 2025

## About the Research

Metamaterials are engineered structures that can manipulate electromagnetic (EM) waves in unconventional ways, with applications in EM shielding, cloaking and wave absorption. Designing them is usually slow, because it depends on repeated, computationally heavy simulations.

This thesis presents a machine learning framework that speeds up the prediction and design of metamaterials with desired EM properties. A deep learning model is trained to map geometric and material parameters to EM characteristics such as permittivity, permeability and scattering parameters. For this, we generated a dataset of more than 1,100 simulated metamaterial samples in CST Studio Suite over the 20-32 GHz range, using an automated Python interface. We also built a backward prediction model, a custom artificial neural network (ANN), that generates metamaterial designs from a target frequency response.

The approach reduces design time while keeping prediction accuracy high, and shows the potential of ML-driven metamaterial design for 5G and radar applications.

For the full method, dataset and results, see the thesis book and the short report above.

## About this Repository

This repository was mainly created to customize an existing CST Python API for our needs and to automate the simulation process: creating a design, running the simulation, extracting the results and storing them in a database. The output files are stored here together with their data. The ML model trained on this data is in the `notebooks` folder.

## Folder Structure

- `cst_python_api/`: the existing CST Python API, modified to fit our needs
- `examples/`: small examples to check how the API is used
- `simulations/main.py`: main script. It opens CST, creates a design, runs the simulation with the selected parameters, extracts the important results, pre-processes them and saves them to the database
- `output/`: saved output files
- `notebooks/initial_model.ipynb`: the machine learning model trained on our data
- `docs/undergraduate_thesis.pdf`: thesis book
- `docs/short_report.pdf`: short report
- `Database.py`: creates the database schema and the database
- `simulation.db`: the database with the simulation data
- `setup.py`: one-time setup to install dependencies
- `requirements.txt`: Python dependencies

## Setup

Requires Python and, to re-run the simulations, CST Studio Suite with a valid license. The ML notebook does not need CST: download the dataset from Kaggle and open the notebook.

```bash
git clone https://github.com/sh-riyad/ml-metamaterial-property-prediction.git
cd ml-metamaterial-property-prediction
pip install -r requirements.txt
python setup.py
python simulations/main.py
```

## Repository Status

The thesis work and code were completed before the thesis exam on 26 October 2025. The repository was last updated on 16 October 2026, only to organize the folder structure and add the thesis book, short report and documentation for showcase. No simulation, database or model code was changed in this update.
