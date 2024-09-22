# 📅 CalSync - Calendar Organisation and Management for Personal Activities and Scheduling

## Overview

### _CALSYNC is Basic User Calendar System with Google Calendar Integration._

## Features

- 🔄 2-way sync with Google Calendar
- 🕒 Display events in local time
- 🏷️ Tagging events
- 🖍️ Resizing events, Task reordering, Drag & drop tasks & events
- ✉️ Email capture
- 🔐 Google OAuth authentication

## Setup & Guides

### 1. **Clone the repo.**

```bash
git clone https://github.com/manyayadav/compas-calendar.git
cd compas
```

### 2. Create .env file and add the credentials

### 3. Setup Accounts
CALSYNC relies on a few external services. Let's start by creating accounts for those and adding the credentials to that environment file.

Google OAuth:
CALSYNC uses the Google Calendar API to import and sync events from GCal. Refer to 
https://developers.google.com/identity/protocols/oauth2/web-server for setting up crendentials- Client's URL and Client's Secret

### 4. MongoDB
CALSYNC connects to MongoDB through the NodeJS driver.

Create a free MongoDB Atlas account

Get your Node.js driver connection string

When you get your connection string,scroll down to the Network access in the left sidebar and add your current ip address. 

Update the connection string in your .env file

### 5. Supertokens
Supertokens offers many different authentication options (AKA: recipes). 
Create a free Supertokens account and select the Managed Core option
After your instance is configured, copy the connection URI and API key to your .env file

### 6. Start in Dev Mode
Run these commands from the root COMPAS directory

#### **Install dependencies**

```bash
yarn
```

#### **Start the backend in dev mode**

```bash
yarn dev:backend
```

#### **Open a separate terminal & start the web app in dev mode**

```bash
yarn dev:web
```

#### **Open the app in your browser:**

[http://localhost:9080](http://localhost:3000)

Sign in with one of your authorized test Google accounts.


