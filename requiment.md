**SRS - Software Requirement Specification**

1. Introduction

   The Blog REST API Application is a collection of public api endpoints that enables users to create, manage, and interact with a single author blog. The backend application provides authentication functionality, allows users to create and view articles, comment on articles and upload cover photos for articles. This document outlines the functional and non-functional requirements for the development of the Blog REST API Application.

2. System Overview

   The Blog REST API Application aims to provide a seamless user experience while ensuing the security and integrity of user data. It allows users to browse articles without authentication, but authentication is required for commenting. Administrators have access to an admin dashboard for managing articles, comments, and cover photos.

3. Functional Requirements

   a. Authentication

   - Users should be able to register for an account by providing their email address and a secure password.
   - Users should be able to log in securely using their email address and password.
   - Administrators should be able to log in securely using their credentials.

   b. User Management

   - Admin can create new users
   - Admin can see a list of users
   - Admin can update or delete users
   - Admin can change password for any user

   c. Article Management

   - Authenticated users should be able to create, edit, and delete their own articles.
   - Articles should contain a title, content, and an optional cover photo.
   - Any users should be able to view a list of all articles and retrieve individual articles.

   d. Commenting

   - Authenticated users should be able to post comments on articles.
   - Comments should include the author's name, email. (optional), and the comment text.
   - Users should be able to view comments associated with an article.
   - Admin can manage comments

   e. Cover Photo Management

   - Authenticated users should be able to upload and update a cover photo for their articles.
   - The system should support various image formats and validate uploaded cover photos.

