# STP to STL Converter and Viewer

This is a comprehensive tool for converting STP/STEP files to STL format with material cost analysis and 3D visualization.

## Features

- Convert STP/STEP files to STL format
- Calculate dimensions, volume, weight, and material cost
- Interactive 3D viewer for STL files
- Material selection for cost estimation
- Server-based conversion with web interface
- Comprehensive measurements
- Support for both Gmsh and OpenCASCADE backends

## Requirements

The following packages are required:

- Python 3.6+
- Flask
- Gmsh
- PythonOCC-Core (OpenCASCADE)
- Three.js (included via CDN)

Install the required Python packages:

```bash
pip install flask numpy
```

For the geometric processing backends:

```bash
# For Gmsh
pip install gmsh

# For OpenCASCADE
pip install PythonOCC-Core
```

## Usage

### Web Interface

1. Start the server:

```bash
python convert_stp_to_stl_server.py
```

2. Open a web browser and navigate to http://localhost:5000
3. Upload an STP/STEP file, select material, and click "Convert & View"
4. The converted model will be displayed with dimension and cost information

### Command-line Conversion

For batch conversion of multiple files:

```bash
python convert_stp_to_stl.py path/to/directory -o output_directory
```

For a single file:

```bash
python convert_stp_to_stl.py path/to/file.stp -o output_directory
```

## Available Scripts

- `convert_stp_to_stl_server.py`: Flask server with web interface
- `convert_stp_to_stl_simple.py`: Simplified Flask server
- `convert_stp_to_stl.py`: Command-line tool using Gmsh
- `convert_stp_to_stl_new.py`: Command-line tool using OpenCASCADE
- `run_conversion_server.py`: Simple launcher script

## Web Interface Files

- `stp_converter.html`: Main web interface

## Material Properties

The system includes built-in properties for common materials:

| Material  | Density (g/cm³) | Cost ($/kg) |
|-----------|----------------|-------------|
| PLA       | 1.24           | 20.00       |
| ABS       | 1.04           | 22.00       |
| PETG      | 1.27           | 25.00       |
| Resin     | 1.12           | 40.00       |
| Steel     | 7.85           | 15.00       |
| Aluminum  | 2.70           | 20.00       |

Custom materials can also be specified.

## How It Works

1. The STP/STEP file is loaded using either Gmsh or OpenCASCADE
2. A mesh is generated from the 3D model
3. Dimensions are calculated from the bounding box
4. Volume is calculated from the mesh
5. Weight is calculated based on material density
6. Cost is estimated based on weight and material cost per kg
7. The STL file is generated and can be viewed in the browser

## Troubleshooting

- If conversion fails with Gmsh, the system will automatically try OpenCASCADE
- Make sure the STP/STEP file is valid and properly formatted
- Large files may take longer to process
- If the web server doesn't start, check if port 5000 is already in use

## License

MIT License #   3 d - m o d e l - v i e w  
 #   3 d - m o d e l - v i e w  
 #   3 d - m o d e l - v i e w  
 