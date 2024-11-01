
# COLMAP Model Reader and Exporter

This project provides tools for reading, writing, and exporting camera parameters from COLMAP binary and text models. It supports both `.bin` and `.txt` model formats.

## Features

1. **Read and Write COLMAP Models**: Supports both binary (`.bin`) and text (`.txt`) model formats.
2. **Export Camera Parameters**: Extracts and exports intrinsic and extrinsic camera parameters, as well as azimuth, elevation, and distance to a specified directory.
3. **Save Parameters to Pickle File**: Saves the camera parameters to a `.pkl` file for easy loading and further processing.

## Requirements

- Python 3.x
- numpy
- argparse
- collections
- pickle
- struct
- os

You can install the required libraries by running:
```bash
pip install numpy
pip install argparse
pip install pickle
```

## Usage

This script is designed to be run from the command line. Below is an example of how to use it:

```bash
python your_script_name.py --input_model path/to/your/model --input_format .bin --export_dir path/to/export/directory
```

### Command Line Arguments

- `--input_model`: Path to the input COLMAP model directory (Required).
- `--input_format`: Format of the input model, either `.bin` or `.txt` (Required).
- `--export_dir`: Directory to export the camera parameters and metadata (Required).

### Example

```bash
python colmap_model.py --input_model ./sample_model --input_format .bin --export_dir ./exported_params
```

## Output

The script will export the following files to the specified directory:

1. `camera_intrinsics.txt`: Contains the intrinsic camera parameters (K matrix).
2. `camera_extrinsics.txt`: Contains the extrinsic camera parameters (rotation matrix and translation vector).
3. `camera_angles.txt`: Contains the azimuth, elevation, and distance of the camera positions.
4. `meta.txt`: Contains a summary of the camera intrinsic parameters, azimuths, elevations, distances, and camera poses.
5. `meta.pkl`: Pickle file containing a list of the intrinsic matrix `K`, azimuths, elevations, distances, and camera poses, for easy loading in future processing.

## Code Structure

- **Data Structures**: Use of namedtuples `CameraModel`, `Camera`, `Image`, and `Point3D` for structured data handling.
- **Helper Functions**: Functions for reading and writing binary and text models, converting quaternion to rotation matrix, computing intrinsic matrix, azimuth, elevation, and distance.
- **Main Functionality**: The `main` function handles the command-line argument parsing and orchestrates the reading, processing, and exporting of camera parameters.

## Contributing

If you find any bugs or have a feature request, please create an issue or submit a pull request on GitHub.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgements

This project was inspired by the COLMAP software. Please refer to the COLMAP documentation for more details on the model format and underlying algorithms.

## Contact

If you have any questions or need further assistance, feel free to contact me via GitHub.

---

Ensure you replace `your_script_name.py` with the actual script name, and adjust the sample paths according to your directory structure.

Feel free to clone, modify, and expand this project as needed. Happy coding!

