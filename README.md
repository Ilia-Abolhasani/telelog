# LogGram

LogGram is a Python package for sending error logs and messages to Telegram channels or groups. It allows you to easily track errors and notifications in real-time using Telegram bots.

## Features

- Send error tracebacks to a specified Telegram channel or group
- Support for both synchronous and asynchronous message sending
- Configurable logging with file output
- Easy setup and integration

## Installation

```bash
pip install loggram
```
## Usage

1. **Create a Telegram Bot:**
   - Follow [this guide](https://core.telegram.org/bots#6-botfather) to create a new bot and obtain your bot token.
   - Add the bot to your desired channel or group and promote it as an admin.

2. **Initialize LogGram:**
   Here's an example of how to use LogGram in your project:

    ```python    
    from loggram import Loggram

    # Replace with your actual bot token and chat ID
    token = "YOUR_TELEGRAM_BOT_TOKEN"
    chat_id = "YOUR_TELEGRAM_CHAT_ID"

    # Create an instance of Loggram
    logger = Loggram(token, chat_id, verbose=True)

    # example
    try:
        1 / 0  # Code that raises an error
    except Exception as e:
        logger.send_traceback(str(e))
    ```

## Contributing
Contributions are welcome! If you find a bug or have a suggestion, please open an issue.


## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


## ⚠️ Security Notice

**Important:** Ensure the secure handling of your API keys and secrets. Do not hard code sensitive information directly in your source code. Consider using environment variables or a secure configuration management system to store and retrieve confidential data.

For example, you can use the `python-decouple` library along with a `.env` file to manage your project's configuration:

1. Install `python-decouple`:

    ```bash
    pip install python-decouple
    ```

2. Create a `.env` file in your project's root directory and add your secret information:

    ```ini
    SECRET_KEY=your_actual_secret_key
    ```

3. In your code, use `python-decouple` to access your configuration variables:

    ```python
    from decouple import config

    secret_key = config('SECRET_KEY')
    ```

By following secure practices, you help protect your application and sensitive data.
