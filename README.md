# SecurityNinja

An app that checks a Wordpress website for plugin versions, notifying the owner if updates are needed.

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#requirements">Requirements</a></li>
      <ul>
        <li><a href="#google-sheet">Google Sheet</a></li>
        <li><a href="#google-service-account">Google Service Account</a></li>
        <li><a href="#mailgun">Mailgun</a></li>
        <li><a href="#wordpress-setup">Wordpress Setup</a></li>
      </ul>
    <li><a href="#local">Local</a></li>
    <li><a href="#production">Production</a></li>
  </ol>
</details>

## About The Project

SecurityNinja is a python-based web scraping tool used to evaluate the security of a Wordpress website. The project parses through a Google Sheet containing entries that have a url, username, and key to scan the website. Results are then emailed to the user connected to the Wordpress website, informing them of plugins that need to be updated.

## Requirements

### Google Sheet

   Variable(s):
   ```sh
   SHEET_ID = ID_of_google_sheet (from the url of the doc)
   SHEET_NAME = name_of_sheet_to_use (name of individual sheet)
   ```
### Google Service Account
   Create a Google service account on console.cloud.google.com
   - Select APIs & Services from the navigation menu
   - Select Credentials
   - Create Credentials -> Service account

   Download the credentials.json file
   - Select IAM & Admin from the navigation menu
   - Select Service Accounts
   - Click on your service account
   - Under Keys, Add Key, Create new key, JSON

   Share your Google Sheet with the service account
   
   Variable(s):
   ```sh
   GOOGLE_APPLICATION_CREDENTIALS = filepath_to_credentials.json
   ```
### Mailgun

   Variable(s):
   ```sh
   API_KEY =
   MAILGUN_EMAIL =
   MAILGUN_EMAIL_ENDPOINT =
   ```
### Wordpress Setup

How to setup Wordpress credentials to authenticate API
- Wordpress API Key on Google Form submission rather than password

## Local

This is an example of how you may give instructions on setting up your project locally.

To get a local copy up and running follow these simple example steps:
- Create necessary requirements by following the Requirements listed earlier in the README file.
- Ensure your credentials.json filepath is accessible.
- Run securityNinja.py

## Production

This is an example of how you may give instructions on setting up your project on production.

To get a production copy up and running follow these simple example steps:
- Create necessary requirements by following the Requirements listed earlier in the README file.
- Store Google sheet, Google service account, and Mailgun requirements securely in production environment.
- Ensure your credentials.json filepath is accessible.
- Run securityNinja.py

https://github.com/Global-Tech-Team/SecurityNinja
