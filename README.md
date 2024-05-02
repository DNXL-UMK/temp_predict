
# Weather Temperature Prediction using LSTM

[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/) 
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)
[![MIT License](https://img.shields.io/badge/License-MIT-green.svg)](https://choosealicense.com/licenses/mit/)
[![GPLv3 License](https://img.shields.io/badge/License-GPL%20v3-yellow.svg)](https://opensource.org/licenses/)
[![AGPL License](https://img.shields.io/badge/license-AGPL-blue.svg)](http://www.gnu.org/licenses/agpl-3.0)


## Table of Contents

- [Psychic model](#jeli-climate-prediction)
  - [Getting started](#about-the-project)
  - [Installation](#installation)
  - [Roadmap](#usage)
  - [Screenshot](#contributing)
  - [Lessons](#license)
  - [Screenshot](#contributing)
  - [Known Limitation](#license)
  - [Improvement](#contact)
  - [Authoes](#contact)
  - [Acknowledgement](#contact)


## Getting Started

### Introduction
This project is all about building a model that can predict daily mean climate temperatures using Long Short-Term Memory (LSTM) neural networks. The idea is to come up with a tool that can almost accurately forecast the temperature based on stuff like relative humidity, dew point, wind speed, and other weather parameters. For simplicity the prediction model given name is **Psychic** 

Psychic documentation in the notebook comment 🎊

## Installation

1. Clone the repo 

```bash
  git clone https://github.com/DNXL-UMK/temp_predict.git
```
2. Navigate to the project directory
```bash
  cd temp_predict
```
3. Install dependencies [❗ currently the dependencies is based on my entire libraries (including unrelated library to the project like hugging face or transformers), there's known fix but for now ❌]
```bash
  pip install -r requirements.txt
```
4. Open the code in Jupyter Notebook (My environment :Vscode)
```bash
  code Temp_predict_mean_1991_2021.ipynb
```

### Methodology
#### Data Preprocessing
First things first, clean up the data so we can feed it into our model. We then handle missing values, normalize and standardize all the features, and cut up the data into nice 30 rows of sequences that our LSTM network can digest.

After the task is completed, we set climate parameters as our input (features) sequences, and the target parameter is the daily mean temperature for training the psychic model.

Then, we use the Long Short-Term Memory (LSTM) model; this model is specifically good for tracking patterns in datasets. Our model layer scheme uses layers of 50 LSTM cells, followed by a 20% dropout, another layer of 50 neurons, and a dense output layer. We train our model using the Adam optimizer (for general purpose use and computation saving) and the Mean Squared Error (MSE) loss function.


#### Model Evaluation
To asses the model accuracy, I use some metrics from sklearn such aslike Mean Squared Error (MSE) and Mean Absolute Error (MAE) and R-squared (R2) to measure how far off its predictions are from the actual temperatures. I also plot the graph between every epoch and with 20% balance of whole dataset to better visualize the accuracy of the model.


#### Results
For the model result, our model kind of does pretty well. It achieves a mean squared error on the test set of 0.2970 and a mean absolute error (MAE) of 98.33% accuracy on the test dataset. Error metrics indicate that the scaler and model tuning are good, but there's always room for improvement. Actually, before getting good results in both metrics, I take a closer look at the model tuning and various scalers to see what can be done to improve the model. Is it always a good habit to revise the whole code of the model of the model thoroughly


## Roadmap

![roadmap](/assets/images/san-juan-mountains.jpg "San Juan Mountains")



## Screenshots

![The San Juan Mountains are beautiful!](/assets/images/san-juan-mountains.jpg "San Juan Mountains")
![The San Juan Mountains are beautiful!](/assets/images/san-juan-mountains.jpg "San Juan Mountains")
![The San Juan Mountains are beautiful!](/assets/images/san-juan-mountains.jpg "San Juan Mountains")
![The San Juan Mountains are beautiful!](/assets/images/san-juan-mountains.jpg "San Juan Mountains")
![The San Juan Mountains are beautiful!](/assets/images/san-juan-mountains.jpg "San Juan Mountains")
![The San Juan Mountains are beautiful!](/assets/images/san-juan-mountains.jpg "San Juan Mountains")
![The San Juan Mountains are beautiful!](/assets/images/san-juan-mountains.jpg "San Juan Mountains")
![The San Juan Mountains are beautiful!](/assets/images/san-juan-mountains.jpg "San Juan Mountains")


## Lessons Learned

Informative video about LSTM



## Known limitation

1. Currently, the sequence length has an issue where it deletes the last sequence length, which is 30 rows of daily data. Using the LSM model, losing 30 rows of data might not be a big issue compared to 11,323 rows of data.

2. The requirement text generated cannot focus on a specific project environment but instead the whole notebook, leading to unrelated dependencies.

3. unrelated to model performance, but the model plot visualization is currently unavailable inside the notebook and instead requires more dependencies (Netron) and a browser for visualization.

4. An advanced model and large dataset required large computation power and a GPU. Currently, based on a local machine (supa hot laptop), there might be a transition to a cloud environment (codespace).

## Future Improvement
1. other model prophet
2. pca robust scaler
3. RandomForestRegressor
## Authors

- [@DNXL](https://www.github.com/DNXL-UMK)

📌Another project upcoming 
## Acknowledgements

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)

