---

# OTPWizard Backend

This is a backend application designed to test the functionality of the `otpwizard` npm package. The backend provides endpoints for sending OTP emails and verifying OTPs.

## Installation

1. Clone the repository:

    ```bash
    git clone <repository_url>
    ```

2. Install dependencies:

    ```bash
    cd OTPWizard-Backend
    npm install
    ```

3. Set up environment variables:

    Create a `.env` file in the root directory of the project and provide the following environment variables:

    ```
    GMAIL_USER=your-email@gmail.com
    GMAIL_PASS=your-gmail-password
    ```

    Replace `your-email@gmail.com` and `your-gmail-password` with your actual Gmail credentials.

4. Start the server:

    ```bash
    npm start
    ```

## Usage

### Endpoints

- **POST `/sendMail`**: 
  - Description: Generates an OTP of specified length and sends it via email to the provided email address.
  - Request Body:
    ```json
    {
      "Otplength": 6,
      "emailInput": "recipient@example.com"
    }
    ```
  - Response:
    ```json
    {
      "msg": "Otp Send",
      "otp": "123456"
    }
    ```

- **POST `/verifyOtp`**:
  - Description: Verifies whether the provided OTP matches the expected OTP.
  - Request Body:
    ```json
    {
      "otpInput": "123456",
      "otp": "123456"
    }
    ```
  - Response:
    ```json
    {
      "msg": "checked",
      "isValid": true
    }
    ```

- **GET `/check`**:
  - Description: Checks if the server is running.
  - Response:
    ```json
    {
      "msg": "all ohk"
    }
    ```

## Contributing

Contributions are welcome! If you have any suggestions, bug reports, or feature requests, please open an issue or submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

---
