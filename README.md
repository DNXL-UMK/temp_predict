
# Climate change Prediction using LSTM

![LSTM](https://img.shields.io/badge/LSTM-model-green?style=flat)
![climate](https://img.shields.io/badge/climate-prediction-red?labelColor=yellow&style=flat)
![Github pro](https://img.shields.io/badge/Github%20-pro-blue?labelColor=red&style=flat)

![bnanner](https://github.com/DNXL-UMK/temp_predict/blob/main/assets/Screenshot%202024-05-02%20230327.png)                                
                                                    
                                                    

### Introduction
This project is all about building a model that can predict daily mean temperatures using Long Short-Term Memory (LSTM) neural networks using 30 year worth of daily dataset from 1991 to 2021. The idea is to come up with a tool that can almost accurately forecast the temperature based on stuff like relative humidity, dew point, wind speed, and other weather parameters. Other than testing on validation data, I also test the model on new dataset of year 2022, see the screenshot. For simplicity the prediction model given name is **Psychic** 


Psychic documentation in the notebook comment 🎊


## Table of Contents 📋

- [Psychic model](#jeli-climate-prediction)
  - [Lesson](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#screenshots)
  - [Getting started](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#getting-started)
  - [Installation](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#installation)
  - [Roadmap](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#roadmap)
  - [Methodology](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#methodology)
  - [Screenshot](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#screenshots)
  - [Known Limitation](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#known-limitation)
  - [Future improvement](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#future-improvement)
  - [Authoes](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#authors)
  - [Acknowledgement](https://github.com/DNXL-UMK/temp_predict?tab=readme-ov-file#acknowledgements)


## Getting Started ✅

### Lessons to be Learned🧑‍🏫

Informative video about LSTM


[![LSTM](https://img.youtube.com/vi/YCzL96nL7j0/0.jpg)](https://www.youtube.com/watch?v=YCzL96nL7j0)



## Installation 🧑‍💻

1. Clone the repo 

```bash
  git clone https://github.com/DNXL-UMK/temp_predict.git
```

2. Navigate to the project directory
```bash
  cd temp_predict
```

3. Install dependencies
[❗ currently the dependencies is based on my entire libraries (including unrelated library to the project like hugging face or transformers), there's known fix but for now ❌]
Try this first
```bash
  pip install -r requirement_guess.txt
```

4. Open and run the code in Jupyter Notebook (My environment :Vscode)
```bash
  code Preprocessing_dataset.ipynb
```
if theres dependencies issues, use this
```bash
  pip install -r requirements_full.txt
```

### Methodology
#### Data Preprocessing
First things first, clean up the data so we can feed it into our model. We then handle missing values, normalize and standardize all the features, and cut up the data into nice 30 rows of sequences that our LSTM network can digest. 🔬

After the task is completed, we set climate parameters as our input (features) sequences, and the target parameter is the daily mean temperature for training the psychic model.

Then, we use the Long Short-Term Memory (LSTM) model; this model is specifically good for tracking patterns in datasets. Our model layer scheme uses layers of 50 LSTM cells, followed by a 20% dropout, another layer of 50 neurons, and a dense output layer. We train our model using the Adam optimizer and the Mean Squared Error (MSE) loss function.👾


#### Model Evaluation
To asses the model accuracy, I use some metrics from sklearn such Mean Squared Error (MSE) and Mean Absolute Error (MAE) and R-squared (R2) to measure how far off its predictions are from the actual temperatures. I also plot the graph between every epoch and with 20% balance of whole dataset to better visualize the accuracy of the model. 📊


#### Results
For the model result, our model kind of does pretty well. It achieves a mean squared error on the test set of 0.280 and a mean absolute error (MAE) of 98.38% accuracy on the test dataset. Error metrics indicate that the scaler and model tuning are good, but there's always room for improvement. Actually, before getting achieving good results, I take a closer look at the opimizer(SGD etc) ,various scalers(RobustScaler etc), model tuning( several hundred epoch and thousands of thousands neurons iterations, rip laptop 😭) to see what can be done to improve the model. Is it always a good habit to revise the whole code. There is only 130 rows of temperature value prediction with 1 threshold value that differs with the actual value, as compared to the full rows of data which are 11293 (after subtracting 30 for the sequence length issue).📈

Mean Squared Error: 0.2801887190633722

Mean Absolute Error: 0.4164799928770702

R^2 Score: 0.8024131150432166


## Roadmap ⏳

![roadmap](https://github.com/DNXL-UMK/temp_predict/blob/main/assets/Psychic%20model1.png)



## Screenshots 🖼️


#### Model loss on every epoch iteration
![Model loss on every epoch iteration](https://github.com/DNXL-UMK/temp_predict/blob/main/assets/output.png)

#### Model prediction validation
![Model prediction validation](https://github.com/DNXL-UMK/temp_predict/blob/main/assets/val.png)

#### Timeseries interactive plot between true value and predicted (20% validation)
![ dataset predictions](https://github.com/DNXL-UMK/temp_predict/blob/main/assets/validation%20plotly.png)

#### Testing psychic model with new dataset of year 2022
![new data](https://github.com/DNXL-UMK/temp_predict/blob/main/assets/new_data_2022.png)

#### Timeseries interactive plot between true value and predicted with new dataset of year 2022 (The plot is a bit skewed shows that climate dataset needed to be constansly trained with latest data for accuracy)
![ plotly](https://github.com/DNXL-UMK/temp_predict/blob/main/assets/plotly%20new%20data.png)



## Known limitation 💣

1. Currently, there is an issue with the sequence length where it deletes the last 30 rows of daily data. With the LSM model, the loss of 30 rows of data may not be significant when compared to the loss of 11,293 rows of data. There is several solution in mind but I save it for future improvement

2. The generated requirement.txt lacks focus on a specific project environment, resulting in the inclusion of unrelated dependencies throughout the notebook. (Basically every libraries I install including Transformers, beautifulsoup4 and etc) ⚠️

3. Additionally, the model plot visualization is currently not accessible within the notebook. To view the visualization, you will need to install additional dependencies (Netron) and use a browser.🙅

4. A high-level model and extensive dataset necessitated significant computational power and a GPU. At present, there is a possibility of moving from a local machine (my laptop dyin rapidly every hyperparameter tuning 🌡️) to a cloud environment (codespace).




## Future Improvement 🧯
1. There are alternative models that could be explored for this case study, including neural prophets, decision trees, and various others. For enhanced accuracy, it is advisable to conduct tests using different models and fine-tune the hyperparameters to achieve optimal results.

2. Similarly, the neural network model also offers numerous scalers for the climate dataset that have not been tested in this case study. Scalers suitable for handling large and unpredictable datasets include RobustScaler, Principal Component Analysis (PCA), and other similar techniques.
   
3. The target parameter for the model is currently set as the mean value of the daily temperature. It is because there is so much noisy data or outliers that can distort the data lack of accuracy in predicting temperature on a specific date and time. Neural network and any regression are sensitive to outliner, to remove it beforehand is important to ensure accurate reading.

## Authors 🪪
### contact
- [@DNXL](https://www.github.com/DNXL-UMK)
- [Linkedin](https://www.linkedin.com/in/muhddaniel/)

📌Another project upcoming 
Genrative pre-trained transformer (GPT) or LLama scheme for UMK research uses (personal project)


## Acknowledgements 🙇

 - [Awesome Readme Templates](https://awesomeopensource.com/project/elangosundar/awesome-README-templates)
 - [Awesome README](https://github.com/matiassingers/awesome-readme)
 - [How to write a Good readme](https://bulldogjob.com/news/449-how-to-write-a-good-readme-for-your-github-project)
   
   [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.7087890.svg)](https://doi.org/10.5281/zenodo.7087890)

   
  Zippenfenig, P. (2023). Open-Meteo.com Weather API [Computer software]. Zenodo. https://doi.org/10.5281/ZENODO.7970649

  Hersbach, H., Bell, B., Berrisford, P., Biavati, G., Horányi, A., Muñoz Sabater, J., Nicolas, J., Peubey, C., Radu, R., Rozum, I., Schepers, D., Simmons, 
  A., Soci, C., Dee, D., Thépaut, J-N. (2023). ERA5 hourly data on single levels from 1940 to present [Data set]. ECMWF. 
  https://doi.org/10.24381/cds.adbb2d47

  Muñoz Sabater, J. (2019). ERA5-Land hourly data from 2001 to present [Data set]. ECMWF. https://doi.org/10.24381/CDS.E2161BAC

  Schimanke S., Ridal M., Le Moigne P., Berggren L., Undén P., Randriamampianina R., Andrea U., Bazile E., Bertelsen A., Brousseau P., Dahlgren P., 
  Edvinsson L., El Said A., Glinton M., Hopsch S., Isaksson L., Mladek R., Olsson E., Verrelle A., Wang Z.Q. (2021). CERRA sub-daily regional reanalysis 
  data for Europe on single levels from 1984 to present [Data set]. ECMWF. https://doi.org/10.24381/CDS.622A565A
