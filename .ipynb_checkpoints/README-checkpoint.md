# 4000_project

This readme file will guide you through the project files.

The repo has everything needed to reproduce all project results, from data preprocessing to figures generation.

- Data section:
    nyiso folder: all the data used for this project are inside this folder, it was collected fully from nyiso website directly:
    - `da_lmp` Day-Ahead price data.
    - `rt_lmp` Real-Time price data.
    - `load_forecast` load forecasts data.
    - `actual_load` actual load data (not needed).
    - `weather_forecast` weather forecasts data (not needed).
    
    - `NYISO_data_processing_4000.ipynb` This notebook will process all the files and create one dataframe for each dataset.
    
    
- Model Training:
    We built 3 different models: CNN, LSTM, CNN-LSTM. We experimented with each model using different structures and only kept the best performing structure.
    Each model has two main notebooks:
    1- for hyperparameter search, keras-tuner: this notebook has the full process for the search (example: `CNN_LSTM_model_keras_tuner.ipynb`).
    2- for Best model training: this notebook walks through the implementation for best model after choosing the best hyperparameters (example: `CNN_LSTM_model.ipynb`)
    For each model, we keep the best one for each look-back window considered (24-48-72 hours), so we have 9 candiadate models.
    
- Model Comparisons:
    - `Models_comparisons.ipynb` this notebook run various comparisons between the candidate models to have a better picture for the performance.
    
    
- Transfer Learning:
    - `Transfer_learning_models.ipynb` in this notebook we show the possibily of using tranfer learning to move models trained on certain zone to another zone. The notebook summaries our efforts in this task.
    
    
- Others:
    - `figures` include the figures produced from the notebooks and the ones used in the report.
    - `random_search` and `tuning_results` have the results of the hyperparameter search conducted for each model.