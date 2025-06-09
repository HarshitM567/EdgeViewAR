# 📱 Real-Time Edge Detection Viewer
This Android application captures live camera frames, processes them in native C++ using OpenCV, and renders the output in real-time using OpenGL ES 2.0. Developed as part of the RnD Intern Assessment.

✅ Features Implemented
📸 Live Camera Feed using TextureView and Camera2 API

🔁 Real-Time Frame Processing via OpenCV (C++) using JNI

🎨 OpenGL ES 2.0 Rendering for displaying processed frames as textures

⚙️ Modular structure: separates camera logic, native image processing, and rendering


📷 Demo
Raw Feed	Edge Detection

⚙ Setup Instructions
Prerequisites
Android Studio (Arctic Fox or above)

Android NDK (r21 or above)

OpenCV 4.x (native build)

CMake, LLDB

Steps
Clone the repo:

bash
Copy
Edit
git clone https://github.com/yourusername/realtime-edge-detector.git
Set up OpenCV:

Download native OpenCV SDK from opencv.org

Extract and link it in CMakeLists.txt and jniLibs

Build and run on a physical Android device with Camera permissions enabled.

🧠 Architecture Overview
Frame Flow
Camera Frame Capture (Java/Kotlin)
Captured using TextureView and Camera2 API.

JNI Bridge
Raw frame data passed from Java to native C++ layer using JNI.

OpenCV Processing (C++)
Applied filters like Canny Edge Detection or Grayscale using OpenCV.

OpenGL Rendering (Java + Native)
Processed image uploaded to an OpenGL texture and rendered on screen in real-time.

🗂 Project Structure
arduino
Copy
Edit
📁 app/
   └── Camera setup, UI, JNI calls
📁 jni/
   └── C++ OpenCV frame processing logic
📁 gl/
   └── OpenGL rendering logic
🔧 Controls (Bonus)
Toggle Button → Switch between raw and processed feed

Logs FPS to Logcat (Log.d("FPS", "..."))

🏁 Build & Run
Tested on Android 10+ (API 29+)

Minimum FPS: ~15 on mid-range devices

🧪 Tech Stack
Android SDK (Java)

NDK + JNI

OpenCV (C++)

OpenGL ES 2.0

CMake
