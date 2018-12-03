# Model a predict the success/failure of Kickstarted project

This repo contains the files to predict the success/failure of a kickstarter campaign. 


# Instructions to use the Kick Starter Prediction Model

The class in the model.py is capable of performing data pre-processing, model training, prediction generation and
evaluation. 

## Model.KSModel
###class model.KSModel(data_path)

Model for predicting success/failure of a Kick starter project.

#### Parameters: data_path: string
                    Path to the data file containing the kick starter data.
 
 
#### Methods
**data_transformer()**  : Perform data cleaning, removal, transformation on data.

    Parameters: data_path - string, optional
    Returns: x_data - numpy array
             labels - numpy array

**data_processing()**  : Perform scaling and splitting on the given data.

    Parameters: None
    Returns: None

**train_model()**  : Perform model training on the input data.

    Parameters: None
    Returns: None

**process_custom_data()** : Process and scale custom data for testing.

    Parameters: data_path - string
    Returns: x_custom - numpy array
             labels - numpy array
    
**make_prediction** : Generate predictions on the given test data.

    Parameters: x_test - numpy array, optional
    Returns: Predictions - numpy array of size x_test if given.
    
**evaluate_model** : Evaluate the Random forest model with metrics like accuracy, precision, recall, f1 score and auc.
Plot the precision recall curve.

    Parameters: x_test - numpy array, optional
                         Test input data for the model as numpy array.
                y_test - numpy array, optional
                         Test label data for the model as numpy array.
    Returns: None
 
 
## Example Usage:


    > from model import KSModel
    > classifier = KSModel('data.csv')
    > classifier.data_processing()
    > classifier.train_model()
    > classifier.evaluate_model()
        Accuracy of predictions: 98.0734152408 %
        Precision score: 0.970139349701
        Recall score: 0.98252688172
        F1 score: 0.976293823038
        Area Under the Curve: 0.997330581364
    
    
## Example Usage with custom test data

    > from model import KSModel
    > classifier = KSModel('data.csv')
    > classifier.data_processing()
    > classifier.train_model()
    > x_test, y_test = classifier.process_custom_data('data.csv')
    > pred = classifier.make_prediction(x_test)
    > classifier.evaluate_model(x_test, y_test)
        Accuracy of predictions: 98.0734152408 %
        Precision score: 0.970139349701
        Recall score: 0.98252688172
        F1 score: 0.976293823038
        Area Under the Curve: 0.997330581364