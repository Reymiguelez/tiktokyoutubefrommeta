#Post Automation for YouTube Shorts, Instagram, and TikTok
Automated system for downloading, processing, and posting videos to multiple social media platforms. Ideal for content creators who want to repost podcast clips and viral videos.

## 📋 Features
- **Automatic Download**: Automatically collects videos from YouTube and TikTok
- **Video Processing**: Applies layout, watermark, and platform-specific optimizations
- **Multi-Platform Upload**: Simultaneous posting to YouTube Shorts, Instagram Reels, and Facebook
- **Smart Scheduling**: Control posting frequency with time windows
- **Visual Dashboard**: Streamlit interface for complete management
- **AI for Titles**: Title enhancer using LLM APIs
## 🛠️ Technologies
- **Python 3.12+**
- **yt-dlp**: Download videos from YouTube/TikTok
- **YouTube Data** API v3**: Upload to YouTube Shorts
- **Meta Graph API**: Upload to Instagram/Facebook
- **Streamlit**: Interactive Dashboard
- **APScheduler**: Task Scheduling
## 📁 Project Structure
```
onca-alfa/
├── main.py # Main entry point
├── app.py # Streamlit Dashboard
├── config.py # Centralized settings
├── requirements.txt # Python dependencies
├── .env # Environment variables
├── core/
│ └── logger.py # Logging system
├── services/
│ ├── database.py # SQLite database
│ ├── youtube_downloader.py # Download YouTube
│ ├── tiktok_downloader.py # Download TikTok
│ ├── youtube_uploader.py # Upload YouTube Shorts
│ ├── meta_uploader.py # Upload Instagram/Facebook
│ ├── title_enhancer.py # AI to improve titles
│ ├── watermark_service.py # Watermark
│ ├── layout_service.py # Video layout
│ ├── caption_service.py # Rotating captions
│ ├── posting_scheduler.py # Scheduling
│ └── youtube_processing.py # YouTube Processing
└── data/
├── shorts.db # Database
├── youtube_config.json # YouTube Configuration

├── tiktok_config.json # TikTok Configuration
├── caption_config.json # Captions
└── layout_config.json # Layout Configuration
```
## 🚀 Quick Start
### 1. Clone and Install
```bash
git clone (https://github.com/Reymiguelez/tiktokyoutubefrommeta)
cd tiktokyoutubefrommeta
pip install -r requirements.txt
```
### 2. Configure Environment Variables
```bash
cp .env.example .env
```
Edit the `.env` file with your settings:

```env
# YouTube API
YOUTUBE_CLIENT_SECRETS_FILE=client_secrets.json
# Meta API (Facebook/Instagram)
META_ACCESS_TOKEN=your_token
META_FB_PAGE_ID=your_page_id
META_IG_USER_ID=your_user_id
# Sources to Monitor
YOUTUBE_SOURCES='["https://youtube.com/@channel1", "https://youtube.com/@channel2"]'
TIKTOK_SOURCES='["@profile1", "@profile2"]'
# Posting Settings
CHECK_INTERVAL_MINUTES=60
DAILY_LIMIT=5
POST_DELAY_MINUTES=15
# IA (Optional)
LLM_ENABLED=false
LLM_API_KEY=sk-...
```
### 3. Configure the YouTube API
1. Access [Google Cloud Console](https://console.cloud.google.com/)
2. Create a project
3. Enable "YouTube Data API v3"
4. Create OAuth 2.0 credentials (Desktop App)
5. Download and save as `client_secrets.json`
### 4. Run
```bash
# Scheduled mode (continuous loop)
python main.py --run
# One-time check
python main.py --sync
# Post video from backlog now
python main.py --post-now
# Dashboard (in another terminal)
streamlit run app.py
```
## 📖 Using the Dashboard
The Streamlit dashboard allows:

- **Overview**: View bot status, daily posts, and control of Start/Stop
- **Social Media Config**: Configure YouTube/TikTok channels, captions, titles, and enabled platforms
- **Layout Editor**: Customize background and video position
- **Captions & Comments**: Manage caption library, hashtags, and pinned comments
## ⚙️ Scheduling Settings
The system offers two scheduling modes:
### Block Mode (Recommended)
- Group posts with long pauses
- Configurable time windows
- Daily posting limit
- Random variation to avoid detection
### Fixed Interval Mode
- Posts at regular intervals
- Ideal for even distribution
## 🔧 Development
```bash
# Virtual environment
python -m venv venv
source venv/bin/activate # Linux/Mac
venv\Scripts\activate # Windows
# Run
python main.py --run
# Dashboard
streamlit run app.py
```
## 📝 License
MIT License
## ⚠️ Notes
- This project requires compliance with the Terms of Service of the platforms
- Respect copyright and republication policies
- Use responsibly
Thinking: The documentation was successfully created. The LSP errors are just warnings about undefined variables in the original code.
