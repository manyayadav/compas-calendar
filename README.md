# 🧭 Compass

## Overview

### _Compass is Basic User Calendar System with Google Calendar Integration._

## Features

Here are the main features. Visit [app.compasscalendar.com](https://app.compasscalendar.com) to see them all in action with your own events

- 🔄 2-way sync with Google Calendar
- 🕒 Display events in local time
- 🏷️ Tagging events
- 🖍️ Resizing events, Task reordering, Drag & drop tasks & events
- ✉️ Email capture
- 🔐 Google OAuth authentication

## Setup & Guides

1. Clone the repo.
cd compass

2. Create .env file and add the credentials

3. Setup Accounts
Compass relies on a few external services. Let's start by creating accounts for those and adding the credentials to that environment file.

Google OAuth
Compass uses the Google Calendar API to import and sync events from GCal. Refer to 
https://developers.google.com/identity/protocols/oauth2/web-server for setting up crendentials- Client's URL and Client's Secret

4. MongoDB
Before using Mongo db, ensure you install it in your local machine.

User data is stored across a few MongoDB collections. These collections are created automatically at runtime, so you just have to create an account to get started.

Compass connects to MongoDB through the NodeJS driver.

Create a free MongoDB Atlas account

Get your Node.js driver connection string

When you get your connection string,scroll down to the Network access in the left sidebar and add your current ip address. Make sure you always include your ip address when you switch networks because your device ip v4 address changes from one ISP to another and from time to time.

Update the connection string in your .env file

5. Supertokens
Compass uses Supertokens to manage user sessions. This is what allows users to stay signed in between page refreshes. It also prompts reauthorization after an extended time away.

Supertokens offers many different authentication options (AKA: recipes). Compass only uses their managed session service, which means you don't have to worry about a lot of their onboarding. What we do need is to get the credentials to Supertokens Core, their managed-service.

Supertokens will provision the auth infrastructure in AWS for you, presenting a connection URI and API key afterwards. That's all we need to get started.

Create a free Supertokens account
Click trough the onboarding steps
If prompted for a recipe, select Passwordless
Select the Managed Core option
After your instance is configured, copy the connection URI and API key to your .env file

6. Start in Dev Mode
Pfew! That was a lot of setup. Now for the fun part. Run these commands from the root compass directory

Install dependencies
yarn

Start the backend in dev mode
yarn dev:backend

Open a separate terminal & start the web app in dev mode
yarn dev:web

Open the app in your browser: http://localhost:9080

Sign in with one of your authorized test Google accounts

If all goes well, Compass will:

Create a new user in MongoDB
Start a user session with Supertokens
Add the user's email to ConvertKit (if enabled)
Import events from the user's primary Google Calendar into MongoDB
Setup a sync channel to receive Google Calendar webhook notifications for the duration specified in the .env (if enabled)

