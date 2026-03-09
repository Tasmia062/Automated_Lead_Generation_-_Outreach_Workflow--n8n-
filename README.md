# Automated Lead Generation & Outreach (n8n)

![n8n](https://img.shields.io/badge/Built%20With-n8n-EA4B71)
![Automation](https://img.shields.io/badge/Automation-Workflow-blue)
![License](https://img.shields.io/badge/License-MIT-green)

An end-to-end lead generation and outreach automation workflow built with n8n.
It automatically finds businesses from Google Maps, extracts contact information from their websites, enriches the data, and sends personalized outreach emails.
_____________________________________________________________________________________________________________________________

This workflow was originally built for an events company running yoga and wellness events across Europe who needed a scalable way to contact studios in multiple cities.

## Overview

Before this automation, the outreach process was completely manual:

1. Search businesses on Google Maps
2. Copy business name and website
3. Visit the website
4. Find an email address
5. Paste everything into a spreadsheet
6. Write and send individual outreach emails

This workflow automates the entire process.

Users simply enter a city and keyword in Google Sheets and for the personalized outreach emails user just adds the email template in the sheet and approves the leads to be sent. The system handles the rest automatically.

_____________________________________________________________________________________________________________________________

## Workflow Architecture

### The automation pipeline:

<img width="862" height="262" alt="automated_lead_generation_outreach_workflow" src="https://github.com/user-attachments/assets/d82ab95f-539d-4e8a-a4f2-38737945548c" />


### The automation performs the following steps:
1. Lead Discovery
   - Searches Google Maps for businesses based on a city and keyword
   - Example: Yoga studios in Berlin
2. Website Scraping
   - Visits each business website
   - Extracts:
     ~ Email addresses
     ~ Social media links
     ~ Contact information
3. Data Cleaning
   - Removes duplicate businesses
   - Filters invalid emails
   - Structures the data for outreach
4. Lead Storage
   - Saves all leads into Google Sheets
5. Lead Approval System
   - Team members review leads
   - When a lead is marked "Approved", the outreach process begins
6. AI Email Personalization
   - Uses GPT-4o to generate a personalized outreach email
   - Tailors each email based on the business
7. Automated Outreach
   - Sends emails through Gmail
   - Optionally generates a Shopify discount code for promotions
8. Tracking
   - Every lead is logged
   - Every email sent is recorded

____________________________________________________________________________________________________________________________

## Key Features

1. Automated Google Maps lead scraping
2. Website email extraction
3. Social media discovery
4. Duplicate lead removal
5. Google Sheets lead management
6. AI-generated personalized emails
7. Shopify discount code generation
8. Gmail email automation
9. Fully automated outreach pipeline

_____________________________________________________________________________________________________________________________

## Tech Stack
1. n8n – workflow automation
2. Google Sheets – lead database
3. Google Maps API – business discovery
4. OpenAI (GPT-4o) – email generation
5. Gmail API – email delivery
6. Shopify API – discount code creation

_____________________________________________________________________________________________________________________________

## Prepare the Google Sheet

Create a Google Sheet with two tabs.

### Input Sheet

Used to trigger lead searches.

Example columns:

<img width="919" height="192" alt="input_sheet" src="https://github.com/user-attachments/assets/ada7d49e-957c-4a92-9f17-c30b2c6a8125" />

### Leads Sheet

Where extracted leads are stored.

Example columns:

<img width="868" height="23" alt="lead_info" src="https://github.com/user-attachments/assets/4a144a67-8da0-41af-a48b-d97a05c2375c" />
<img width="927" height="122" alt="leadinfo" src="https://github.com/user-attachments/assets/bf114d33-31af-461f-a953-ea2485f3dda1" />

_____________________________________________________________________________________________________________________________

## Setup Instructions

### 1. Import the Workflow
- Download the workflow JSON file
- Open your n8n instance
- Go to Workflows → Import
- Upload the workflow file

### 2. Required Credentials
Before running the workflow, configure these credentials inside n8n:
- Google Sheets OAuth2
- Gmail OAuth2
- OpenAI API
- Google Maps API
- Shopify API (optional)

### 3. Configure Environment Variables
Replace the placeholders in the workflow with your credentials:
- YOUR_GOOGLE_MAPS_API_KEY
- YOUR_GOOGLE_SHEET_ID
- YOUR_OPENAI_API_KEY
- YOUR_SHOPIFY_CLIENT_ID
- YOUR_SHOPIFY_CLIENT_SECRET

_____________________________________________________________________________________________________________________________

## How the Outreach Works

- A user enters a city and keyword in the input sheet.
- The workflow searches Google Maps for matching businesses.
- It visits each website and extracts contact information.
- Leads are stored in Google Sheets.
- A team member marks a lead as Approved.
- The workflow generates a personalized email using GPT-4o.
- A Shopify discount code is created (optional).
- The email is sent automatically via Gmail.

_____________________________________________________________________________________________________________________________

## Real-World Use Cases

This workflow can automate outreach for many industries:
• Event organizers contacting venues  
• SaaS companies doing partnership outreach  
• Marketing agencies prospecting local businesses  
• Fitness brands contacting gyms and studios  
• Affiliate program recruitment  
• Local B2B lead generation
