# 📸 Social Project - Photo Sharing Web Application

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Django](https://img.shields.io/badge/Django-3.2%2B-092E20.svg)](https://www.djangoproject.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-2.2%2B-38B2AC.svg)](https://tailwindcss.com/)
[![License: ISC](https://img.shields.io/badge/License-ISC-yellow.svg)](https://opensource.org/licenses/ISC)

A full-featured social photo-sharing web application built with **Django** and styled using **Tailwind CSS**. Users can share photos with titles and captions, engage with others by liking and commenting on posts, and manage custom user profiles with avatars.

---

## ✨ Features

### 👤 User Authentication & Profile Management
- **Registration & Authentication**: User sign-up, login, and logout workflows.
- **Profile Customization**: Dedicated profile model linked to each user with profile picture upload.
- **Account Settings**: Update user details (name, email) and profile picture.
- **Password Management**: Complete password change and password reset workflows (console email backend configured for local testing).

### 📷 Post Sharing & Community Feed
- **Create Posts**: Upload images with titles, captions, and automatically generated slugs.
- **Interactive Social Feed**: Browse posts in a card-based layout featuring author avatars, timestamps, titles, and captions.
- **User Feed ("My Posts")**: Filtered view showing only posts created by the authenticated user.

### ❤️ Engagement & Social Interactions
- **AJAX Post Likes**: Like and unlike posts asynchronously without full-page reloads.
- **Smart Like Counters**: Intuitive like summaries (e.g., *"john & 2 others like this"*).
- **Post Comments**: Leave comments on posts with author tracking and chronological comment display.

---

## 🛠️ Tech Stack

- **Backend**: Python, Django
- **Frontend**: Django Templates, Tailwind CSS, JavaScript / jQuery (AJAX interactions)
- **Database**: SQLite (default for development; easily swappable with PostgreSQL or MySQL)
- **Image Processing**: Pillow (Python Imaging Library)
- **Package Managers**: `pip` (Python) & `npm` (Frontend asset build)

---

## 📁 Project Structure

```text
socialproject/
├── manage.py                   # Django CLI management script
├── db.sqlite3                  # SQLite development database
├── package.json                # Node.js dependencies & Tailwind build script
├── socialproject/              # Project configuration directory
│   ├── settings.py             # Django settings & configurations
│   ├── urls.py                 # Root URL configuration
│   ├── wsgi.py                 # WSGI application entrypoint
│   └── asgi.py                 # ASGI configuration
├── posts/                      # Posts & interactions application
│   ├── models.py               # Post and Comment models
│   ├── views.py                # Post creation, feed display, AJAX like logic
│   ├── forms.py                # PostCreateForm and CommentForm
│   ├── urls.py                 # Routing for /posts/...
│   └── templates/posts/        # Post templates (feed.html, create.html)
├── users/                      # Authentication & user profile application
│   ├── models.py               # Profile model with avatar uploads
│   ├── views.py                # Auth, registration, profile editing, personal feed
│   ├── forms.py                # Login, registration, and profile edit forms
│   ├── urls.py                 # Routing for /users/...
│   ├── static/users/           # Tailwind CSS styles and UI icons
│   └── templates/users/        # Auth and profile templates
└── media/                      # Uploaded user avatars and post photos
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed on your machine:
- **Python 3.8+**
- **Node.js & npm** (required to build Tailwind CSS)
- **Git**

---

### Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/husankhon/social_project.git
   cd social_project
   ```

2. **Create and activate a virtual environment**
   - **macOS / Linux**:
     ```bash
     python3 -m venv venv
     source venv/bin/activate
     ```
   - **Windows**:
     ```bash
     python -m venv venv
     venv\Scripts\activate
     ```

3. **Install Python dependencies**
   ```bash
   pip install -r requirements.txt
   ```
   *(Or manually: `pip install django pillow django-mathfilters`)*

4. **Install Node dependencies and compile Tailwind CSS**
   ```bash
   npm install
   npm run build
   ```

5. **Apply database migrations**
   ```bash
   python manage.py migrate
   ```

6. **Create an administrative superuser** *(optional, for admin access)*
   ```bash
   python manage.py createsuperuser
   ```

7. **Run the development server**
   ```bash
   python manage.py runserver
   ```

8. **Open in browser**
   - Application Feed: [http://127.0.0.1:8000/posts/feed](http://127.0.0.1:8000/posts/feed)
   - User Profile / My Posts: [http://127.0.0.1:8000/users/](http://127.0.0.1:8000/users/)
   - Admin Panel: [http://127.0.0.1:8000/admin/](http://127.0.0.1:8000/admin/)

---

## 🧭 URL Routing Overview

| Route | Description |
|---|---|
| `/posts/feed` | Community feed showing all posts, likes, and comments |
| `/posts/create` | Form to upload an image and create a post (login required) |
| `/posts/like` | AJAX endpoint to toggle likes on a post |
| `/users/` | Personal dashboard displaying user profile & personal posts |
| `/users/register/` | Account registration |
| `/users/login/` | User login |
| `/users/logout/` | User logout |
| `/users/edit/` | Edit user profile details and avatar photo |
| `/users/password_change/` | Change password (authenticated users) |
| `/users/password_reset/` | Password reset request via email token |
| `/admin/` | Django administrative interface |

---

## 🎨 Styling with Tailwind CSS

Tailwind CSS styles are configured via `package.json`. If you make changes to classes in your templates:

- To recompile CSS:
  ```bash
  npm run build
  ```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!
1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

---

## 📄 License

Distributed under the **ISC License**. See `package.json` for details.
