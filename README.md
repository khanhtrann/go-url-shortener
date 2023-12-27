# Purpose
When an user sends an URL and/or a custom short to the server, it will generate a URL short and return it to the user. 

The app also implements rate limiting to prevent users from abuse the server (10 requests/30minutes/1 IP)
# How to Use
After cloning the git project, in the terminal, type `sudo docker compose up -d`. After a minute, it shall show that the containers have started successfully.    

Then, make request to the app, using `http://localhost:3000/api/v1`

Request body should look like this:

    {
        "url": "https://www.youtube.com/watch?v=n9iKoJ9ZE-Q",
    }

The server will return your shortened URL as below:

    {
        "url": "https://www.youtube.com/watch?v=n9iKoJ9ZE-Q",
        "short": "localhost:3000/501b1d",
        "expiry": 24,
        "rate_limit": 7,
        "rate_limit_reset": 24
    }
