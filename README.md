# UMCS Discord Bot

## Overview
The UMCS Discord Bot allows members of the UWI Mona Computing Society to interact with the UMCS website and engage in activities like weekly coding challenges, project notifications, and job listings. The bot automates notifications, provides access to coding challenges, and ensures a smooth experience by limiting certain commands to a dedicated bot commands channel.

## Features

### 1. **Automated Project Notifications**
- **Description:** Automatically posts new projects from the UMCS website in a “Projects” channel.
- **Details:** Includes project title, description, and relevant links in real-time as they are posted on the website.

### 2. **Job and Internship Postings**
- **Commands:**
  - `/jobs list` – Show the latest job and internship opportunities from the website (only usable in the **Bot Commands** channel).
  - `/jobs info [job_id]` – Display detailed information on specific jobs.
- **Automated Notifications:** Job postings are automatically sent to the “Job-Opportunities” channel.

### 3. **Event and Newsletter Notifications**
- **Commands:**
  - `/events list` – Show upcoming UMCS events (only usable in the **Bot Commands** channel).
  - `/events signup [event_id]` – Enable users to sign up for events directly from Discord.
  - `/newsletter latest` – Retrieve the latest UMCS newsletter.
- **Automated Notifications:** Event reminders and newsletters are automatically posted in the **Announcements** channel.

### 4. **Weekly Coding Challenges**
- **Commands:**
  - `/challenge request [difficulty] [language]` – Post a coding challenge based on difficulty (easy, medium, hard) and optionally by programming language. If no language is specified, a language-agnostic challenge will be posted.
- **Details:**
  - Challenges are posted weekly in a “Weekly-Challenge” channel.
  - Admins can configure the challenge interval using `/admin challenge_interval [interval]`.
  - Solutions to the previous week’s challenges are posted one day before the next challenge is issued.

### 5. **User Dashboard Integration**
- **Commands:**
  - `/dashboard view` – Display a personalized dashboard (submitted projects, upcoming events, etc.) from the UMCS website (only usable in the **Bot Commands** channel).
  - `/dashboard submit_project` – Guide users through the project submission process.

### 6. **Admin Tools**
- **Commands (Admin Only):**
  - `/admin announce [message]` – Post announcements to both the website and Discord.
  - `/admin post_job [job_details]` – Post new job opportunities directly from Discord and sync with the website.

## Channel-Specific Usage
- **Bot Commands Channel:** Commands that display a lot of information, such as `/jobs list`, `/events list`, and `/dashboard view`, are restricted to a dedicated bot commands channel to avoid clutter in other channels.

## Technology Stack
- **Bot Framework:** discord.py
- **API:** Integrates with the UMCS website API for project, job, and event data.
- **Security:** User authentication is handled through OAuth2, with all communications secured via HTTPS.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/UMCS/umcs-discord-bot.git
   ```

2. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables for your Discord bot token, OAuth2 keys, and API keys.

4. Run the bot:

   ```bash
   python bot.py
   ```

## Configuration

- **Challenge Interval:** Admins can configure the challenge interval using the `/admin challenge_interval [interval]` command (e.g., weekly, daily).
- **Channel Restrictions:** Make sure to configure the bot so that commands requiring large output are restricted to the **Bot Commands** channel.

## Contribution

Feel free to contribute to the UMCS Discord Bot by submitting pull requests or reporting issues in the GitHub repository.

## License
This project is licensed under the MIT License.
