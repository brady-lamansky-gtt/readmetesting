# SecurityNinja

An app that checks Wordpress plugin versions and sends notifications if you need to update your wordpress site.

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
    </li>
    <li>
      <a href="#requirements">Requirements</a>
      <ul>
        <li><a href="#local">Local</a></li>
        <li><a href="#production">Production</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About The Project

SecurityNinja is a python-based web scraping tool used to evaluate the security of a Wordpress website. The project parses through a Google Sheet containing entries that have a url, username, and key to scan the website. Results are then emailed to the user connected to the Wordpress website, informing them of plugins that need to be updated.

## Requirements

1. Google sheet
   ```sh
   SHEET_ID = ID_of_google_sheet (from the url of the doc)
   SHEET_NAME = name_of_sheet_to_use (name of individual sheet)
   GOOGLE_APPLICATION_CREDENTIALS = filepath_to_credentials.json (from service account)
   ```
2. Google service account
   ```sh
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
   ```
3. Mailgun
   ```sh
   API_KEY =
   MAILGUN_EMAIL =
   MAILGUN_EMAIL_ENDPOINT =
   ```

## Local

This is an example of how you may give instructions on setting up your project locally.
To get a local copy up and running follow these simple example steps.

## Production

This is an example of how you may give instructions on setting up your project on production.
To get a production copy up and running follow these simple example steps.

## Wordpress Setup

How to setup Wordpress credentials to authenticate API
