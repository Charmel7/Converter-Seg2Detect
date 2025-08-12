```markdown
# YOLOv8 Segmentation to Detection Converter

## 📁 Project Structure
```
conversion_seg2detect/
├── segment_to_box.py          # Single file conversion
├── prepare_dataset_for_detection.py  # Batch conversion
├── input/                    # Sample input structure
│   ├── seg_labels/           # Segmentation annotations (.txt)
│   └── images/               # Corresponding images
└── output/                   # Auto-generated output
```

## 🚀 Quick Start

### Prerequisites
```bash
pip install numpy
```

## 🔧 Usage

### 1. Convert Single File
```bash
python segment_to_box.py \
  -i "input/seg_labels/image1.txt" \
  -o "output/det_labels/image1.txt" \
  --image-size 640 640
```

### 2. Convert Entire Dataset
```bash
python prepare_dataset_for_detection.py \
  --input-dir "input/seg_labels" \
  --output-dir "output/det_labels" \
  --image-size 640 640 \
  --copy-images
```

## 📋 Parameters

### For `segment_to_box.py`
| Parameter       | Description                | Required |
|-----------------|----------------------------|----------|
| `-i`, `--input` | Input .txt file path       | Yes      |
| `-o`, `--output`| Output .txt file path      | Yes      |
| `--image-size`  | Image width and height     | Yes      |

### For `prepare_dataset_for_detection.py`
| Parameter         | Description                     | Required |
|-------------------|---------------------------------|----------|
| `--input-dir`     | Input directory with .txt files | Yes      |
| `--output-dir`    | Output directory               | Yes      |
| `--image-size`    | Image width and height         | Yes      |
| `--copy-images`   | Copy corresponding images      | No       |

## 💡 Examples

### Input Format (Segmentation)
```
0 100 200 150 250 300 400
1 150 300 200 350 250 400
```

### Output Format (Detection)
```
0 0.312500 0.468750 0.312500 0.312500
1 0.390625 0.520833 0.156250 0.208333
```

## 📜 License
MIT
```
