### IITK Attendence App

React-based web application for managing student attendance. It includes features for logging in, marking attendance, adding students, and retrieving attendance records, all features using a face-recognition by python with flask backend

-- By this_is_mjk Manas Jain Kuniya

### Watch the video to learn and use

[![Watch the video](https://raw.githubusercontent.com/this-is-mjk/Attendance-App-Task/main/useDemo/thumbnail.png)](https://youtu.be/NdP8Q0V74HA)

### Set Up

Ensure you have python and npm installed properly.
run the following commands after clonning the repository

```
cd Attendance-App-Task
cd backend
pip install -r requirements.txt
python3 app.py
```

open a new terminal and reach Attendance-App-Task

```
npm install
npm start
```

### Dependencies

1. python3
2. npm
3. React
4. Axios
5. Material-UI
6. js-cookie
7. MongoDB compass

## Components

1. Home.js
   main component, handles the application's logic and renders the appropriate UI elements based on the user's state (logged in, admin, etc.).

2. alert.js
   Displays alert messages to the user based on the response recieved form server.

3. attendenceTable.js
   Renders a table with attendance data recieved

4. camera.js
   Handles the webcam functionality for showing the webcam image on the page

5. inputID.js
   Input field component for entering the roll number.

6. request.js
   Contains functions for sending HTTP requests to the backend server with fixed parameters

7. createFormData.js
   function to create FormData object from the roll number and webcam image, to send in the request

8. requestCameraPermission.js
   Requests camera access permissions if the browser do not provide the permission

9. infoToggle.js
   toggling additional information on the UI, just for looks and info 😀

10. loadScreen.js
    Loading screen component displayed during data fetching.

### Features

1.  User Authentication: JWT-based authentication, workes with postman, issues with the react frontend
2.  Face Detection and verification
3.  Attendance Management
4.  Admin Power of Adding students, getting attendence and mark absent all

### Used technologies

1. Backend: Flask
2. Database: MongoDB
3. Facial Recognition: OpenCV, DeepFace
4. Token Management: JWT

## Backend

### API Endpoints

1. POST /login - Login using roll number and webcam image.
2. POST /mark-attendence - Mark attendance using roll number and webcam image.
3. POST /add-student - Add a new student using roll number and webcam image.
4. POST /get-attendence - Get attendance data for a specific roll number.
5. GET /mark-absent-all - Mark all other students as absent for the day.

### Login

    URL: /login
    Method: POST
    Description: Logs in the user and returns a JWT token.
    Request:
    Form Data:
        user_id: User ID
        image: User image file
    Response:
        Success: { "status": "Login successful", "isAdmin": boolean, "attendence": [] }
        Error: { "status": "Error message" }

### Mark Attendance

    URL: /mark-attendance
    Method: POST
    Description: Marks the user's attendance.
    Request:
    Form Data:
        user_id: User ID
        image: User image file
    Response:
        Success: { "status": "attendance marked" }
        Error: { "status": "Error message" }

### Add Student

    URL: /add-student
    Method: POST
    Description: Adds a new student to the system (Admin only).
    Request:
    Form Data:
            user_id: User ID
            image: User image file
    Response:
        Success: { "status": "student added" }
        Error: { "status": "Error message" }

### Get Attendance

    URL: /get-attendance
    Method: POST
    Description: Gets the attendance records for the user or another user (Admin only).
    Request:
        Form Data:
        user_id: User ID (of the user whose attendance is requested)
    Response:
        Success: { "status": "Got Attendance", "attendance": [] }
        Error: { "status": "Error message" }

### Mark Absent All

    URL: /mark-absent-all
    Method: GET
    Description: Marks all users as absent who have not marked their attendance for the day (Admin only).
    Response:
        Success: { "status": "All other marked absent, count: n" }
        Error: { "status": "Error message" }

### Error Handling

Custom exceptions are used to handle errors and return appropriate responses:

1. missing_form_data
2. face_not_detected
3. user_not_found
4. something_went_wrong
5. not_admin

### Helper Functions

1. extract_id_and_image: Extracts user ID and image from the request.
2. check_face: Compares two images to check if they have the same face.
3. extrat_face: Extracts the face from an image.
4. mark_present: Marks a user as present.
5. check_and_get_use: Checks if a user exists and returns the user.
6. check_admin: Checks if a user is an admin.
7. mark_absent: Marks all users as absent who have not marked their attendance for the day.

### what i learned for this project

1. got my weekness of react, like cookies and a bit of await, known and will now work on it
2. got to know i can ignore the CORS issue of localhost by using localh.st
3. came to know about Flask and DeepFace technologies
4. helped me to brush me up with a few mongo db resources and python
5. came to know about pip freeze > requirements.txt to list all requirements easily.
6. http://localh.st:5000 for CORS issue solution.

### Area of Improvement in backend

1. to make the code more readable by using file organising for different function
2. JWT implementation intergration with the frontend.
3. front end is very messy with a lot of code repetation, would like to organise the same and learn new concept to use multiple useStae variables across the react app without passing every where,
4. React code can get full of errors in no time, i want to make it organised and compact so that it is esay to use at multiple places, modularity is my focus.

### Scope of improvement in frontend

1. increase the readablity
2. organise the files and fucntions in a better way.
3. understand the concepts of useEffect, hooks, ects in deep, currently i face a bit issue in this topic
4. Reduce copy pasting, increase typing you myself even when i just following the tutorial online, or only online resource.
