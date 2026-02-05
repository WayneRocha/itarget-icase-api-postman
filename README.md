# ITarget ICase API - Postman Collection

This repository contains the Postman collection and environment configurations for the ITarget ICase API.

## 📁 Repository Structure

```
.
├── ITarget-ICase-API.postman_collection.json  # Main API collection
├── environments/                               # Environment configurations
│   ├── Development.postman_environment.json   # Local development environment
│   ├── Staging.postman_environment.json       # Staging environment
│   └── Production.postman_environment.json    # Production environment
└── README.md                                   # This file
```

## 🚀 Getting Started

### Prerequisites

- [Postman](https://www.postman.com/downloads/) installed on your computer
- Access to the ITarget ICase API (development, staging, or production)

### Installation

1. **Clone this repository:**
   ```bash
   git clone https://github.com/WayneRocha/itarget-icase-api-postman.git
   cd itarget-icase-api-postman
   ```

2. **Import the collection in Postman:**
   - Open Postman
   - Click on "Import" button (top-left corner)
   - Select the `ITarget-ICase-API.postman_collection.json` file
   - Click "Import"

3. **Import the environment:**
   - Click on "Import" button again
   - Navigate to the `environments/` folder
   - Select the environment file you need (Development, Staging, or Production)
   - Click "Import"

4. **Select the environment:**
   - In Postman, use the environment dropdown (top-right corner)
   - Select the imported environment (e.g., "Development")

5. **Configure environment variables:**
   - Click on the "eye" icon next to the environment selector
   - Click "Edit" for your selected environment
   - Update the variables as needed (especially `username` and `password` for non-development environments)

## 📚 API Collection Structure

The collection is organized into the following folders:

### 1. Health Check
- **GET Health Status** - Check if the API is running

### 2. Authentication
- **POST Login** - Authenticate and receive an access token (automatically saved to environment)
- **POST Logout** - End the current session

### 3. Cases
- **GET All Cases** - Retrieve all cases
- **GET Case by ID** - Get a specific case
- **POST Create Case** - Create a new case
- **PUT Update Case** - Update an existing case
- **DELETE Case** - Delete a case

### 4. Users
- **GET All Users** - Retrieve all users
- **GET User by ID** - Get a specific user
- **POST Create User** - Create a new user
- **PUT Update User** - Update an existing user
- **DELETE User** - Delete a user

## 🔐 Authentication

Most endpoints require authentication. Follow these steps:

1. Execute the **POST Login** request in the Authentication folder
2. The auth token will be automatically saved to the `auth_token` environment variable
3. All authenticated requests will use this token in the Authorization header

## 🌍 Environments

### Development
- **Base URL:** `http://localhost:3000/api`
- **Purpose:** Local development and testing
- **Credentials:** Pre-configured with dev credentials

### Staging
- **Base URL:** `https://staging-api.itarget-icase.com/api`
- **Purpose:** Pre-production testing
- **Credentials:** Must be configured manually

### Production
- **Base URL:** `https://api.itarget-icase.com/api`
- **Purpose:** Production API access
- **Credentials:** Must be configured manually
- **⚠️ WARNING:** Use with caution!

## 📝 Environment Variables

The following variables are used across the collection:

| Variable | Description | Example |
|----------|-------------|---------|
| `base_url` | API base URL | `http://localhost:3000/api` |
| `username` | User's username for authentication | `dev_user` |
| `password` | User's password for authentication | `dev_password` |
| `auth_token` | Authentication token (auto-populated) | `eyJhbGc...` |
| `case_id` | ID of a case for testing | `1` |
| `user_id` | ID of a user for testing | `1` |

## 🔄 Running the Collection

### Manual Testing
1. Select an environment from the dropdown
2. Navigate through the folders
3. Click on any request and press "Send"

### Automated Testing with Newman

You can run the entire collection using Newman (Postman's CLI):

```bash
# Install Newman
npm install -g newman

# Run the collection with Development environment
newman run ITarget-ICase-API.postman_collection.json \
  -e environments/Development.postman_environment.json

# Run with a specific environment
newman run ITarget-ICase-API.postman_collection.json \
  -e environments/Staging.postman_environment.json
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/new-endpoint`)
3. Commit your changes (`git commit -am 'Add new endpoint'`)
4. Push to the branch (`git push origin feature/new-endpoint`)
5. Create a Pull Request

## 📄 License

This project is for internal use within the ITarget organization.

## 📞 Support

For issues or questions, please contact the ITarget development team.
