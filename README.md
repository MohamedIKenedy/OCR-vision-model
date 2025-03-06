# OCR Application for Driver's Licenses and Passports

## Overview
This application provides Optical Character Recognition (OCR) capabilities specifically designed for extracting information from identification documents such as driver's licenses and passports. It uses Llama 3.2 Vision AI model through Ollama to process images and extract relevant information from these documents.

## Features
- Upload images of driver's licenses or passports
- Automatically extract text and relevant information from the documents
- Determine whether the uploaded document is a driver's license or passport
- Download extracted information in JSON or Markdown format
- Web-based user interface built with Streamlit
- Accessible via public URL through ngrok tunneling

## Prerequisites
- Google Colab environment
- Internet connection
- Ngrok authtoken (for creating public URL)

## Installation

The application is designed to run in a Google Colab environment. The setup process installs all necessary dependencies and configures the environment for running the OCR application.

### Step 1: Install Dependencies
The following dependencies will be installed:
- colab-xterm
- pciutils
- Ollama
- Streamlit
- pyngrok

### Step 2: Setup Ollama
```bash
curl https://ollama.ai/install.sh | sh
ollama serve &
ollama pull llama3.2-vision
```

### Step 3: Configure Ngrok
Replace "YOUR_AUTHTOKEN" in the script with your actual ngrok authtoken.
```python
ngrok.set_auth_token("YOUR_AUTHTOKEN")
```

## Usage

1. Run the Colab notebook to set up the environment and start the application
2. Access the application via the ngrok URL provided in the output
3. Upload an image of a driver's license or passport using the file uploader
4. Click "Extract Information" to process the image
5. View the extracted information displayed on the screen
6. Download the results in either JSON or Markdown format using the provided buttons

## How It Works

1. The application receives an uploaded image from the user
2. The image is encoded to base64 format
3. The encoded image is sent to the Llama 3.2 Vision model running locally via Ollama
4. The AI model analyzes the image and extracts relevant information from the document
5. The response is parsed and presented to the user in a readable format
6. Users can download the extracted data in their preferred format

## Technical Details

### Components
- **Streamlit**: Provides the web interface
- **Ollama**: Runs the AI model locally
- **Llama 3.2 Vision**: Performs the OCR and document analysis
- **ngrok**: Creates a tunnel to make the local Streamlit application publicly accessible

### File Structure
- `app.py`: Contains the Streamlit application code
- Supporting Python code for setup and configuration

### API Communication
The application communicates with the Ollama API running locally at:
```
http://localhost:11434/api/chat
```

## Troubleshooting

- If the application fails to start, check that all dependencies were installed correctly
- Ensure that the Ollama server is running with `ollama serve &`
- Verify that the Llama 3.2 Vision model has been successfully pulled with `ollama list`
- If the ngrok tunnel fails to establish, check that your authtoken is valid
- For image processing issues, ensure that the uploaded images are in JPG, JPEG, or PNG format

## Security Considerations

This application processes potentially sensitive identification documents. Consider the following security measures:
- Do not use this application on public or shared computers
- Ensure that processed documents are not stored unnecessarily
- The application runs locally through Colab, but is exposed via ngrok - be cautious about sharing the public URL

## License
MIT License

Copyright (c) 2025 Mohamed IFQIR

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Author
Mohamed IFQIR
https://medifqir.vercel.app/
