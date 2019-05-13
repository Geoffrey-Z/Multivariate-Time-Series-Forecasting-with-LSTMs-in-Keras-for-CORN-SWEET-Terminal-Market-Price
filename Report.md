# Sweet Corn Terminal Price Forecasting with LSTMs in Keras
Weiling(Geoffrey) Zhu

## Abstract
This project implements a street sign Sweet Corn Terminal Price Forecasting using LSTMs in Keras. This project is written in Python 3. The `keras`, `tensorflow`, and `scikit-learn` packages were used to build the model. Data visualization and preprocessing was done with the `matplotlib` packages.

## Dataset

The following dataset were considered for this project:

- [USDA - Fruit and Vegetable - Terminal Market Price - Reports](https://marketnews.usda.gov/mnp/fv-report?commAbr=CORN&rowDisplayMax=25&startIndex=1&repType=termPriceWeekly&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&reportConfig=true&repTypeChanger=termPriceWeekly&type=termPrice&locChoose=commodity&locAbrfrom=HX&locAbrlength=1&locAbr=&commodityClass=allcommodity&y=15&y=15&y=11&y=11&y=13&y=15&y=14&y=8&y=0&y=9&y=9&y=11&y=7&y=8&y=12&x=32&x=28&x=27&x=52&x=36&x=40&x=40&x=24&x=34&x=50&x=28&x=52&x=25&x=23&x=43&locAbrPass=ALL%7C%7C&refine=false&step3date=true&repDate=01%2F07%2F2017&endDate=12%2F29%2F2018&organic=&environment=&_environment=1&Run=Run) - a USDA Datasource for Terminal Market Price of Fruit and Vegetable.
- Original download file: [terminal prices sweet corn.xlsx](https://github.com/Geoffrey-Z/Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price/blob/master/terminal%20prices%20sweet%20corn.xlsx)

The datasets below were selected due to its simplicity and smaller size. The USDA dataset is very large, and has far more data than is necessary for a small-scale project like this.
- CORN_SWEET_Price_Monthly_Univariate_Forecasting: [BI-COLOR CORN-SWEET MONTHLY PRICE 1998-2018.csv](https://github.com/Geoffrey-Z/Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price/blob/master/BI-COLOR%20CORN-SWEET%20MONTHLY%20PRICE%201998-2018.csv)
- CORN_SWEET_Price_Weekly_Univariate_Forecasting: [BI-COLOR CORN-SWEET WEEKLY PRICE 1998-2018.csv](https://github.com/Geoffrey-Z/Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price/blob/master/BI-COLOR%20CORN-SWEET%20WEEKLY%20PRICE%201998-2018.csv)
- CORN_SWEET_Price_Weekly_Multivariate_Forecasting: [BI-COLOR, WHITE, YELLOW CORN-SWEET WEEKLY PRICE 1998-2018.csv](https://github.com/Geoffrey-Z/Multivariate-Time-Series-Forecasting-with-LSTMs-in-Keras-for-CORN-SWEET-Terminal-Market-Price/blob/master/BI-COLOR%2C%20WHITE%2C%20YELLOW%20CORN-SWEET%20WEEKLY%20PRICE%201998-2018.csv)

## Splitting

The CORN_SWEET_Price_Weekly_Multivariate_Forecasting dataset is splited into  into Training Set (first 70% rows) and Validation Set (remaining 30% rows).

## Input Data Visualization

The CORN_SWEET_Price_Weekly_Multivariate_Forecasting dataset contains 1099 records, 4 Columns. It contains weekly terminal prices for BI-COLOR, WHITE and YELLOW CORN-SWEET in U.S. from 1/1/1998 to 12/31/2018. The visualization below showing the 21 years of data for each Variety.

![Data_Visualization.png](assets/Data_Visualization.png)

## Network Architecture

I used a LSTM to forecastin the price of sweet corn. I chose this type of model because they are known to perform quite well on time Series datasets, such as Airline Passengers prediction problem and Air Pollution Forecasting. The architecture of the final version of the Keras model is shown below.

```python
# design network
model = Sequential()
model.add(LSTM(50, input_shape=(train_X.shape[1], train_X.shape[2])))
model.add(Dense(1))
model.compile(loss='mae', optimizer='adam')
# fit network
history = model.fit(train_X, train_y, epochs=50, batch_size=72, validation_data=(test_X, test_y), verbose=2, shuffle=False)
# plot history
pyplot.plot(history.history['loss'], label='train')
pyplot.plot(history.history['val_loss'], label='test')
pyplot.legend()
pyplot.show()
```

This architecture is a relatively simple convolutional network. It achieves an accuracy of ~96% on the validation dataset. This was the simplest and most accurate model out of several variants I tried. Listed below are some of the variants I tried out.

- Decreasing the number of filters in the first convolutional layer from 64 to 16. This resulted in a faster training time. However, the accuracy decreased by ~2%.
- Decreasing the number of filters in the first convolutional layer from 64 to 32. This resulted in a faster training time. However, the accuracy decreased by ~1%.
- Adding a 0.2 dropout layer after the first max pooling layer. This did not affect accuracy.
- Adding another convolutional and max pooling layer after the first max pooling layer. This did not affect accuracy.
- Increasing the number of units in the first dense layer from 64 to 128. This did not affect accuracy.
- Decreasing the number of units in the first dense layer from 64 to 32. This decreased accuracy by ~10%.

