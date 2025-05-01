# uni_ukr_mova_project

This project designed to showcase understanding and ability use such skills as **SQL**, **Docker**, **Python**, **external APIs**, and creating pathway for interactions with users (telegram bot / web-based dashboard). 

The bot integrates with [ukr-mova.in.ua](https://ukr-mova.in.ua) API to provide users definitions and examples of Ukrainian words.

Also, the project features mini web dashboard which visualizes word search statistics history in simple browser-based interface.

## Table of Contents

- [Features](#features)
- [Technologies](#technologies)
- [Installation](#installation)
- [API_Integration](#api_integration)
- [Showcase_examples](#showcase_examples)

---

## Features

This bot supports the following commands:


- `/search <word>` Search for Ukrainian word using the [ukr-mova.in.ua](https://ukr-mova.in.ua) API. Returns definition, example usage, and image (if available).

- `/stats`  
  Show the top 5 most frequently searched terms by all users.

- `/help`  
  Display usage instructions and available commands.

Behind the scenes, all search activity is logged to MySQL database. Statistics can be queried and returned as part of bot commands or viewed from web-based interface.

## Technologies

The project is built using the following core technologies:

- **Python 3.8** – Core language used for backend logic.
- **Docker** – Containerization for consistent environment setup.
- **MySQL** – Database for storing query stats & user data.
- **Flyway** – Database migration to manage schema changes.
- **Bootstrap** – Used in mini dashboard for UI.
- **REST API** – Integration with [ukr-mova.in.ua](https://ukr-mova.in.ua) for UA language data.


## Installation

Follow these steps to rub project locally:

1. Clone the repository:
   ```bash
   git clone ...

2. Create and configure the .env file`s:

    Create .env at ./front/ 
    ```bash
    # .env example
    flask_app_key=1234
    db_host=mysql
    db_user=root
    db_password=root
    db_database=my_db
    mail_host=mailhog
    mail_port=1025
    ```
    
    Create .env at ./telegram_bot/ 
    ```bash
    API_KEY=INSERT-SOME:SUPER-SECRET-KEY-HERE
    db_host=mysql
    db_user=root
    db_password=root
    db_database=my_db
    log_file_path=/var/log/myapp/myapp.log

3. Build and start the containers:


    Ensure docker virtualisation service is already running, then


    ```bash
    docker compose build
    docker compose up
    ```

## API_Integration

For those, who will reproduce code or experimenting:

https://ukr-mova.in.ua/api-new?route=examples

https://ukr-mova.in.ua/api-new?route=categories

## Showcase_examples

![telegram_bot](/examples/2.png)
![web_based_dashboard](/examples/1.png)
![db_content](/examples/3.png)