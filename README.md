This repository contains the trained Neural Network Model (NNM) and the synthetic lunar reflectance dataset.

[ROLO_band_reflectance.HDF](https://github.com/ZhenhuaJing/NNM/releases/tag/v1.0.0): The comprehensive synthetic lunar reflectance dataset generated using the GIRO/ROLO model and NASA SPICE toolkit. It contains densely sampled geometric configurations and the corresponding 32-band lunar reflectance spectra.

[lunar_nnm.keras](https://github.com/ZhenhuaJing/NNM/releases/tag/v1.0.0): The trained Keras neural network model.

To run the trained NNM, users first need to prepare the input geometric features (e.g., phase angle, observer coordinates) and save them as a `.HDF` file. In the main script, users should specify the data directory and load the synthetic dataset by defining `data_file = 'ROLO_band_reflectance.h5'`. Next, the trained Keras model can be loaded by executing `model = keras.models.load_model( 'lunar_nnm.keras')`. Once the model and data are ready, the prediction is performed by calling `y_pred = model.predict(test_x_norm)`, which rapidly outputs the estimated 32-band lunar reflectance. Finally, users need to apply the corresponding inverse normalization and log-transform to the `y_pred` array to retrieve the final physical reflectance values.
