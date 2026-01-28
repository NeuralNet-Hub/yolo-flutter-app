<div align="center">
  <a href="https://neuralnet.solutions" target="_blank">
    <img width="450" src="https://raw.githubusercontent.com/NeuralNet-Hub/assets/main/logo/LOGO_png_orig.png">
  </a>
</div>

# Ultralytics YOLO Flutter App 🚀

This repository is a **fork** of [Ultralytics YOLO Flutter App](https://github.com/ultralytics/yolo-flutter-app) and provides an open-source implementation of YOLO (You Only Look Once) models for Flutter applications. Built with the AGPL license, this project allows developers to integrate computer vision capabilities into their mobile applications.

## 📋 What is YOLO?

YOLO (You Only Look Once) is an AI architecture for real-time object detection, image classification, and pose estimation. This Flutter plugin provides seamless integration of YOLO models into iOS and Android applications with a single codebase.

## ✨ Features

- **5 AI Tasks**: Object Detection, Image Classification, Instance Segmentation, Pose Estimation, Oriented Bounding Box Detection
- **Cross-platform**: Works on iOS 13.0+ and Android API 21+
- **Real-time Performance**: Up to 30 FPS on modern devices
- **Easy Integration**: Simple Flutter API with comprehensive documentation
- **Flexible Deployment**: Supports both local execution and Docker containerization
- **Open Source**: Released under AGPL-3.0 license

## 📋 Requirements

- Flutter SDK 3.0+
- Dart 2.17+
- Android Studio or Xcode for development
- Docker (optional, for containerized deployment)

## 🚀 Quick Start with Docker

The recommended way to run this project is using Docker:

### 1. Clone the repository
```bash
git clone https://github.com/NeuralNet-Hub/yolo-flutter-app.git
cd yolo-flutter-app
```

### 2. Build the Docker image
```bash
docker build -t yolo-flutter-app .
```

> **Note**: The Dockerfile was originally taken from [flutter-docker](https://github.com/iarunsaragadam/flutter-docker) and has been adapted for this project.

## 🚀 Quick Start with Flutter

### 1. Add dependencies
```yaml
dependencies:
  ultralytics_yolo: ^0.1.26
```

### 2. Install dependencies
```bash
flutter pub get
```

### 3. Add a model
Download YOLO model files from the repository or export from Ultralytics:
```bash
# Example: Download from releases
# Add model files to ios/Runner/ or android/app/src/main/assets
```

### 4. Run the app
```bash
flutter run
```

## 📊 Supported Tasks

| Task | Description | Use Cases |
|------|-------------|-----------|
| **Detection** | Find objects & locations | Security, inventory, shopping |
| **Segmentation** | Pixel-perfect object masks | Photo editing, segmentation |
| **Classification** | Image categorization | Content moderation, tagging |
| **Pose Estimation** | Human pose & keypoints | Fitness apps, motion capture |
| **OBB Detection** | Rotated bounding boxes | Aerial imagery, license plates |

## 🐳 Docker Deployment

### Using Docker for Development

The project includes a pre-configured Dockerfile for building and running the Flutter application:

```bash
# Build the Docker image
docker build -t yolo-flutter-app .

# Run with volume mounting for hot reload (development)
docker run -p 8080:8080 -v $(pwd):/app yolo-flutter-app
```

### Dockerfile Information

- **Source**: Based on [flutter-docker](https://github.com/iarunsaragadam/flutter-docker)
- **Includes**: Flutter SDK, Android SDK, Java 17
- **Default Command**: Builds the Flutter APK in release mode
- **Architecture**: Supports amd64 and arm64

## 💡 Usage Example

```dart
import 'package:ultralytics_yolo/ultralytics_yolo.dart';

YOLOView(
  modelPath: 'yolo11n',
  task: YOLOTask.detect,
  onResult: (results) {
    print('Found ${results.length} objects!');
    for (final result in results) {
      print('${result.className}: ${result.confidence}');
    }
  },
)
```

## 📁 File Structure

```
.
├── lib/                    # Dart source code
│   ├── ultralytics_yolo.dart    # Main plugin
│   ├── core/                    # Core implementation
│   ├── models/                  # Data models
│   └── platform/                # Platform-specific code
├── android/                  # Android native code
├── ios/                      # iOS native code
├── example/                  # Example application
├── Dockerfile                # Docker configuration
├── pubspec.yaml             # Flutter dependencies
└── README.md                # This file
```

## 🔧 Configuration

### Platform-Specific Setup

**For iOS:**
- Add CoreML models to `ios/Runner/`
- Configure Xcode project settings
- Enable necessary permissions in `Info.plist`

**For Android:**
- Add TFLite models to `android/app/src/main/assets/`
- Configure Gradle build files
- Ensure Android SDK is properly set up

## 📝 License

This project is released under the **[GNU Affero General Public License v3.0 (AGPL-3.0)](LICENSE)**. 

This license ensures:
- Freedom to run, study, and change the software
- Freedom to distribute copies of the software
- Freedom to distribute modified versions of the software
- Copyleft provisions that require modified versions to be released under the same license when distributed

As a fork of the official Ultralytics YOLO Flutter App, this repository maintains the same licensing terms while providing additional features and customizations.

## 🧠 About NeuralNet

[NeuralNet](https://neuralnet.solutions) is an AI software development company specializing in privacy-focused artificial intelligence solutions. Our mission is to democratize AI technology while ensuring data privacy and security.

### Connect with Us

🌐 **Company Website**: [neuralnet.solutions](https://neuralnet.solutions)  
📝 **Author's Blog**: [henrynavarro.org](https://henrynavarro.org)  

### Acknowledgements

This project is a fork of [Ultralytics YOLO Flutter App](https://github.com/ultralytics/yolo-flutter-app) and the Dockerfile is based on [flutter-docker](https://github.com/iarunsaragadam/flutter-docker). We thank the original developers for their excellent work.

---

_Developed by_ **_[Henry Navarro](https://github.com/hdnh2006)_** _- Building the future of computer vision, one model at a time._

## 📮 Support

- 🐛 **Bug Reports**: [GitHub Issues](https://github.com/NeuralNet-Hub/yolo-flutter-app/issues)
- 💡 **Feature Requests**: [GitHub Discussions](https://github.com/NeuralNet-Hub/yolo-flutter-app/discussions)
- 📖 **Documentation**: [Ultralytics Docs](https://docs.ultralytics.com/)

---

**Stay Updated**: Follow us on social media for the latest updates and AI development insights!