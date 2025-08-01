````markdown
# Soccer Player Re-Identification (15 sec Video)

## About

This is a small project where I had to track soccer players in a 15-second video. The main aim was to give a unique ID to each player and make sure that if a player leaves the frame and comes back, they still get the same ID.

---

## What I Did

- I used **YOLOv8** (`yolov8n.pt`) to detect players frame by frame in the video.
- After that, I used a **Vision Transformer (ViT)** to extract features from each player and match them using cosine similarity.
- Based on this, I assigned IDs and stored them frame-wise.
- Finally, I created a new video with the player bounding boxes and their IDs shown.

---

## Files in This Folder

- `main.ipynb`: Jupyter notebook with the full code (detection + tracking).
- `15sec_input_720p.mp4`: Input video.
- `yolov8n.pt`: YOLO model I used for detection.
- `yolo_detections.json`: Stores the bounding boxes for each frame.
- `tracked_output_new.mp4`: Final video with player tracking output.
- `tracking_results.json`: Metadata about tracked players.
- `Report`: Deccribes what remains and how i will proceede with more time/resources.

---

## How to Run

1. Make sure you have Python installed.
2. Install the required libraries:

```bash
pip install torch torchvision transformers opencv-python ultralytics
````

3. Open `main.ipynb` using Jupyter Notebook or Jupyter Lab.
4. Just run the notebook cells one by one. It will:

   * Detect players using YOLO
   * Assign IDs using re-identification logic
   * Save detections and output video
