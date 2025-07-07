# Self-Driving-Car-Simulation

[Watch the demo on YouTube](https://youtu.be/JOZqNO-JRSc)


## Setup

```sh
# Clone the repository
git clone https://github.com/uday-rana/cvi620-project.git

# Create a Conda environment
conda env create -f environment.yaml

# Activate the environment
conda activate cvi620-project
```

### macOS Setup

If you are using **macOS**, please be aware of the following setup differences:

- The simulator used in this project was downloaded directly from the official [Udacity Self-Driving Car Simulator GitHub repository](https://github.com/udacity/self-driving-car-sim), as the default installer provided may not work reliably on macOS.

- Some Python dependencies included in `requirements.txt` or `environment.yaml` were either incompatible with macOS or not required for local development. In those cases:

  - Incompatible dependencies were either replaced with macOS-friendly versions, or
  - Unnecessary dependencies were commented out or removed to avoid installation issues.

- A separate conda environment was created to isolate these changes. If you are using macOS, it is **recommended** to review and adjust the dependencies before installing with `pip` or `conda`.

This ensures that your environment remains stable and the training pipeline runs without error on macOS systems.

## Usage

1. Collect driving data using [Udacity's Self-Driving Car Simulator](https://github.com/udacity/self-driving-car-sim) in training mode. Save the output into a folder named `data/`.

2. Train the model using the following command:

   ```sh
   python -m cvi620-project
   ```

   This will create a trained model saved as `model.h5`.

3. To test the trained model, launch the simulator in autonomous mode. Then run the following command:

   ```sh
   python scripts/TestSimulation.py
   ```

## Final Deliverables

- Modularized codebase with clearly separated functionality:

  - `data_preprocessing.py`: Loads and cleans raw driving log data, preprocesses images (cropping, resizing, normalization).
  - `data_augmentation.py`: Performs data augmentation including flipping, brightness adjustment, shifting, zooming, and rotation to enrich the dataset.
  - `model_training.py`: Defines and trains the convolutional neural network (CNN) using the processed and augmented dataset.
  - `training_visualization.py`: Plots training and validation loss curves to help evaluate model performance.
  - `scripts/TestSimulation.py`: Runs the trained model in inference mode to control the car in the simulator.

- `model.h5`: The final trained model

- README with setup instructions and development challenges
