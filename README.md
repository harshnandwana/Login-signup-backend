# FastAPI User Authentication and Password Reset

``` nohup uvicorn sign:app --port=8090 --host=0.0.0.0 --reload > uvicorn.log 2>&1 &```

## Overview

This FastAPI application provides user authentication and password reset features for a web application. It is designed to be a secure and efficient solution for user management.

## Table of Contents

- [Signup](#signup)
- [Login](#login)
- [Reset Password](#reset-password)
- [Features](#features)
- [Considerations](#considerations)
- [Dependencies](#dependencies)

## Signup

### Features of the Signup Form

- User registration with email, password, full name, company name, and phone number.
- Email format validation to ensure correct email addresses.
- Checking if the email is already registered to prevent duplication.
- Domain restriction for email addresses to allow only business emails.
- Passwords are securely hashed using the bcrypt algorithm.
- Custom password strength checks can be easily configured.
- Secure storage of user data in a MongoDB database.

## Login

### Features of the Login

- User login with email and password.
- Rate limiting for login attempts (5 attempts per minute).
- Account lockout mechanism after a certain number of failed login attempts (default: 3).
- Passwords are securely hashed and verified using bcrypt.
- Generation of JWT (JSON Web Token) access tokens upon successful login.

## Reset Password

### Features of the Password Reset

- Password reset functionality to help users regain access to their accounts.
- Generates a unique reset token for user verification.
- Generates a new, random, and secure password for the user.
- Background task for asynchronous sending of password reset emails.
- Email notifications include the new password and a reset link.

## Features

- Efficient and secure user registration and login.
- Protection against brute-force attacks with rate limiting and account lockout.
- Asynchronous handling of email notifications for password resets.
- Customizable password strength checks.
- Use of JWT tokens for secure authentication.
- Passwords are securely hashed for database storage.
- User-friendly signup, login, and password reset functionalities.
- Code is well-documented and easy to understand and modify.

## Considerations

- User data is stored in a MongoDB database, making it easily scalable and accessible.
- Passwords are securely hashed to protect user information.
- Access tokens have expiration times for enhanced security.
- Password reset functionality is implemented with strong random password generation.
- Rate limiting and account lockout mechanisms protect against unauthorized access.

## Dependencies

- FastAPI for building the web application.
- MongoDB for storing user data.
- `pydantic` for data validation.
- `passlib` for password hashing.
- `jwt` for JSON Web Token generation.
- `smtplib` for sending email notifications.
- `slowapi` for rate limiting and error handling.
