# Privilege Escalation

The example demonstrates a privilege escalation vulnerability and how to exploit it.

## Steps to reproduce

1. Install all dependencies

    `$ npm install`

2. Start the **insecure.ts** server

    `$ npx ts-node insecure.ts`

3. In the browser, send a GET request

    ```
        http://localhost:3000/send-form
    ```

4. Try different UserIds and see which one gives you authorized access to change the role of that user.

## For you to do

Answer the following:

1. Briefly explain the potential vulnerabilities in **insecure.ts**

insecure.ts is vulnerable to privilege escalation due to insecure authentication and authorization checks. It relies solely on user-provided IDs and roles without verifying the authenticity of the user.

2. Briefly explain how a malicious attacker can exploit them.

attacker can exploit this vulnerability by sending a POST request with a different user ID and role, such as userId = 1 & newRole = admin, to escalate their privileges and gain unauthorized access to administrative functions.

3. Briefly explain the defensive techniques used in **secure.ts** to prevent the privilege escalation vulnerability?

secure.ts prevents privilege escalation by implementing session-based authentication and authorization. It verifies the logged-in user's session and ensures that only users with the 'admin' role can update roles.
