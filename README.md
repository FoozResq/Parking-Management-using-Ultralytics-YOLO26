# Parking-Management-using-Ultralytics-YOLO26
# 🚗 AI-Powered Parking Management System using Ultralytics YOLO

An intelligent, real-time computer vision solution that automates parking lot monitoring, space utilization tracking, and vehicle classification using state-of-the-art object detection.

## 🌟 Key Features
* **Real-Time Occupancy Detection:** Monitors parking zones via video/camera feeds to instantly classify spaces as `Vacant` or `Occupied`.
* **Custom Region of Interest (ROI) Mapping:** Defines specific bounding zones (polygons) for individual parking spots to eliminate detection noise.
* **Vehicle Classification:** Distinguishes between cars, trucks, and motorcycles to analyze lot usage behavior.
* **Analytical Logging:** Outputs real-time lot occupancy metrics, timestamps, and turnover rates to a structured database.

## 🛠️ Tech Stack & Architecture
* **Computer Vision Engine:** Python & Ultralytics YOLO 
* **Core Libraries:** OpenCV (video stream processing, ROI polygon overlay), NumPy, Pandas
* **Data Layer:** SQL Server / PostgreSQL (for historical occupancy logging and analytics)
* **Visualization:** (Optional) Power BI dashboard connected to the SQL database for live tracking of lot KPIs.

## 🧠 How It Works (Pipeline)
1. **Stream Ingestion:** Captures frames from a camera feed or video file using OpenCV.
2. **ROI Masking:** A static configuration maps out the coordinate polygons of each parking space.
3. **YOLO Inference:** The Ultralytics YOLO model detects vehicle bounding boxes across the entire frame.
4. **Intersection Over Union (IoU) Logic:** The system calculates the overlap between the detected vehicles and the pre-defined parking space polygons. If the overlap cross a threshold, the spot is marked **Occupied**.
5. **Data Push:** The live count of free vs. occupied spots is sent directly to the data layer.

## 📦 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/yolo-parking-management.git](https://github.com/your-username/yolo-parking-management.git)
   cd yolo-parking-management
