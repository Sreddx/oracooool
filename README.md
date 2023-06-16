
# Oracooool Formula 1 web app:

Web application that allows people to learn about the formula 1 rules, make predictions and share predictions with their friends.  


Made by: Sebastian Rojas Salazar, Pablo Blanco, Diego Velazquez, Jaime Rodriguez and Jesus Palomino for the Development of advanced apps course.

It includes the following features:  

- Information about the most important Formula 1 rules.
- Information about the most recent drivers, teams and circuits up to 2023.
- Chatbot that allows users to ask anything about the sport.
- Predictions module that is powered by a machine learning model trained with historical data.
- User login to save predictions made by the user that can be shared with friends and groups to score up points. 

## Installation

### Set up .env

```plaintext
# Flask
FLASK_SESSION_SECRET_KEY=''
FLASK_JWT_SESSION_SECRET_KEY=''

# Postgres  
DB_HOST=''
DB_NAME=''
DB_USER=''
DB_PASSWORD=''
DB_PORT=''
```
### Back end
- Create a python virtual environment and install requirements.txt.
- Run `scripts/flask.sh` to set up the back end.
### Database
- Run `scripts/postgres.sh` to create db container
- Connect to DB and run scripts in sql folder (base.sql, teams.sql, drivers.sql,...) In order

### Front end  
- Install packages in front end folder with `npm install`
- Run `npm start`
