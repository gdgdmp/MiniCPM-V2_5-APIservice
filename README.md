# FastAPI Image Processing Service

## Project Overview

This is an image processing service built with FastAPI. Users can upload image files and provide a text prompt, and the service will use the `MiniCPM-Llama3` model to process the image and generate a corresponding text result.

## Installation Dependencies

Before running this project, make sure you have installed the following dependencies:

```bash
pip install fastapi uvicorn aiofiles aiohttp pillow transformers torch
How to Run
You can start the service with the following command:

bash
复制代码
uvicorn main:app --host 0.0.0.0 --port 8000 --log-level info
After starting the service, you can access the /process_file endpoint via a POST request.

API Usage
Endpoint: /process_file
Method: POST
Parameters:
prompt: Form parameter, the text prompt provided by the user.
file: Uploaded image file (supports BMP, JPG, etc.).
Response:
Success: Returns the generated text result in the format {"results": {"generated_text": "..."}}.
Failure: Returns HTTP error code and error message.
Notes
Ensure that GPU is correctly configured to accelerate the inference process.
Only specific image formats are supported.
