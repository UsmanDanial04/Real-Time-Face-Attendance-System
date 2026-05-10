# 📸 Face Recognition Attendance System

A robust face recognition-based attendance system built for Google Colab that uses computer vision and machine learning to automatically mark attendance by identifying registered faces through the webcam.
✨ Features

- 🎯 Real-time Face Detection - Instant face recognition through webcam
- 👤 Multi-Face Registration - Register multiple users with 5 sample images each
- 📊 Automated Attendance Logging - Automatic CSV-based attendance records
- 💾 Persistent Storage - Pickle-based face encoding storage
- 🔒 High Accuracy - Uses dlib's state-of-the-art face recognition
- 🌐 Browser-Based - Runs entirely in Google Colab with webcam access

# 🏗️ Project Structure
```
face-attendance-system/
│
├── attendance.ipynb              # Main Jupyter notebook
│
├── face_encodings.pkl           # Stored face encodings (generated)
├── attendance_log.csv           # Attendance records (generated)
│
└── registered_faces/            # Directory for face images (generated)
    ├── Ahmad_1.jpg
    ├── Ahmad_2.jpg
    ├── Danial_1.jpg
    └── ...
```

# 🚀 Getting Started

## Prerequisites

- Google account (for Google Colab)
- Webcam-enabled device
- Modern web browser with webcam permissions

# Installation

- Open Google Colab
```
   https://colab.research.google.com/
```
- Upload the notebook

- Upload attendance.ipynb to your Colab workspace
- Or open directly from GitHub


# Install Dependencies (Run the first cell)
```
python   !pip install face_recognition opencv-python-headless
```

# 📦 Required Libraries

LibraryVersionPurposeface_recognition1.3.0Face detection and recognitionopencv-python-headless4.xImage processingnumpyLatestNumerical computationsdlib19.xFace landmark detection

# 💻 Usage

1. Initialize the System
```
pythonsystem = FaceAttendanceSystemColab()
```

3. Register Users

- Register a new user with 5 face samples:
```
pythonsystem.register_face("John Doe", samples=5)
```
# Steps during registration:

- Click the "📸 Capture" button
- Position your face in the camera
- Repeat for all 5 samples
- Face encodings are automatically saved

# 3. Mark Attendance
```
pythonsystem.run_attendance()
```

# Process:

- Click "📸 Capture" to take photo
- System identifies the face
- Attendance is automatically logged with timestamp

# 4. View Attendance Records
```
pythonsystem.view_attendance()
```

# Output format:
```
Name       | Date       | Time     | Status
-----------|------------|----------|--------
Ahmad      | 2026-01-05 | 18:47:10 | Present
Danial     | 2026-01-05 | 18:47:48 | Present
```

# 🔧 Technical Details

1. Face Recognition Pipeline
2. mermaidgraph LR
A [Camera Capture] --> B[Face Detection]
B --> C[Face Encoding]
C --> D[Compare with Database]
D --> E{Match Found?}
E -->|Yes| F[Mark Attendance]
E -->|No| G[Unknown Face]

# Key Parameters

- Recognition Threshold: 0.55 (lower = stricter matching)
- Samples per Person: 5 (adjustable)
- Image Format: JPEG with 80% quality
- Encoding Model: dlib's ResNet-based model

# Storage Format

- Face Encodings (face_encodings.pkl):
```
python{
    "Person1": [encoding1, encoding2, ...],
    "Person2": [encoding1, encoding2, ...]
}
```
- Attendance Log (attendance_log.csv):
```
csvName,Date,Time,Status
Ahmad,2026-01-05,18:47:10,Present
```

# 🎯 How It Works

- Registration Phase
- Captures multiple face samples
- Extracts 128-dimensional face encodings using dlib
- Stores encodings in pickle file for persistence


# Recognition Phase

- Captures real-time image from webcam
- Detects and encodes faces
- Compares against stored encodings using Euclidean distance
- Marks attendance if distance < 0.55


# Logging Phase

- Records name, date, time, and status
- Appends to CSV file for easy export



# 🛡️ Best Practices

## For Better Accuracy
✅ Ensure good lighting during registration
✅ Capture faces from different angles
✅ Maintain consistent distance from camera
✅ Avoid occlusions (glasses, masks during registration)
✅ Use high-quality webcam

# Security Considerations

- 🔐 Store face_encodings.pkl securely
- 🔐 Implement access controls for attendance data
- 🔐 Consider encryption for sensitive face data
- 🔐 Regular backup of attendance logs

# 🐛 Troubleshooting

## Common Issues
- "No face detected" error

- Ensure proper lighting
- Move closer to camera
- Check camera permissions

## Face not recognized

- Re-register with more samples
- Adjust recognition threshold
- Ensure similar lighting conditions

## Webcam not working

- Grant browser camera permissions
- Check if camera is in use by another app
- Refresh the Colab page

# 📈 Future Enhancements

 - Multi-face attendance (group photos)
 - Export to Excel with formatting
 - Integration with Google Sheets
 - Email notifications for attendance
 - Dashboard for attendance analytics
 - Anti-spoofing measures
 - Mobile app support

# 🤝 Contributing

- Contributions are welcome! Please follow these steps:

Fork the repository
Create a feature branch (git checkout -b feature/AmazingFeature)
Commit your changes (git commit -m 'Add some AmazingFeature')
Push to the branch (git push origin feature/AmazingFeature)
Open a Pull Request

# 📄 License

 This project is licensed under the MIT License - see the LICENSE file for details.
👨‍💻 Author
Usman Danial

GitHub: https://github.com/UsmanDanial04

LinkedIn: www.linkedin.com/in/usman-danial-b4568b289

# 🙏 Acknowledgments

- face_recognition by Adam Geitgey
- dlib for face detection models
- Google Colab for providing free GPU resources

# 📞 Support
For issues and questions:

🐛 Open an issue

💬 Start a discussion


<div align="center">
⭐ Star this repository if you find it helpful!
Made with ❤️ by Usman Danial
</div>
