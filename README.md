# VidSnap 🎬

VidSnap is an AI-powered video reel generator that transforms your text and photos into engaging video content. Simply provide text and upload images, and VidSnap will create a video reel with AI-generated narration using ElevenLabs API and video processing with FFmpeg.

## Features ✨

- **AI Text-to-Speech**: Convert your text into natural-sounding audio using ElevenLabs API
- **Photo Integration**: Upload multiple photos to create dynamic video content
- **Automated Video Generation**: Combine audio and images into professional video reels using FFmpeg
- **User-Friendly Interface**: Clean and responsive web interface built with Bootstrap
- **Flask Backend**: Robust Python backend for handling all processing tasks

## Demo 🎥

[Add a demo GIF or link to your video here]

## Prerequisites 📋

Before you begin, ensure you have the following installed on your system:

- Python 3.7 or higher
- FFmpeg
- Git

## Installation 🚀

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/vidsnap.git
cd vidsnap
```

### 2. Create Virtual Environment

```bash
# Create virtual environment
python -m venv venv

# Activate virtual environment
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate
```

### 3. Install Python Dependencies

```bash
pip install -r requirements.txt
```

If you don't have a requirements.txt file, install the following packages:

```bash
pip install flask
pip install requests
pip install python-dotenv
pip install pillow
pip install ffmpeg-python
pip install elevenlabs
```

### 4. Install FFmpeg

#### Windows:
1. Download FFmpeg from [https://ffmpeg.org/download.html](https://ffmpeg.org/download.html)
2. Extract the files and add the `bin` folder to your system PATH
3. Verify installation: `ffmpeg -version`

#### macOS:
```bash
# Using Homebrew
brew install ffmpeg
```

#### Ubuntu/Debian:
```bash
sudo apt update
sudo apt install ffmpeg
```

### 5. Environment Variables

Create a `.env` file in the root directory and add your ElevenLabs API key:

```env
ELEVENLABS_API_KEY=your_elevenlabs_api_key_here
FLASK_SECRET_KEY=your_secret_key_here
FLASK_ENV=development
```

To get your ElevenLabs API key:
1. Sign up at [ElevenLabs](https://elevenlabs.io/)
2. Go to your profile settings
3. Copy your API key



## Project Structure 📁

```
vidsnap/
│
├── app.py                 # Main Flask application
├── requirements.txt       # Python dependencies
├── .env                  # Environment variables
├── .gitignore           # Git ignore file
│
├── templates/           # HTML templates
│   ├── index.html       # Main page
│   └── result.html      # Results page
│
├── static/             # Static files
│   ├── css/           # Custom CSS files
│   ├── js/            # Custom JavaScript files
│   ├── videos/        # Generated videos
│   └── audio/         # Generated audio files
│
├── uploads/           # User uploaded images
├── temp/             # Temporary files
└── utils/            # Utility functions
    ├── text_to_speech.py
    ├── video_generator.py
    └── file_handler.py
```

## Usage 🎯

### 1. Start the Application

```bash
python app.py
```

The application will be available at `http://localhost:5000`

### 2. Using VidSnap

1. **Enter Text**: Write the text you want to convert to speech
2. **Upload Photos**: Select multiple images for your video reel
3. **Generate Video**: Click the generate button and wait for processing
4. **Download**: Once complete, download your generated video reel

## Configuration ⚙️

### ElevenLabs Voice Settings

You can customize the voice settings in your application:

```python
# In your text-to-speech module
voice_settings = {
    "stability": 0.5,
    "similarity_boost": 0.75,
    "style": 0.0,
    "use_speaker_boost": True
}
```

### Video Settings

Customize video output settings:

```python
# Video configuration
VIDEO_CONFIG = {
    "fps": 30,
    "resolution": "1920x1080",
    "duration_per_image": 3,  # seconds
    "fade_duration": 0.5      # seconds
}
```

## API Endpoints 🔌

- `GET /` - Main page with upload form
- `POST /generate` - Process text and images to generate video
- `GET /download/<filename>` - Download generated video
- `GET /status/<task_id>` - Check processing status

## Error Handling 🚨

The application includes comprehensive error handling for:

- Invalid file formats
- ElevenLabs API errors
- FFmpeg processing errors
- File upload limits
- Network connectivity issues

## Contributing 🤝

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## Troubleshooting 🔧

### Common Issues

**1. FFmpeg not found**
```bash
# Verify FFmpeg installation
ffmpeg -version

# If not installed, follow installation steps above
```

**2. ElevenLabs API errors**
- Check your API key in `.env` file
- Verify your ElevenLabs account has credits
- Ensure API key has proper permissions

**3. File upload issues**
- Check file size limits in Flask configuration
- Ensure upload directory has write permissions
- Verify supported image formats (jpg, jpeg, png, gif)

**4. Video generation fails**
- Check FFmpeg installation and PATH
- Verify all dependencies are installed
- Check logs for specific error messages

## Acknowledgments 🙏

- [ElevenLabs](https://elevenlabs.io/) for AI voice generation
- [FFmpeg](https://ffmpeg.org/) for video processing
- [Flask](https://flask.palletsprojects.com/) for the web framework
- [Bootstrap](https://getbootstrap.com/) for the frontend styling

---

**Made with ❤️ by [Your Name]**

*Star ⭐ this repository if you find it helpful!*
