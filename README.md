# GitHub User Data API Backend

Welcome to the **GitHub User Data API Backend**! This API allows you to manage and interact with GitHub user data by saving, updating, deleting, and retrieving user information stored in MongoDB. Additionally, you can find mutual followers between users and perform user searches based on various criteria.

## Features

- **Fetch GitHub User Data**: Save data from a GitHub profile into the database.
- **Retrieve Saved Data**: Access stored user data from the database.
- **Soft Delete & Restore Users**: Mark users as deleted and restore them if necessary.
- **Search Users**: Search for users in the database by their username.
- **Find Mutual Followers**: Identify mutual followers between users.
- **Sorting**: Sort users by their `created_at` date or any custom field.

## Technologies Used

- **Node.js**: JavaScript runtime environment for server-side scripting.
- **Express.js**: Web framework for building APIs.
- **MongoDB**: NoSQL database to store user data.
- **Axios**: Promise-based HTTP client for making requests to the GitHub API.
- **GitHub API**: Used to fetch user data from GitHub.

## Deployed Link

You can access the deployed API at:  
[https://autonomizebackend.onrender.com](https://autonomizebackend.onrender.com)

For local development, the backend will be running at `http://localhost:8080`.

## Installation & Setup

### Prerequisites

Before getting started, ensure you have the following:

- **Node.js** (v14 or higher)
- **MongoDB** (local or cloud instance)
- **GitHub Personal Access Token** (for API authentication)

API Endpoints
POST /save-user/:username
Fetches data from GitHub for the specified username and saves it to the database. If the user already exists, it checks if they have been deleted and restores them if necessary.

Parameters:
username (required): GitHub username.
Response:
Success: Returns saved user data.
Error: Returns an error message if user data cannot be fetched or saved.
GET /mutual-friends/:username
Finds mutual followers between the specified GitHub user and their followers.

Parameters:
username (required): GitHub username.
Response:
Success: Returns a list of mutual followers.
Error: Returns an error message if the followers cannot be retrieved.
GET /search-users
Searches for users in the database, with optional filtering by username.

Query Parameters:
username (optional): Filter results by username.
Response:
Success: Returns a list of matching users.
Error: Returns an error message if no users match or if there is an issue with the search.
DELETE /delete-user/:username
Soft deletes a user by marking them as deleted in the database.

Parameters:
username (required): GitHub username.
Response:
Success: Returns a confirmation message indicating the user has been deleted.
Error: Returns an error message if the user could not be deleted.
PATCH /update-user/:username
Updates the data of a user based on the provided information.

Parameters:

username (required): GitHub username.
Request Body: The updated data for the user.
Response:

Success: Returns the updated user data.
Error: Returns an error message if the update fails.
GET /users
Returns a list of all users sorted by a specified field.

Query Parameters:
sortBy (optional): The field to sort by (default: created_at).
Response:
Success: Returns a sorted list of users.
Error: Returns an error message if the users cannot be fetched or sorted.
