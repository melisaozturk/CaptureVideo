# CaptureVideo

An iOS camera application built with Swift that provides photo capture functionality with camera switching and flash control capabilities.

## Overview

CaptureVideo is a native iOS application that demonstrates the implementation of camera functionality using AVFoundation framework. The app allows users to capture photos using the device's front or rear camera with flash control options.

## Features

- Photo capture using device cameras
- Switch between front and rear cameras
- Flash control (on/off toggle)
- Real-time camera preview
- Automatic photo library integration
- Portrait orientation support
- Clean and minimal user interface

## Requirements

- iOS 13.0+
- Xcode 11.0+
- Swift 5.0+
- Physical iOS device with camera (required for testing camera features)

## Permissions

The app requires the following permissions to function properly:
- **Camera Access** (`NSCameraUsageDescription`): Required to capture photos
- **Photo Library Access** (`NSPhotoLibraryUsageDescription`): Required to save captured photos to the device

These permissions are already configured in `Info.plist`.
## Usage

### Capturing Photos

1. Launch the app
2. Grant camera and photo library permissions when prompted
3. Point the camera at your subject
4. Tap the "CAPTURE" button to take a photo
5. Photos are automatically saved to your device's photo library

### Switching Cameras

Tap the "Switch Camera" button to toggle between front and rear cameras.

### Flash Control

Tap the "Flash" button to toggle flash on/off (available when using rear camera).

## Key Components

### CameraController.swift

The core camera management class that handles:
- Camera device discovery and configuration
- Capture session management
- Photo output processing
- Camera switching logic
- Flash mode control

Key methods:
- `prepare(completionHandler:)` - Initializes and configures the camera session
- `displayPreview(on:)` - Shows camera preview on the provided view
- `captureImage(completion:)` - Captures a photo
- `switchCameras()` - Switches between front and rear cameras

### ViewController.swift

The main view controller that:
- Manages UI elements (preview, capture button)
- Handles user interactions
- Integrates CameraController with the UI
- Saves captured photos to the photo library

## Technical Implementation

The app uses:
- **AVFoundation** for camera capture and control
- **Photos** framework for photo library integration
- **UIKit** for user interface
- **AVCaptureSession** for managing camera input/output
- **AVCapturePhotoOutput** for photo capture
- **AVCaptureVideoPreviewLayer** for camera preview

## Error Handling

The app includes error handling for common scenarios:
- Camera unavailability
- Invalid capture sessions
- Device input errors
- Photo capture failures

Errors are defined in `CameraController.CameraControllerError` enum.

## Limitations

- Must be run on a physical device for camera functionality
- Simulator testing is limited to UI components only
- Video recording is not currently implemented (photo capture only)

## Acknowledgments

- Built using Apple's AVFoundation framework
- Camera implementation follows iOS best practices
