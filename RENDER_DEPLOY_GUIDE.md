# 🚀 How to Deploy DHASU-RUSHER on Render.com

Render is a great free hosting platform. Follow these steps carefully to deploy your bot for **FREE** 24/7.

## Step 1: Push Code to GitHub (Important!)
Render pulls code from GitHub, so you need to put this folder on GitHub first.

1.  **Create a GitHub Account** if you don't have one: [https://github.com/](https://github.com/)
2.  **Create a New Repository** (Name it something like `dhasu-bot`).
3.  **Upload Files**:
    *   You can upload via browser or use Git Desktop.
    *   Make sure `main.py`, `requirements.txt`, `render.yaml`, and the `PB2` / `APIS` folders are all uploaded.

## Step 2: Create a Render Account
1.  Go to [https://dashboard.render.com/](https://dashboard.render.com/)
2.  Sign up using your **GitHub** account (this makes it easier).

## Step 3: Deploy using Blueprint (Easiest Way)
I created a `render.yaml` file for you, which makes this super restart.

1.  In Render Dashboard, click **"New +"** and select **"Blueprint"**.
2.  Connect your GitHub repository (Grant permission if asked).
3.  Select your `dhasu-bot` repository.
4.  Render will automatically detect the `render.yaml` file.
5.  Click **"Apply"** or **"Create Service"**.

## Step 4: Manual Setup (If Blueprint fails)
If you prefer doing it manually:

1.  Click **"New +"** -> **"Web Service"**.
2.  Connect your GitHub Repo.
3.  **Settings**:
    *   **Name**: `dhasu-bot` (or any name)
    *   **Language**: `Python 3`
    *   **Build Command**: `pip install -r requirements.txt`
    *   **Start Command**: `python main.py`
    *   **Instance Type**: Free
4.  **Environment Variables** (Advanced):
    *   Key: `PORT`
    *   Value: `10000`
5.  Click **"Create Web Service"**.

## Step 5: Keep It Alive
*   Once deployed, Render will give you a URL (e.g., `https://dhasu-bot.onrender.com`).
*   **Important**: The Free Tier on Render "sleeps" if nobody visits the website for 15 minutes.
*   To keep it running 24/7, use a free "Uptime Monitor" service (like UptimeRobot or Cron-job.org) and set it to ping your Render URL every 5 minutes.

## Troubleshooting
*   **Logs**: Check the "Logs" tab in Render to see if the bot started correctly.
*   **Dependencies**: If it fails installation, check if `requirements.txt` is missing any library.
