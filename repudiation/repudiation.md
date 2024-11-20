# Repudiation

The example demonstrates a vulnerability that can lead to repudiation by malicious users attempting to access the services provided by a server.

## Steps to reproduce

1. Install all dependencies

    `$ npm install`

2. Run the server __insecure.ts__.

3. Pretend to be a malicous user and interact with the services by sending requests from the browser.

4. Do you think your actions can be repudiated?

## For you to do

1. Briefly explain the vulnerability.

insecure.ts has lack of proper logging and tracking of user actions. This allows malicious users to deny (repudiate) their actions, as there is no reliable record of their activities.

2. Briefly explain why the vulnerability is addressed in __secure.ts__.

by implementing detailed logging of user actions. Each request and action is logged with a timestamp, user information, and the action performed, providing a reliable record that can be used to verify user activities.

3. Which design pattern is used in the secure version to address the vulnerability? Briefly explain how it works?

Logging pattern. This pattern involves recording significant events and actions within the application to a log file. In repudiation/secure.ts, middleware is used to log each request with details such as the request method, URL, user IP, and a timestamp. This ensures that all user actions are recorded and can be reviewed later to prevent repudiation.