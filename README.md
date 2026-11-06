# Hi, I'm Gang Wang

**Software Engineer | Computer Vision | Robotics Perception**

I build perception software that runs on real sensors and robots, and the backend systems around it. Recent work covers GPU scene flow, RGB-D mapping on a mobile robot, and a kitchen system tied to live Square orders.

---

## Featured Projects

### [DeGraF Flow GPU](https://github.com/Richer211/DegrafFlowGPU)

GPU sparse-to-dense scene flow for a real conveyor, built from a CUDA DeGraF detector, RAFT, and InterpoNet.

**Highlights**
- Export RAFT and InterpoNet to ONNX and run them with TensorRT inside a C++ process, with CUDA feature extraction in the same binary.
- On KITTI 2015, optical-flow EPE dropped from 3.23 to 2.64, and scene-flow EPE3D from 0.257 m to 0.160 m.
- RealSense D435i on a fixed-speed belt: live status on CPU, offline scene flow on GPU, one shared IDLE/MOVING view. Empty belt stays IDLE; an object stays MOVING on the belt and returns to IDLE about 0.4 s after it drops into the bin.

### [PuzzleBot RGB-D SLAM](https://github.com/Richer211/puzzlebot-rgbd-slam)

Monocular visual odometry and offline RGB-D SLAM on a PuzzleBot with a RealSense D435i and a Jetson Nano 2GB.

**Highlights**
- Monocular pipeline in Python and OpenCV: Zhang calibration at about 0.32 px reprojection error, FAST and Lucas–Kanade tracking, RANSAC pose recovery. Tested on KITTI and on indoor robot video with turns, fast motion, and low texture.
- Capture on the Nano at 640×480 / 15 FPS. A converter writes depth-aligned ROS 2 bags. RTAB-Map runs in a fixed ROS 2 Humble Docker image.
- Two indoor maps: 44 nodes from a 44-second handheld pass (610 aligned frames), and 26 nodes from a 30-second on-robot drive. Mapping stays on the host because 2GB cannot hold the live pipeline.

### [Restaurant Kitchen Pass](https://github.com/Richer211/restaurant-kitchen-pass)

Kitchen pass for a real restaurant. Square orders land on a shared pickup list; waiters mark dishes taken on the pass screen.

**Highlights**
- Square OAuth and order sync by Square id, including incremental pulls, merges, cancellations, and business filters.
- Dish state is stored in SQLite and pushed to the ops page and the pass screen. Paid Square tickets are closed on sync so finished orders leave the active board.
- Ran the loop in the restaurant: Square ticket, kitchen, pickup, waiter collection.

### [Doc2Action AI Workspace](https://github.com/Richer211/DOC2ACTION)

LLM workspace that turns meeting notes, PRDs, and emails into summaries, action items, risks, and open questions.

**Highlights**
- FastAPI and Next.js, with OpenAI extraction, a rule-based fallback, semantic chunking, and source-grounded references.
- JWT login, API key support, SQLite, request logging, health checks, and an editable review step.
- Deployed with Docker, Vercel, Railway, and GitHub Actions. CI gates the backend deploy.

**Live app:** [doc-2-action.vercel.app](https://doc-2-action.vercel.app)  
**API docs:** [Railway Swagger UI](https://doc2action-production.up.railway.app/docs)

---

## Technical Focus

- **Languages:** Python, C++, JavaScript / TypeScript
- **Perception:** OpenCV, camera calibration, visual odometry, RGB-D SLAM (RTAB-Map), RealSense D435i, ROS 2, Jetson Nano, scene flow, RAFT, InterpoNet
- **Inference:** CUDA, ONNX, TensorRT, Docker
- **Backend:** FastAPI, REST APIs, SQLite, MySQL, Redis, WebSocket, JWT
- **Delivery:** Docker, GitHub Actions, Linux, Vercel, Railway

---

## Background

- MSc Scientific Computing and Data Analysis (Computer Vision and Robotics), Distinction — Durham University
- Backend and platform work on SaaS and private-cloud systems before the MSc

---

## Connect

- GitHub: [github.com/Richer211](https://github.com/Richer211)
- LinkedIn: [linkedin.com/in/gang-wang-b42b462b6](https://linkedin.com/in/gang-wang-b42b462b6)
