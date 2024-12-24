# Barcode Correction and Decoding

This project is a computer vision-based tool that processes distorted barcode images. It can handle images with noise, tilts, or incomplete sections and outputs corrected images along with the decoded barcode information.

---

## Features
- **Distortion Correction**: Automatically detects and corrects tilted or incomplete barcodes.
- **Noise Reduction**: Enhances barcode images by removing visual noise.
- **Barcode Decoding**: Reads and outputs the information encoded in the barcode using Code-11 decoding techniques.
- **Comprehensive Output**: Provides the corrected image and the decoded barcode content.
- **Visualization**: Generates detailed visualizations of processing steps.

---

## Installation

### Prerequisites
Ensure you have the following installed:
- Python 3.8 or above

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/barcode-correction-decoding.git
   cd barcode-correction-decoding
   ```

2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Verify installation by running:
   ```bash
   python main.py --help
   ```

---

## Usage

### Command Line
Run the tool with the following command:
```bash
python main.py --input <input_image_path> --output <output_image_path>
```

### Arguments
- `--input`: Path to the distorted barcode image.
- `--output`: Path to save the corrected image.
- `--show`: (Optional) Displays the processed image and decoding result.

### Example
```bash
python main.py --input samples/barcode1.png --output results/corrected_barcode1.png --show
```

---

## Example Outputs
### Input:
![Distorted Barcode](samples/barcode1.png)

### Corrected:
![Corrected Barcode](results/corrected_barcode1.png)

### Decoded Output:
```
Barcode Content: 
```

---

## How It Works
1. **Image Preprocessing**:
   - Converts colored pixels to grayscale and removes noise.
   - Enhances edges and normalizes contrast.
   - Detects and removes wave patterns using FFT transformation.

2. **Geometric Correction**:
   - Applies perspective transforms to correct tilts.
   - Aligns the barcode horizontally using Sobel edge detection and affine transformations.

3. **Row and Column Analysis**:
   - Identifies the row with the most black pixels.
   - Finds the column with the longest continuous sequence of black pixels.

4. **Barcode Decoding**:
   - Implements Code-11 decoding to interpret barcode content.
   - Provides detailed feedback on success or failure.

5. **Visualization**:
   - Generates subplots showing each step in the process for debugging and demonstration.

---

## Contributing

We welcome contributions! Please:
1. Fork the repository.
2. Create a feature branch.
3. Submit a pull request with a detailed explanation of your changes.

---
