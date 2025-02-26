Apple & Banana Detection API (FastAPI + OpenCV)
⚠️ Work in Progress – Not Fully Functional Yet
📌 Overview
This project extends the previous Apple Detection API by adding Banana Detection and implementing two detection methods:

Color & Shape Analysis – Detects apples and bananas based on color segmentation and contour detection.
Template Matching – Compares input images with pre-saved apple/banana templates for detection.
🚧 Current Status: The program is still in development, with several issues preventing full functionality. A new version with improved accuracy and stability will be released in the next update.

❌ Known Issues & Challenges
🔴 Template Matching Not Working Properly – The detection accuracy is inconsistent, and cv2.matchTemplate() fails on some images.
🔴 File Path Issues – OpenCV (cv2.imread()) fails to load template images due to incorrect relative paths.
🔴 FastAPI Response Errors – StreamingResponse caused serialization issues, requiring a workaround to return processed images.
🔴 Contour-Based Detection Needs Optimization – The algorithm sometimes misclassifies objects due to lighting and size variations.
🔴 Jupyter Notebook Compatibility – Running FastAPI inside Jupyter required nest_asyncio, but stability issues remain.

📌 Next Update: The next version will address these issues with improved file handling, better error handling, and optimized detection logic.

🛠️ Technologies Used
FastAPI → Web API for image processing requests
OpenCV → Classical computer vision for object detection
NumPy → Image manipulation and mathematical operations
Uvicorn → ASGI server for running FastAPI
Jupyter Notebook → Development environment
📡 API Endpoints
Method	Endpoint	Description
POST	/detect_fruits	Upload an image and attempt to detect apples and bananas
GET	/download/color	Download processed color-based detection image
GET	/download/template	Download template-matching result
📌 Example Request (/detect_fruits)
bash
Copy
Edit
curl -X 'POST' 'http://127.0.0.1:8000/detect_fruits' \
  -H 'accept: application/json' \
  -H 'Content-Type: multipart/form-data' \
  -F 'file=@test.jpg'
📌 Example JSON Response (Currently Inaccurate Due to Bugs)
json
Copy
Edit
{
  "color": {"apple": 1, "banana": 0},
  "template": {"apple": 0, "banana": 2}
}
🔄 Planned Fixes & Enhancements
🔹 Fix file path issues – Ensure cv2.imread() properly loads template images.
🔹 Improve template matching – Adjust scaling & thresholding to reduce false negatives.
🔹 Enhance contour-based detection – Add more shape filtering to improve accuracy.
🔹 Refactor FastAPI response handling – Fix StreamingResponse and serialization issues.
🔹 Optimize API performance – Reduce latency and improve processing speed.

📌 How to Run Locally
bash
Copy
Edit
# Clone the repository
git clone https://github.com/your-username/fruit-detection-api.git
cd fruit-detection-api

# Install dependencies
pip install -r requirements.txt

# Run the API
uvicorn main:app --reload

# Open API docs
http://127.0.0.1:8000/docs
👨‍💻 Author

Guneet Singh 
https://www.linkedin.com/in/guneet-singh-16a5b5225/
guneetsingh792@gmail.com

🚀 Why This Project?
Despite the challenges, this project demonstrates problem-solving skills, computer vision techniques, and API development expertise. The next update will bring an improved, functional version.

🚀 Ideal for companies looking for Python engineers skilled in FastAPI, OpenCV, and image processing!

📢 Want to Collaborate?
This project is still evolving! Contributions, suggestions, and issue reports are welcome. Fork, star, or open an issue to help improve it. 🚀✨

This README now clearly communicates that the project is still in progress, outlines the issues, and sets expectations for the next update—a great way to show companies how you approach debugging and iteration.

Would you like any additional formatting or details? 🚀
