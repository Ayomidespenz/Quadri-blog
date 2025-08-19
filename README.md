# Blog Platform - Full Stack Application

A modern blog platform built with Laravel (Backend) and Vue.js (Frontend) featuring user authentication, post management, comments, likes, and a responsive design.

## Features

### Backend (Laravel)
- **User Authentication** with Laravel Sanctum
- **Post Management** (CRUD operations)
- **Comments System**
- **Likes System**
- **User Profiles** with bio and avatar
- **Search and Filtering**
- **Categories Support**
- **File Upload** for images
- **API Documentation**

### Frontend (Vue.js)
- **Responsive Design** with Bootstrap 5
- **User Authentication** (Login/Register/Forgot Password)
- **Blog Posts** with real-time interactions
- **Comments** with real-time updates
- **Likes** with instant feedback
- **User Dashboard** for post management
- **Profile Management**
- **Search and Filtering**

## Prerequisites

- PHP 8.2 or higher
- Composer
- Node.js 16 or higher
- npm or pnpm
- MySQL/PostgreSQL/SQLite

## Installation

### Backend Setup

1. **Navigate to the backend directory:**
   ```bash
   cd blog-backend
   ```

2. **Install PHP dependencies:**
   ```bash
   composer install
   ```

3. **Copy environment file:**
   ```bash
   cp .env.example .env
   ```

4. **Generate application key:**
   ```bash
   php artisan key:generate
   ```

5. **Configure database in `.env`:**
   ```env
   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=blog_platform
   DB_USERNAME=your_username
   DB_PASSWORD=your_password
   ```

6. **Run migrations:**
   ```bash
   php artisan migrate
   ```

7. **Seed the database with sample data:**
   ```bash
   php artisan db:seed
   ```

8. **Create storage link:**
   ```bash
   php artisan storage:link
   ```

9. **Start the development server:**
   ```bash
   php artisan serve
   ```

The backend will be available at `http://localhost:8000`

### Frontend Setup

1. **Navigate to the frontend directory:**
   ```bash
   cd blog-platform
   ```

2. **Install dependencies:**
   ```bash
   npm install
   # or
   pnpm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   # or
   pnpm dev
   ```

The frontend will be available at `http://localhost:5173`

## Default Users

After running the seeder, you can use these default accounts:

### Admin User
- **Email:** admin@example.com
- **Password:** password
- **Role:** Admin

### Regular Users
- **Email:** john@example.com
- **Password:** password
- **Role:** User

- **Email:** sarah@example.com
- **Password:** password
- **Role:** User

- **Email:** michael@example.com
- **Password:** password
- **Role:** User

## API Endpoints

### Authentication
- `POST /api/register` - User registration
- `POST /api/login` - User login
- `POST /api/logout` - User logout (authenticated)
- `POST /api/forgot-password` - Request password reset
- `POST /api/reset-password` - Reset password

### User Profile
- `GET /api/user/profile` - Get user profile (authenticated)
- `PUT /api/user/profile` - Update user profile (authenticated)
- `POST /api/user/avatar` - Update user avatar (authenticated)
- `POST /api/user/password` - Update password (authenticated)

### Posts
- `GET /api/posts` - Get all posts
- `GET /api/posts/{id}` - Get specific post
- `POST /api/posts` - Create new post (authenticated)
- `PUT /api/posts/{id}` - Update post (authenticated)
- `DELETE /api/posts/{id}` - Delete post (authenticated)
- `GET /api/posts/search` - Search posts
- `GET /api/categories` - Get all categories
- `GET /api/user/posts` - Get user's posts (authenticated)
- `GET /api/user/stats` - Get user stats (authenticated)

### Comments
- `GET /api/posts/{post}/comments` - Get post comments
- `POST /api/posts/{post}/comments` - Add comment (authenticated)

### Likes
- `POST /api/posts/{post}/like` - Like a post (authenticated)
- `DELETE /api/posts/{post}/like` - Unlike a post (authenticated)

## Project Structure

```
standard-one/
├── blog-backend/          # Laravel Backend
│   ├── app/
│   │   ├── Http/Controllers/
│   │   └── Models/
│   ├── database/
│   │   ├── migrations/
│   │   └── seeders/
│   ├── routes/
│   └── config/
└── blog-platform/         # Vue.js Frontend
    ├── src/
    │   ├── components/
    │   ├── views/
    │   ├── services/
    │   └── composables/
    ├── public/
    └── package.json
```

## Technologies Used

### Backend
- **Laravel 11** - PHP framework
- **Laravel Sanctum** - API authentication
- **MySQL/PostgreSQL** - Database
- **Eloquent ORM** - Database operations

### Frontend
- **Vue.js 3** - JavaScript framework
- **Vue Router** - Client-side routing
- **Axios** - HTTP client
- **Bootstrap 5** - CSS framework
- **Vite** - Build tool

## Development

### Backend Development
- The API follows RESTful conventions
- All responses are in JSON format
- Authentication is handled via Bearer tokens
- File uploads are stored in the `storage/app/public` directory

### Frontend Development
- Components are organized by feature
- API calls are centralized in the `services/api.js` file
- Authentication state is managed with Vue composables
- Responsive design with Bootstrap 5

## Deployment

### Backend Deployment
1. Set up your production environment
2. Configure your web server (Apache/Nginx)
3. Set up your database
4. Run migrations and seeders
5. Configure environment variables
6. Set up file storage

### Frontend Deployment
1. Build the production version:
   ```bash
   npm run build
   ```
2. Deploy the `dist` folder to your web server
3. Configure your web server to serve the SPA

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
