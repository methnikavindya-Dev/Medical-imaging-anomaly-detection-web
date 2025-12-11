# 🏥 Medical Imaging Analysis Platform

> Advanced web-based anomaly detection system for medical scans using digital image processing algorithms

[![Live Demo](https://img.shields.io/badge/demo-live-brightgreen)](https://your-demo-url.vercel.app)
[![React](https://img.shields.io/badge/React-18.2.0-blue.svg)](https://reactjs.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

![Medical Imaging Platform Banner](https://via.placeholder.com/1200x400/4F46E5/FFFFFF?text=Medical+Imaging+Analysis+Platform)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Demo](#demo)
- [Technologies Used](#technologies-used)
- [Algorithms Implemented](#algorithms-implemented)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [How It Works](#how-it-works)
- [Screenshots](#screenshots)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## 🎯 Overview

This project is a web-based medical imaging analysis platform that automatically detects anomalies in medical scans including tumors, fractures, and infections. Built with React and Canvas API, it demonstrates the application of digital image processing algorithms in healthcare diagnostics.

**Academic Context:** This project was developed as part of a Digital Image Processing course, implementing concepts learned in laboratory sessions using Python, OpenCV, NumPy, and MATLAB, translated into a deployable web application.

### Key Highlights

- ✨ **Real-time Processing**: Instant analysis without server delays
- 🔒 **Privacy-First**: All processing happens locally in the browser
- 🎨 **Three Detection Modes**: Tumor, Fracture, and Infection detection
- 📊 **Visual Feedback**: Side-by-side comparison with confidence scores
- 🚀 **Zero Backend**: Fully client-side application

## ✨ Features

### 🧠 Detection Algorithms

1. **Tumor Detection**
   - Edge detection using Sobel operator
   - Morphological operations (dilation and erosion)
   - Connected component analysis
   - Region highlighting in red

2. **Fracture Detection**
   - Canny-inspired edge detection
   - Hough transform for line detection
   - Strong edge thresholding
   - Line highlighting in blue

3. **Infection Analysis**
   - Adaptive thresholding
   - Connected component labeling
   - Size-based filtering
   - Area highlighting in yellow

### 🎨 User Interface

- **Modern Design**: Clean, professional medical interface
- **Responsive Layout**: Works on desktop, tablet, and mobile
- **Interactive Algorithm Selection**: Easy switching between detection modes
- **Drag-and-Drop Upload**: Simple file upload interface
- **Real-time Results**: Instant feedback with confidence scores

## 🎬 Demo

### Live Application
🔗 **[View Live Demo](https://your-demo-url.vercel.app)** *(Replace with your actual URL)*

### Quick Start Video
*(Add a GIF or video demonstration here)*

## 🛠️ Technologies Used

### Frontend Framework
- **React 18.2.0** - UI component library
- **JavaScript ES6+** - Core programming language
- **HTML5** - Structure and Canvas elements
- **CSS3** - Styling (via Tailwind)

### Styling & UI
- **Tailwind CSS** - Utility-first CSS framework
- **Lucide React** - Icon library

### Image Processing
- **Canvas API** - Pixel manipulation and rendering
- **FileReader API** - File handling
- **Custom Algorithms** - Computer vision implementations

### Build Tools
- **Create React App** - Project scaffolding
- **Webpack** - Module bundling
- **Babel** - JavaScript transpiling

### Deployment
- **Vercel** - Hosting platform
- **Git** - Version control
- **GitHub** - Repository hosting

## 🔬 Algorithms Implemented

### 1. Gaussian Blur
```
Purpose: Noise reduction
Formula: G(x,y) = (1/2πσ²) * e^(-(x²+y²)/2σ²)
Implementation: Convolution with 5x5 kernel
```

### 2. Sobel Edge Detection
```
Purpose: Edge detection
Kernels: 
  Gx = [[-1,0,1], [-2,0,2], [-1,0,1]]
  Gy = [[-1,-2,-1], [0,0,0], [1,2,1]]
Formula: G = √(Gx² + Gy²)
```

### 3. Morphological Operations
```
Dilation: Expands white regions
Erosion: Shrinks white regions
Purpose: Noise removal and gap closing
```

### 4. Adaptive Thresholding
```
Purpose: Local contrast enhancement
Method: Calculates threshold based on neighborhood
```

### 5. Connected Component Analysis
```
Purpose: Region detection
Algorithm: Flood fill with stack-based traversal
```

## 📦 Installation

### Prerequisites

- Node.js 18.x or higher
- npm or yarn package manager
- Modern web browser (Chrome, Firefox, Safari, Edge)

### Step-by-Step Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/medical-imaging-platform.git
   cd medical-imaging-platform
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Start development server**
   ```bash
   npm start
   ```

4. **Open in browser**
   ```
   Navigate to http://localhost:3000
   ```

### Build for Production

```bash
npm run build
```

This creates an optimized production build in the `build` folder.

## 🚀 Usage

### Basic Workflow

1. **Select Algorithm**
   - Choose between Tumor Detection, Fracture Detection, or Infection Analysis

2. **Upload Medical Image**
   - Click the upload area or drag and drop an image
   - Supported formats: JPG, PNG, BMP

3. **Start Analysis**
   - Click the "Start Analysis" button
   - Wait for processing (typically 1-2 seconds)

4. **View Results**
   - Compare original vs processed images
   - Review detected anomalies count
   - Check confidence score

### Supported Image Types

- ✅ X-ray images
- ✅ CT scans
- ✅ MRI images
- ✅ General medical imaging formats (JPG, PNG)

### Tips for Best Results

- Use high-contrast images for better detection
- Ensure images are properly oriented
- Larger images may take longer to process
- Try different algorithms for different scan types

## 📁 Project Structure

```
medical-imaging-platform/
├── public/
│   ├── index.html
│   ├── favicon.ico
│   └── manifest.json
├── src/
│   ├── App.js                 # Main React component
│   ├── index.js               # Entry point
│   ├── index.css              # Global styles
│   └── algorithms/
│       ├── gaussianBlur.js
│       ├── sobelEdge.js
│       ├── morphology.js
│       └── thresholding.js
├── package.json
├── tailwind.config.js
├── README.md
└── LICENSE
```

## 🔍 How It Works

### Image Processing Pipeline

```
1. Upload Image
        ↓
2. Load to Canvas
        ↓
3. Extract Pixel Data
        ↓
4. Apply Selected Algorithm
        ↓
5. Process Pixels (Grayscale → Blur → Edge Detection → Morphology)
        ↓
6. Detect Anomalies (Connected Components)
        ↓
7. Highlight Regions
        ↓
8. Display Results
```

### Core Processing Steps

#### Step 1: Grayscale Conversion
```javascript
gray = (R + G + B) / 3
```

#### Step 2: Noise Reduction
```javascript
// Apply Gaussian blur
blurred = applyGaussianBlur(gray, kernelSize=5)
```

#### Step 3: Edge Detection
```javascript
// Sobel operator
edges = sobelEdgeDetection(blurred)
```

#### Step 4: Thresholding
```javascript
binary = edges > threshold ? 255 : 0
```

#### Step 5: Morphological Operations
```javascript
dilated = dilate(binary)
closed = erode(dilated)
```

#### Step 6: Region Detection
```javascript
anomalies = findConnectedComponents(closed)
```

## 📸 Screenshots

### Main Interface
![Main Interface](https://via.placeholder.com/800x450/667EEA/FFFFFF?text=Main+Interface)
*Algorithm selection and upload interface*

### Tumor Detection
![Tumor Detection](https://via.placeholder.com/800x450/EF4444/FFFFFF?text=Tumor+Detection)
*Tumor regions highlighted in red*

### Fracture Detection
![Fracture Detection](https://via.placeholder.com/800x450/3B82F6/FFFFFF?text=Fracture+Detection)
*Fracture lines highlighted in blue*

### Infection Analysis
![Infection Analysis](https://via.placeholder.com/800x450/FBBF24/FFFFFF?text=Infection+Analysis)
*Infected areas highlighted in yellow*

### Results Display
![Results](https://via.placeholder.com/800x450/10B981/FFFFFF?text=Analysis+Results)
*Detailed results with confidence scores*

## 🌐 Deployment

### Deploy to Vercel (Recommended)

1. **Install Vercel CLI**
   ```bash
   npm install -g vercel
   ```

2. **Login to Vercel**
   ```bash
   vercel login
   ```

3. **Deploy**
   ```bash
   vercel
   ```

4. **Production Deployment**
   ```bash
   vercel --prod
   ```

### Deploy to Netlify

1. **Build the project**
   ```bash
   npm run build
   ```

2. **Drag and drop** the `build` folder to [Netlify Drop](https://app.netlify.com/drop)

### Deploy to GitHub Pages

1. **Install gh-pages**
   ```bash
   npm install --save-dev gh-pages
   ```

2. **Add to package.json**
   ```json
   "homepage": "https://yourusername.github.io/medical-imaging-platform",
   "scripts": {
     "predeploy": "npm run build",
     "deploy": "gh-pages -d build"
   }
   ```

3. **Deploy**
   ```bash
   npm run deploy
   ```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. **Commit your changes**
   ```bash
   git commit -m 'Add some AmazingFeature'
   ```
4. **Push to the branch**
   ```bash
   git push origin feature/AmazingFeature
   ```
5. **Open a Pull Request**

### Development Guidelines

- Follow existing code style
- Add comments for complex algorithms
- Test thoroughly before submitting
- Update documentation as needed

## 🐛 Known Issues

- Large images (>5MB) may slow down processing
- DICOM format not currently supported
- Mobile performance may vary

## 🔮 Future Enhancements

- [ ] Add DICOM file support
- [ ] Implement more detection algorithms
- [ ] Add batch processing capability
- [ ] Export detailed analysis reports
- [ ] Multi-language support
- [ ] Real-time video stream analysis
- [ ] Integration with medical databases
- [ ] AI/ML model integration

## 📚 References

### Academic Resources
- Digital Image Processing - Rafael C. Gonzalez
- Computer Vision: Algorithms and Applications - Richard Szeliski
- OpenCV Documentation

### Technical Resources
- [Canvas API Documentation](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [React Documentation](https://react.dev/)
- [Tailwind CSS Documentation](https://tailwindcss.com/)

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Copyright (c) 2024 [Your Name]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction...
```

## 👨‍💻 Author

**[Your Name]**

- GitHub: [@yourusername](https://github.com/yourusername)
- LinkedIn: [Your LinkedIn](https://linkedin.com/in/yourprofile)
- Email: your.email@example.com
- Portfolio: [yourportfolio.com](https://yourportfolio.com)

## 🙏 Acknowledgments

- Thanks to my Digital Image Processing course instructor
- OpenCV community for algorithm references
- React and Tailwind CSS communities
- Medical imaging datasets for testing

## 📊 Project Stats

![GitHub stars](https://img.shields.io/github/stars/yourusername/medical-imaging-platform?style=social)
![GitHub forks](https://img.shields.io/github/forks/yourusername/medical-imaging-platform?style=social)
![GitHub issues](https://img.shields.io/github/issues/yourusername/medical-imaging-platform)
![GitHub pull requests](https://img.shields.io/github/issues-pr/yourusername/medical-imaging-platform)

---

<p align="center">
  Made with ❤️ for Digital Image Processing Course
</p>

<p align="center">
  <a href="#-table-of-contents">Back to Top ⬆️</a>
</p># Medical-imaging-anomaly-detection-web
