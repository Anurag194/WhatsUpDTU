
# WhatsUpDTU

A social networking platform with automated content moderation and context-based authentication system.



## Project Overview

The project is a social networking platform built using the MERN (MongoDB, Express.js, React.js, Node.js) stack. It incorporates two major features: an automated content moderation system and context-based authentication. These features are accompanied by common functionalities found in social media applications, such as profile creation, post creation and sharing, liking and commenting on posts, and following/unfollowing users.

### Automated Content Moderation

The platform's automated content moderation system utilizes various NLP (Natural Language Processing) APIs. These APIs include:

- Perspective API: Used for filtering spam, profanity, toxicity, harassment etc.
- TextRazor API: Integrated for content categorization.
- Hugging Face Interface API: Utilized with BART Large MNLI for content categorization.

A Flask application has been developed to provide similar functionality as the Hugging Face Interface API's classifier. The Flask app utilizes the BART Large MNLI model. It operates as a zero-shot classification pipeline with a PyTorch framework.

The system allows flexibility in choosing different services for API usage or disabling them without affecting overall functionality by using a common interface for interacting with the APIs.

When a user posts content, it undergoes a thorough filtering process to ensure compliance with the community guidelines. Additionally, users have the ability to report posts that they find inappropriate, which triggers a manual review process.

### Context-Based Authentication

The platform implements context-based authentication to enhance user account security. It takes into consideration user location, IP address, and device information for authentication purposes. Users can conveniently manage their devices directly from the platform. To ensure data privacy, this information is encrypted using the AES algorithm and securely stored in the database.

In case of a suspicious login attempt, users are promptly notified via email and are required to confirm their identity to protect against unauthorized access.
.



## Features

- [x] User authentication and authorization (JWT)
- [x] User profile creation and management
- [x] Post creation and management
- [x] Commenting on posts
- [x] Liking posts and comments
- [x] Following/unfollowing users
- [x] Reporting posts
- [x] Content moderation
- [x] Context-based authentication
- [x] Device management
- [x] Admin dashboard
- [x] Moderator dashboard
- [x] Email notifications


## Technologies

- React.js
- Redux
- Node.js
- Express.js
- MongoDB
- Tailwind CSS
- JWT Authentication
- Passport.js
- Nodemailer
- Crypto-js
- Azure Blob Storage
- Flask
- Hugging Face Transformers



## Getting Started

### Prerequisites

Before running the application, make sure you have the following installed:

- Node.js
- MongoDB or MongoDB Atlas account

### Installation

1. Clone the repository

```bash
git clone https://github.com/nz-m/WhatsUpDTU.git
```
2. Go to the project directory and install dependencies for both the client and server

```bash
cd client
npm install
```

```bash
cd server
npm install
```

3. Create a `.env` file in both the `client` and `server` directories and add the environment variables as shown in the `.env.example` files.
4. Start the server

```bash
cd server
npm start
```

5. Start the client

```bash
cd client
npm start
```


### Configuration

Run the `admin_tool.sh` script from the server directory with permissions for executing the script. This script is used for configuring the admin account, creating the initial communities, and other settings.
```bash
./admin_tool.sh
``` 

#### `.env` Variables

For email service of context-based authentication, the following variables are required:

```bash
EMAIL=
PASSWORD=
EMAIL_SERVICE=
```

For content moderation, you need the `PERSPECTIVE_API_KEY` and either the `INTERFACE_API_KEY` or `TEXTRAZOR_API_KEY`. Visit the following links to obtain the API keys:

- [Perspective API](https://developers.perspectiveapi.com/s/docs-get-started)
- [TextRazor API](https://www.textrazor.com/)
- [Hugging Face Interface API](https://huggingface.co/facebook/bart-large-mnli)

If you prefer, the Flask server can be run locally as an alternative to using the Hugging Face Interface API or TextRazor API. Refer to the `classifier_server` directory for more information.


>**Note:** Configuration for context-based authentication and content moderation features are **_not mandatory_** to run the application. However, these features will not be available if the configuration is not provided.


## Usage

### Admin

The admin dashboard can be accessed at the `/admin` route. Use the `admin_tool.sh` script to configure the admin account. The admin account can be used to manage moderators, communities, and perform other admin-related tasks. You can also enable/disable or switch API services using the admin dashboard.

=======
# WhatsUpDTU
>>>>>>> a6171e0db2b7fb83c1bc5090740bc982e8545d2e
