## Keylogger Script

This script is a simple keylogger that captures keystrokes and saves them to a file named `keylog.txt`. Additionally, it sends the log file via email when the `Esc` key is pressed. Below is a detailed description of the script's functionality:

### Features

1. **Keystroke Logging**:
   - The script uses the `pynput` library to listen for keyboard events.
   - Keystrokes are recorded and appended to a file named `keylog.txt`.

2. **Email Notification**:
   - When the `Esc` key is pressed, the script stops logging and sends the `keylog.txt` file as an email attachment.
   - The email is sent using the `smtplib` library, with the email content and attachment handled by the `email.mime` modules.

### How It Works

1. **Logging Keystrokes**:
   - The `on_press` function captures each key press and writes it to `keylog.txt`.
   - The `on_release` function checks if the `Esc` key is pressed. If so, it triggers the `send_email` function and stops the listener.

2. **Sending Email**:
   - The `send_email` function constructs an email with the `keylog.txt` file attached.
   - It uses SMTP to send the email from a specified sender address to a recipient address.

### Usage

1. **Dependencies**:
   - Ensure you have the `pynput` and `smtplib` libraries installed. You can install `pynput` using pip:
     ```sh
     pip install pynput
     pip install smtplib
     ```

2. **Configuration**:
   - Update the `fromaddr`, `toaddr`, and SMTP server details in the `send_email` function with your own email credentials and server information.

3. **Running the Script**:
   - Run the script in your Python environment. It will start logging keystrokes immediately.
   - Press the `Esc` key to stop logging and send the email with the log file attached.

### Important Notes

- **Ethical Use**: This script should only be used for ethical purposes, such as monitoring your own devices or for educational purposes. Unauthorized use of keyloggers is illegal and unethical.
- **Security**: Ensure that your email credentials are stored securely and not hard-coded in the script for production use.

By following the above instructions, you can use this keylogger script to capture keystrokes and send the log file via email.
