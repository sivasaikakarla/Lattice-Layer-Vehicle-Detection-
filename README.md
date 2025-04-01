# Traffic Video Analysis using OpenCV and Parallel Processing

## Overview
This project implements a traffic density analysis system using OpenCV, NumPy, and concurrent processing. It processes video frames to detect motion in Lattice Layer regions and estimates traffic density and vehicle detection in multiple lanes. The system supports both sequential and parallel execution modes and provides visualization of detected traffic.

## Features
- **Histogram Equalization**: Enhances contrast in the regions of interest (ROI) for better motion detection.
- **Grid-based Motion Detection**: Divides each ROI into a grid and detects motion in each cell.
- **Parallel Processing**: Uses ThreadPoolExecutor for concurrent frame processing.
- **Traffic Density Calculation**: Computes the proportion of occupied grid cells to estimate traffic density.
- **GUI Integration**: Supports a Tkinter-based GUI for easy configuration and execution.

## File Structure
- `gui.py`: The Tkinter-based GUI that allows users to select video files and processing parameters.
- `rparallel_he3.py`: The core script that processes video frames in parallel way and computes traffic density.
- `seq.py`: The core script that processes video frames in sequential way and detect vehicle.
- `user_input_data.json`: A configuration file specifying video file path, color channels, grid dimensions, and execution mode.

## Dependencies
Ensure you have the following Python libraries installed:
```sh
pip install opencv-python numpy pandas openpyxl psutil
```

## Configuration
Modify `user_input_data.json` to set up the processing parameters:
```json
{
    "video": "video_input.mp4",
    "color_channel": "V",
    "grids": {
        "rows": 6,
        "cols": 6
    },
    "execution_mode": "Parallel"
}
```
- `video`: Path to the input traffic video.
- `color_channel`: Color space used for motion detection (`H`, `S`, `V`, `gray`, etc.).
- `grids`: Number of rows and columns in the grid-based detection system.
- `execution_mode`: `Parallel` or `Sequential` mode.

## Running the Project
### Using GUI
Run the GUI with:
```sh
python gui.py
```
### Running Directly
To process a video file directly without GUI:
```sh
python rparallel_he3.py
```
or
```sh
python seq.py
```

## Output
- `test_output1.mp4`: Processed video with detected motion highlighted.
- Console logs with traffic density statistics.
- `result_matrix1.xlsx`: (Optional) Stores processed grid results.

## Performance Metrics
- **Execution Time**: Displayed at the end of processing  (parallel took less time than sequential Execution).
- **Memory Usage**: Reports memory consumption in MB.
- These above metrics shown when run individually

## Future Enhancements
- Optimize parallel processing for better performance.
- Add real-time video stream support.
- Implement additional color spaces for improved detection accuracy.

