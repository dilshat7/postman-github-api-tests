# GitHub API Postman Collection

This collection contains automated tests for the GitHub API. It verifies authentication, creates a test repository, and then deletes it.

## Prerequisites

1.  **Postman**: Installed Postman application.
2.  **GitHub Token**:
    *   Create a Personal Access Token (PAT): [GitHub Settings -> Developer settings -> Personal access tokens -> Tokens (classic)](https://github.com/settings/tokens).
    *   **Scopes**: Select `repo` (Full control of private repositories) or `public_repo` (if you plan to create only public ones), and `user` (read:user).
    *   **Important**: Copy the token immediately; you will not be able to see it again.

## Installation and Run

1.  **Import Collection**:
    *   Click **Import** in Postman (top left).
    *   Drag and drop the `github_api_test.postman_collection.json` file or select it.

2.  **Configure Variables**:
    *   Click on the collection name **GitHub API Test** in the left sidebar.
    *   Go to the **Variables** tab.
    *   Find the `token` variable.
    *   Paste your GitHub PAT into the **Current Value** column.
    *   **Note**: For security reasons, the `token` field in the file is currently empty. You must insert your token before running.
    *   Leave `owner` and `repoName` variables empty — they will be populated automatically during test execution.
    *   Click **Save** (Ctrl+S).

3.  **Run Tests**:
    *   Click on the collection name **GitHub API Test** again.
    *   Click the **Run** button (top right, on the collection tab).
    *   In the "Runner" window, ensure all checkboxes are selected.
    *   Click **Run GitHub API Test**.

## What do the tests check?

1.  **Get Authenticated User**:
    *   Checks for status code 200.
    *   Retrieves the user login and saves it to the `owner` variable.
2.  **Create Repository**:
    *   Generates a unique repository name (e.g., `postman-auto-test-12345`).
    *   Sends a POST request.
    *   Checks for status code 201 (Created).
    *   Verifies that the repository was created with the correct name.
3.  **Delete Repository**:
    *   Uses the saved `owner` and `repoName`.
    *   Sends a DELETE request.
    *   Checks for status code 204 (No Content).

## Result

After execution, you should see **green** "PASS" badges next to each test in the Runner.
