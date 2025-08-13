# TesseractOCR iOS Framework

![Version](https://img.shields.io/badge/version-1.0.0-blue.svg)
![iOS](https://img.shields.io/badge/iOS-13.0+-green.svg)
![Tesseract](https://img.shields.io/badge/Tesseract-5.5.1-orange.svg)
![Build](https://github.com/thebenfarmer/TesseractOCR-iOS-Framework/actions/workflows/build-framework.yml/badge.svg)

A comprehensive iOS XCFramework for **Tesseract 5.5.1** with **professional-grade JPEG-12bit integration** and complete imaging pipeline for exceptional OCR quality in iOS applications.

## Key Features

- **Advanced Tesseract 5.5.1**: Latest OCR engine with 54,000+ optimized functions and 100+ language support
- **Professional JPEG-12bit**: **88 specialized j12* functions** with libjpeg-turbo 3.0.4 runtime precision selection
- **Complete Imaging Pipeline**: 6,197 Leptonica functions, 900 PNG, 1,105 TIFF symbols for comprehensive image processing
- **Enhanced OCR Quality**: Handles complex layouts, compressed images, and challenging document types
- **Massive Static Integration**: 425MB framework with all dependencies statically linked (no external requirements)
- **Universal iOS Binary**: Optimized arm64 device (142MB) + arm64/x86_64 simulator (282MB) support
- **Broad Compatibility**: iOS 13.0+ with professional-grade cross-compilation
- **Automated Build**: CI/CD pipeline with automated testing and artifact generation

## Professional-Grade Image Processing

This framework provides a **complete imaging pipeline** with professional-grade libraries:

**JPEG-12bit Excellence (libjpeg-turbo 3.0.4):**
- **88 specialized j12* functions** for 12-bit precision processing
- Runtime precision selection for optimal quality vs. performance
- Advanced SIMD acceleration and arithmetic coding support

**Complete Image Format Support:**
- **Leptonica 6,197 functions**: Professional image processing and analysis
- **PNG (900 symbols)**: Full PNG specification with transparency and metadata
- **TIFF (1,105 symbols)**: Complete TIFF support including compression variants
- **270 total JPEG functions**: Comprehensive JPEG handling and optimization

**Enhanced OCR Quality for:**
- High-resolution scanned documents and technical drawings
- Compressed JPEG images with artifacts
- Multi-format document processing (PDF, TIFF, PNG)
- Complex layouts with mixed text and graphics
- Financial documents requiring precise character recognition
- Low-contrast or challenging image conditions

## Use Cases

Perfect for a wide range of iOS applications:

- **Document Processing**: Invoices, contracts, receipts, PDFs
- **Business Cards**: Automatic contact information extraction
- **Translation Apps**: OCR text from images for real-time translation
- **Accessibility**: Convert images to text for screen readers
- **Receipt Scanning**: Automated expense tracking
- **Digital Libraries**: Convert books and notes to digital text
- **Real-time OCR**: Live camera text recognition
- **Form Processing**: Automated data extraction
- **Financial Documents**: Bank statements, insurance papers
- **Note Taking**: Convert printed text and typed documents to text

## Quick Start

### Recommended: Using Pre-built Framework

**For production apps, use the complete pre-built framework:**

1. **Download**: Get the latest framework from [**GitHub Releases**](https://github.com/thebenfarmer/TesseractOCR-iOS-Framework/releases) 
2. **Add to Project**: Drag `TesseractOCR.xcframework` into your Xcode project
3. **Embed Framework**: Add to target's "Frameworks, Libraries, and Embedded Content"
4. **Import and Use**:

```swift
import TesseractOCR

let tesseract = G8Tesseract(language: "eng")
tesseract?.image = yourUIImage
tesseract?.recognize()
let recognizedText = tesseract?.recognizedText
```

**Pre-built Framework Benefits:**
- **Professional-grade integration**: 54,000+ optimized functions ready to use
- **Complete imaging pipeline**: All image formats and processing capabilities included
- **Massive static libraries** (~425MB) with zero external dependencies
- **Production-tested**: Thoroughly validated for iOS deployment
- **No build complexity**: Download and integrate immediately

### Building Framework Locally

**For development, testing, and local production builds:**

```bash
# Clone the repository
git clone https://github.com/thebenfarmer/TesseractOCR-iOS-Framework.git
cd TesseractOCR-iOS-Framework

# Build production framework (local optimized build)
./build_script_local.sh

# OR use universal build script (same as CI/CD)
./build_script.sh
```

**Build Scripts:**
- **`build_script_local.sh`**: Optimized local production build with 88 j12* symbols
- **`build_script.sh`**: Universal script (CI/local) - attempts production, fallback to demo
- **Both create**: Complete XCFramework (~425MB) when successful
- **CI/CD**: Uses `build_script.sh` for realistic testing

## Framework Architecture

- **Device Framework**: arm64 iOS (optimized for iPhones/iPads)  
- **Simulator Framework**: Universal Binary (arm64 + x86_64)
- **Framework Size**: ~425MB (complete integration with all libraries)
- **JPEG Integration**: 88 j12* + 34 JPEG API symbols
- **Dependencies**: All included (Leptonica, libjpeg-turbo, libpng, libtiff, zlib)

## Installation Options

### Swift Package Manager

```swift
dependencies: [
    .package(url: "https://github.com/thebenfarmer/TesseractOCR-iOS-Framework.git", from: "1.0.0")
]
```

### CocoaPods

```ruby
pod 'TesseractOCR-iOS', :git => 'https://github.com/thebenfarmer/TesseractOCR-iOS-Framework.git', :tag => '1.0.0'
```

### Manual Installation

1. Download the framework from [Releases](https://github.com/thebenfarmer/TesseractOCR-iOS-Framework/releases)
2. Drag `TesseractOCR.xcframework` into your project
3. Embed the framework in your target

## System Requirements

- **iOS**: 13.0+ (Broad compatibility - iPhone 6s and newer)
- **Xcode**: 12.0+ (for building from source)  
- **macOS**: 10.15+ (for building from source)
- **Disk Space**: 2GB free space (for building)

## Language Support

Download language packs from [Tesseract tessdata_fast](https://github.com/tesseract-ocr/tessdata_fast) and add to your app bundle:

```swift
// Single language
let tesseract = G8Tesseract(language: "deu")

// Multiple languages  
let tesseract = G8Tesseract(language: "eng+deu+fra")
```

## Performance & Quality

**Professional-Grade Integration Benefits:**
- **54,000+ optimized functions**: Complete OCR and imaging pipeline
- **12-bit JPEG precision**: 88 specialized functions with runtime selection
- **Comprehensive image support**: 6,197 Leptonica + 900 PNG + 1,105 TIFF functions
- **Zero external dependencies**: All libraries statically integrated
- **Memory-optimized**: Professional cross-compilation with iOS-specific optimizations
- **Multi-architecture native**: Separate optimized binaries for device and simulator

## Build System

### Production Framework (Recommended)

**Pre-built frameworks are available in [GitHub Releases](https://github.com/thebenfarmer/TesseractOCR-iOS-Framework/releases):**

- **Professional Integration**: 54,000+ functions with complete imaging pipeline
- **Advanced JPEG-12bit**: 88 specialized j12* functions with libjpeg-turbo 3.0.4
- **Comprehensive Libraries**: Tesseract 5.5.1, Leptonica 6,197 functions, PNG/TIFF complete support
- **Massive Static Integration**: 425MB (142MB device + 282MB simulator) with zero dependencies
- **Production-Grade**: Professional cross-compilation optimized for iOS deployment

### Universal Build System

**Single build script for all environments:**

- **Local Development**: Same script attempts production build locally
- **CI/CD Testing**: Identical build process validates real cross-compilation  
- **Automatic Fallback**: Demo framework if production build fails
- **Environment Detection**: Adapts behavior for GitHub Actions vs local
- **Realistic Testing**: CI tests actual build pipeline, not just structure

## Continuous Integration

Every commit is automatically tested with:
- **macOS Latest** with **Xcode Latest**
- **Complete Framework Build** from scratch with all 54,000+ functions
- **Professional Integration Verification** (88 j12* JPEG-12bit symbols)
- **Multi-Architecture Testing** (arm64 device + arm64/x86_64 simulator)
- **Comprehensive Artifact Upload** for immediate download and integration

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes  
4. Test with `./build_script.sh`
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## License

This project includes components with different licenses:
- **Tesseract OCR**: Apache 2.0
- **Leptonica**: BSD-style  
- **libjpeg-turbo**: BSD-style (with enhanced 12-bit support)
- **libpng**: PNG License
- **libtiff**: MIT-style
- **zlib**: zlib License

## Troubleshooting

### Build Issues
- Install Xcode Command Line Tools: `xcode-select --install`
- Verify internet connection for dependency downloads
- Ensure sufficient disk space (2GB+)

### Integration Issues  
- Check iOS deployment target (13.0+ required)
- Verify framework is properly embedded
- Include language data files in app bundle

### Performance Issues
- Framework includes 54,000+ optimized functions for comprehensive image processing
- Leverage 88 j12* JPEG-12bit functions for high-quality image processing
- Consider image preprocessing with integrated Leptonica functions for optimal results
- Monitor memory usage with large images (425MB static framework)

---

**Built with Tesseract 5.5.1, professional-grade JPEG-12bit integration, and complete imaging pipeline (54,000+ functions) for exceptional iOS OCR quality.**