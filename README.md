# Mini Facebook (Django)

This project is a miniature Facebook-like web application built using Django. It allows users to create profiles, post status messages, upload images, manage friendships, and view a custom news feed. The app supports user authentication and was developed incrementally through multiple feature-based assignments.

---

## Overview

The Mini Facebook app enables users to:
- Create and update personal profiles
- Post and edit status updates with image uploads
- Add and view friends
- Get friend suggestions
- See a personalized news feed
- Register, log in, and log out securely

This Django project leverages Django’s class-based views, form handling, and ORM features to provide a full-stack social experience.

---

## Components

### Models (`models.py`)
Defines the core data structures:
- `Profile`: User-linked profile with name, city, email, and image
- `StatusMessage`: Timestamps and messages tied to a profile
- `Image`: File uploads associated with status messages
- `Friend`: Bi-directional friendship relationships between profiles

### Views (`views.py`)
Implements the logic for each page:
- `ShowAllProfilesView`, `ShowProfilePageView`
- Profile creation (`CreateProfileView`) and updates (`UpdateProfileView`)
- Status message creation, update, and deletion
- Friend adding (`CreateFriendView`) and suggestions
- News feed display (`ShowNewsFeedView`)
- Login-required behavior via `LoginRequiredMixin`

### Forms (`forms.py`)
Handles form input for:
- Profile creation and update
- Status message submission
- User registration via `UserCreationForm`

### Templates
Uses class-based view templates for:
- Creating/updating profiles and posts
- Viewing profiles, friend suggestions, and news feed
- Logging in and out

### URLs (`urls.py`)
Maps routes to views:
- Profile and post management
- Friend handling
- Authentication (login/logout)
- News feed and friend suggestions

### Admin (`admin.py`)
Registers models to the Django admin interface:
- `Profile`, `StatusMessage`, `Image`, and `Friend`

### App Configuration (`apps.py`)
Defines the app as `mini_fb`.

---

## Features

- User registration and login with Django's built-in auth system
- Profile and status management
- Media upload (images) and rendering
- Friendship logic with bidirectional tracking
- Friend suggestion algorithm excluding existing connections
- News feed combining user and friend activity
- Custom `get_absolute_url`, `get_friends`, and `get_news_feed` model methods

---

## How to Run

1. Install dependencies:
   ```bash
   pip install -r requirements.txt
   pip install django pillow
2. Apply Migrations
   ```bash
   python manage.py makemigrations
   python manage.py migrate
3. Create a superuser for the admin interface:
   ```bash
   python manage.py createsuperuser
4. Run the server
   ```bash
   python manage.py runserver
   
