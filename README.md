# MNIST Docker Classifier

This submission contains a simple MNIST image classifier for the Docker mini exercise.

The classifier used in this project is a `LinearSVC` model trained on MNIST.
The trained model is already included in the submission under `artifacts/mnist_linear_svc.joblib`, so the Docker container only performs inference.

## Files Included

- `Dockerfile`
- `docker-compose.yml`
- `requirements.txt`
- `predict_images.py`
- `mnist_pipeline.py`
- `train_model.py`
- `artifacts/mnist_linear_svc.joblib`

## How To Run

Open `CMD` in the submission directory and run:

```powershell
docker compose up
```

## Expected Input And Output

- The input directory must be named `Data`.
- The output directory must be named `Predictions`.
- `docker-compose.yml` mounts both directories from the host machine into the container.
- The container reads all supported image files from `Data`, predicts a digit for each image, and saves a renamed copy into `Predictions`.

Example:

- Input file: `img27.png`
- Predicted digit: `3`
- Output file: `img27_3.png`

## Notes

- `Data` and `Predictions` are not supposed to be included in the submitted ZIP.
- The model accuracy is not the focus of this exercise; the goal is to produce one prediction file for each image in `Data`.
- `train_model.py` is included for completeness, but it is not required when running the Docker container because the trained model file is already provided.
