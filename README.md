# Exploit Script for "Lab: Blind SQL injection with conditional responses"

This Python script automates the process of exploiting a blind SQL injection vulnerability in PortSwigger's Web Security Academy lab: **[Lab: Blind SQL injection with conditional responses](https://portswigger.net/web-security/sql-injection/blind/lab-conditional-responses)**.

**Disclaimer:**
---
This script is intended for educational purposes only, specifically for solving the aforementioned PortSwigger lab. Unauthorized use of this script against any system for which you do not have explicit permission is illegal and unethical. The author assumes no liability and is not responsible for any misuse or damage caused by this script. **USE RESPONSIBLY AND ETHICALLY.**
---

## Overview

The lab presents a scenario where an application uses a tracking cookie that is vulnerable to blind SQL injection. The vulnerability allows an attacker to infer information about the database by observing conditional responses (specifically, the presence or absence of a "Welcome back!" message) based on injected SQL queries.

This script automates the two main phases of the attack:
1.  Determining the length of the `administrator` user's password.
2.  Extracting each character of the `administrator` user's password.

## Features

* Accepts the target lab URL as input.
* Automatically retrieves initial `TrackingId` and `session` cookies.
* Systematically determines the password length by injecting SQL `LENGTH()` functions.
* Extracts each character of the password by injecting SQL `SUBSTRING()` functions and iterating through possible characters (`a-z`, `0-9`).
* Outputs the `administrator`'s username and the extracted password.
* Includes comments in the code for better understanding.

![image](/images/1.png)
![image](/images/2.png)
![image](/images/3.png)


## Prerequisites

* Python 3.x
* `requests` library:
    ```bash
    pip install requests
    ```

## How to Use

1.  **Clone the repository or download the script.**
    ```bash
    # git clone <your-repo-url>
    # cd <your-repo-directory>
    ```
2.  **Launch the target lab** on PortSwigger's Web Security Academy: [Lab: Blind SQL injection with conditional responses](https://portswigger.net/web-security/sql-injection/blind/lab-conditional-responses).
3.  **Run the script:**
    ```bash
    python your_script_name.py
    ```
    (Replace `your_script_name.py` with the actual name of your Python script file.)
4.  **Enter the Lab URL:** When prompted, paste the unique URL provided by PortSwigger for your lab instance (e.g., `https://0aXXXX.web-security-academy.net/`).
    ```
    Enter the Lab URL (e.g., [https://0a....web-security-academy.net/](https://0a....web-security-academy.net/)): <PASTE_YOUR_LAB_URL_HERE>
    ```
5.  The script will then attempt to:
    * Retrieve initial cookies.
    * Determine the password length for the `administrator` user.
    * Extract the password character by character.
6.  Upon successful completion, the script will print the `administrator`'s username and the extracted password.

    ```
    --- Exploit Finished ---
    [+] Username: administrator
    [+] Password: <extracted_password_here>
    ```

## Example of Script in Action (Placeholder)

*(This is where you can add a screenshot of the script running or successfully completing the lab. Ensure no sensitive or private information is included if you take a screenshot from a real session.)*
