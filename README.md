# API_Intergration

This project is a Node.js application that integrates with Firebase Cloud Messaging (FCM) for sending push notifications. The application allows you to send notifications to specific devices or subscribe/unsubscribe devices to/from topics.

## Features

- **Send Push Notifications**: Send notifications to specific devices using their registration tokens.
- **Subscribe to Topics**: Manage device subscriptions to specific topics for targeted notifications.
- **Unsubscribe from Topics**: Remove devices from specific topics.

## Prerequisites

- **Node.js**: Make sure you have Node.js installed on your system.
- **Firebase Project**: You need a Firebase project with Firebase Cloud Messaging enabled.
- **Service Account Key**: A service account key JSON file from Firebase.

## Setup

1. **Clone the repository**:
    ```bash
    git clone https://github.com/kasidit-wansudon/API_Intergration.git
    cd API_Intergration
    ```

2. **Install dependencies**:
    ```bash
    npm install
    ```

3. **Add your Firebase service account key**:
    - Place your Firebase service account key JSON file in the `server/` directory.
    - The file should be named as `oppo-80086-fe15da6e828d.json` or update the code in `index.js` to reflect the correct file name.

4. **Configure environment variables** (optional):
    - If you have any sensitive data (such as API keys), store them in a `.env` file (which should be ignored by Git).

## Usage

- **Start the server**:
    ```bash
    npm start
    ```

- **Send Notification**:
    - Make a `POST` request to `/fcm/send` with the following payload:
    ```json
    {
      "token": "your_device_registration_token"
    }
    ```

- **Subscribe to a Topic**:
    - Make a `POST` request to `/subscribe-to-topic` with the following payload:
    ```json
    {
      "tokens": ["your_device_registration_token"],
      "topic": "your_topic_name"
    }
    ```

- **Unsubscribe from a Topic**:
    - Make a `POST` request to `/unsubscribe-to-topic` with the following payload:
    ```json
    {
      "tokens": ["your_device_registration_token"],
      "topic": "your_topic_name"
    }
    ```

- **Send Notification to a Topic**:
    - Make a `POST` request to `/send-to-topic` with the following payload:
    ```json
    {
      "topic": "your_topic_name"
    }
    ```

## Notes

- Ensure your Firebase project is properly configured with FCM enabled.
- Handle secrets and API keys securely. Avoid committing sensitive information directly to the repository.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

