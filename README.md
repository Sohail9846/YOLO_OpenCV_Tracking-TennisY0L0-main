# 🎾 Tennis Match Analysis & Visualization

This project uses deep learning and computer vision to **analyze tennis match videos**. It tracks players and the ball, detects key events, calculates advanced metrics (like shot speed and player speed), and renders a final video with real-time visual overlays.

---

## 📌 Key Features

- 🎯 **Player & Ball Detection** using YOLOv8 and custom-trained YOLOv5
- 🧠 **Court Line Detection** with keypoint regression model
- 📍 **Mini Court Visualization** to map actual player and ball positions
- ⚡ **Shot Speed Calculation** (in km/h)
- 🏃 **Player Movement Tracking**
- 📊 **Statistical Overlays** (live on video)
- 💾 **Detection Caching** using pickle stubs for faster debugging

---

## 📁 Project Structure

```
tennis_project/
├── input_videos/
│   └── input_video.mp4
├── output_videos/
│   └── output_video.avi
├── models/
│   ├── keypoints_model.pth         # Court line keypoint model
│   └── last.pt                     # YOLOv5 model for ball detection
├── tracker_stubs/
│   ├── player_detections.pkl
│   └── ball_detections.pkl
├── tennis_utils.py                 # Utility functions
├── mini_court.py                   # Mini court rendering
├── court_line_detector.py          # Keypoint prediction
├── trackers.py                     # Object tracking logic
├── constants.py                    # Measurement constants
└── main.py                         # 🔥 Main execution script
```

---

## ⚙️ How to Run

### 1. Clone the Repository
```bash
git clone https://github.com/Djier/tennis-match-analysis.git
cd tennis-match-analysis
```

### 2. Install Dependencies
Make sure you have Python 3.8+ and run:
```bash
pip install -r requirements.txt
```

### 3. Prepare Models
- Place your **YOLOv8 model** (for players) inside the root or pass the model path.
- Place the **YOLOv5 ball detection model** at: `models/last.pt`
- Place the **court keypoint regression model** at: `models/keypoints_model.pth`

### 4. Add Your Video
Drop your match video at:
```
input_videos/input_video.mp4
```

### 5. Run the Pipeline
```bash
python main.py
```

---

## 🏁 Output

After successful execution, the result is:
```
output_videos/output_video.avi
```

Each frame will include:
- ✅ Player bounding boxes
- 🎾 Ball tracking
- 📉 Shot speed & player speed overlays
- 🗺️ Mini court with real-time ball/player positions
- 📈 Frame-by-frame stats

---

## 📊 Stats Tracked

| Metric                       | Description                           |
|------------------------------|---------------------------------------|
| `player_1_last_shot_speed`   | Speed of last shot in km/h            |
| `player_2_last_player_speed` | Opponent movement speed (km/h)        |
| `player_1_number_of_shots`   | Cumulative shots hit                  |
| `player_1_average_shot_speed`| Real-time shot speed average          |

---

## 📦 Sample Requirements

Here’s a sample of required packages:

```txt
opencv-python
pandas
numpy
torch
ultralytics
```

(Include full list in `requirements.txt`)

---

## 🧠 Future Improvements

- [ ] Rally segmentation & serve detection
- [ ] Heatmaps for player coverage
- [ ] Integration with web dashboard
- [ ] Highlight reel generation

---

## 📄 License

MIT License — feel free to use, modify, and share.

---

## 🙌 Acknowledgements

- YOLOv8 by Ultralytics
- OpenCV community
- ATP/WTA match analytics inspiration

---

## 📬 Contact

For queries or collaboration, reach out at [prabalcaptprice@gmail.com](prabalcaptprice@gmail.com)
