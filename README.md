# AWS Rekognition Node.js Example

## Overview
This project demonstrates an application built with Node.js, integrating Amazon Rekognition for facial recognition capabilities. It features functionalities like indexing new faces, deleting faces, and primarily focuses on face detection using photo analysis.

## Getting Set Up
Before diving into the application, you need to set up an AWS account. Creating a collection and making API calls to Amazon Rekognition are part of the initial setup.

### Prerequisites
- Install Node.js in your environment.
- Ensure AWS CLI is properly installed and configured.

### Installation Steps
1. **Create a Collection in AWS**:
   Configure your AWS CLI with your credentials and create a collection with:
   ```sh
   aws rekognition create-collection --collection-id <your-collection-name>
   ```

2. **Clone the Repository**:
   ```sh
   git clone https://github.com/wanderaraujo/aws-rekognition-with-node-js.git
   ```

3. **Install Dependencies**:
   Navigate to the cloned directory and run:
   ```sh
   npm i
   ```

4. **Configure AWS Settings**:
   In the `/resource/config` directory, edit the `aws-config.js` file to specify your collection name and AWS region:
   ```javascript
   module.exports.collectionName = "YOUR COLLECTION NAME";
   module.exports.region = "YOUR REGION";
   ```

5. **Starting the Server**:
   Launch the application:
   ```sh
   npm start
   ```
   or
   ```sh
   node server
   ```
   The server will start on port 3000.

## API Usage
Interact with the application using an API client like Postman:

- **Detect Face**:
  ```
  POST /detect-face
  Content-Type: application/x-www-form-urlencoded

  photo=<base64 image string>
  ```

- **Index New Face**:
  ```
  POST /index-new-face
  Content-Type: application/x-www-form-urlencoded

  photo=<base64 image string>&id_user=<user ID>
  ```

- **Delete Face**:
  ```
  POST /delete-face
  Content-Type: application/x-www-form-urlencoded

  face_id=<face ID to delete>
  ```

**Note**: Exclude "image/png;base64," from the `photo` parameter.

## Built With
- **Node.js**: The core framework.
- **AWS Rekognition**: For facial recognition features.
- **AWS CLI**: To manage AWS resources.

## Author

- Wahab Khan

## License
