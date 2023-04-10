# SecurityNinja

An app that checks a WordPress website for plugin versions, notifying the owner if updates are needed.

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#requirements">Requirements</a></li>
      <ul>
        <li><a href="#google-sheet">Google Sheet</a></li>
        <li><a href="#google-service-account">Google Service Account</a></li>
        <li><a href="#mailgun">Mailgun</a></li>
        <li><a href="#wordpress-setup">WordPress Setup</a></li>
      </ul>
    <li><a href="#local">Local</a></li>
    <li><a href="#production">Production</a></li>
  </ol>
</details>

## About The Project

SecurityNinja is a python-based web scraping tool used to evaluate the security of a WordPress website. The project parses through a Google Sheet containing entries that have a URL, username, and key to scan the website. A list of plugins that need to be updated is generated and then sent to the corresponding email on the Google Sheet.

## Requirements

### Google Sheet
   Create a Google Sheet with the following columns of data:
   - website url
   - username
   - application password
   - Email Address
   - LastChecked (default to 0)

   Variable(s):
   ```sh
   #ID_of_google_sheet from the URL: docs.google.com/spreadsheets/d/ID_of_google_sheet/edit...
   SHEET_ID = ID_of_google_sheet
   
   #name_of_sheet_to_use from name of individual sheet
   SHEET_NAME = name_of_sheet_to_use
   ```
### Google Service Account
   Create a Google Cloud project on console.cloud.google.com
   - Select **IAM & Admin** from the navigation menu
   - Select **Create a Project** and follow the steps to create a project
   
   Create a Google service account on console.cloud.google.com
   - Select **IAM & Admin** from the navigation menu
   - Select **Service Accounts**
   - Click **CREATE SERVICE ACCOUNT** at the top of the page

   Download the credentials.json file for your service account
   - Select **IAM & Admin** from the navigation menu
   - Select **Service Accounts**
   - Click on your service account
   - Navigate to the **KEYS** heading
   - From the **ADD KEY** dropdown select **Create new key**, and check **JSON**

   Share your Google Sheet with the service account
   
   Variable(s):
   ```sh
   #filepath to credentials.json
   GOOGLE_APPLICATION_CREDENTIALS = credentials.json
   ```
### Mailgun
   Create a free account at signup.mailgun.com

   Variable(s):
   ```sh
   #private_API_key from your mailgun account, under your profile select API Keys
   API_KEY = private_API_key
   
   #your_domain_name from Domains under the Sending dropdown
   MAILGUN_EMAIL = <mailgun@your_domain_name>
   MAILGUN_EMAIL_ENDPOINT = https://api.mailgun.net/v3/your_domain_name/messages
   ```
### WordPress Setup

Log in to your WordPress site with an admin user account
- On the dashboard, go to plugins
- Download the plugin "Application passwords" by George Stephanis
- Under the **Users** dropdown select **Profile**
- Scroll down to **Application Passwords**
- Enter a name in the **Add New Application Password** textbox and click **Add New**
- Save your Application Password and use it in submissions for the Google Sheet

## Local

To get a local copy up and running follow these simple example steps:
- Create necessary requirements by following the <a href="#requirements">Requirements</a>
- Ensure ```credentials.json``` filepath is accessible
- Run ```securityNinja.py``` through your local environment

## Production

To get a production copy up and running follow these simple example steps:
- Create necessary requirements by following the <a href="#requirements">Requirements</a>
- Store
<a href="#google-sheet">Google Sheet</a>,
<a href="#google-service-account">Google Service Account</a>, and
<a href="#mailgun">Mailgun</a> requirements securely in production environment
- Ensure ```credentials.json``` filepath is accessible
- Run ```securityNinja.py``` through your production environment

https://github.com/Global-Tech-Team/SecurityNinja
