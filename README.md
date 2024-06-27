# Rembg API

This project provides a simple Flask-based API for removing backgrounds from images using the `rembg` library. The API takes an image file in a POST request and returns the processed image with the background removed.

## Features

- Remove background from images
- Dockerized for easy deployment
- Simple and easy-to-use API

## Requirements

- Python 3.12
- Docker (optional, for containerized deployment)

## Setup

### Local Setup

1. **Clone the repository**:
    ```sh
    git clone https://github.com/weixianggoh/rembg-api
    cd rembg-api
    ```

2. **Create and activate a virtual environment**:
    ```sh
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install dependencies**:
    ```sh
    pip install -r requirements.txt
    ```

4. **Run the Flask application**:
    ```sh
    python app.py
    ```

5. **Test the API**:
    ```sh
    curl -X POST -F "file=@path_to_your_image_file" http://127.0.0.1:5000/remove-bg --output output.png
    ```

### Docker Setup

1. **Clone the repository**:
    ```sh
    git clone https://github.com/weixianggoh/rembg-api
    cd rembg-api
    ```

2. **Build the Docker image**:
    ```sh
    docker build -t rembg-api .
    ```

3. **Run the Docker container**:
    ```sh
    docker run -d -p 5000:5000 --name rembg-api-container rembg-api
    ```

4. **Test the API**:
    ```sh
    curl -X POST -F "file=@path_to_your_image_file" http://127.0.0.1:5000/remove-bg --output output.png
    ```

## API Endpoints

### Remove Background

- **URL**: `/remove-bg`
- **Method**: `POST`
- **Form Data**:
    - `file`: The image file to process
- **Response**: The processed image with the background removed

### Root

- **URL**: `/`
- **Method**: `GET`
- **Response**: A simple message to confirm the API is running

## Example Usage

```sh
curl -X POST -F "file=@path_to_your_image_file" http://127.0.0.1:5001/remove-bg --output output.png
