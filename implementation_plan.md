# Implementation Plan - GitHub API Postman Autotest

A Postman Collection to automate testing of the GitHub REST API.

## Goal
Create a JSON file compatible with Postman (Colleciton v2.1) that performs automated checks on the GitHub API.

## Scope
- **Authentication**: Bearer Token (PAT).
- **Scenarios**:
  1. **Get User**: Verify authentication and check user details.
  2. **Create Repository**: Create a new repo with a random name (using dynamic variables).
  3. **Delete Repository**: Clean up the created repo.

## Proposed Changes

### [Artifacts]
#### [NEW] [github_api_test.postman_collection.json](file:///C:/Users/ddjab/.gemini/antigravity/brain/80cd7368-e1fa-4798-aaba-df40625533b4/github_api_test.postman_collection.json)
- Will contain the JSON structure for the collection.
- **Variables**: `baseUrl`, `token`, `repoName`, `owner`.
- **Scripts**:
    - *Pre-request*: Generate random strings for repo names.
    - *Tests*: Assert status codes (200, 201, 204), check JSON schema, verify data consistency.

#### [NEW] [README.md](file:///C:/Users/ddjab/.gemini/antigravity/brain/80cd7368-e1fa-4798-aaba-df40625533b4/README.md)
- Instructions on how to import into Postman.
- How to generate a GitHub PAT (Personal Access Token).
- How to set environment variables.

## Verification Plan
### Manual Verification
1. Import the JSON into Postman.
2. Set the `token` variable.
3. Run the collection using the "Run Collection" runner in Postman.
4. Verify all tests pass (Green status).
