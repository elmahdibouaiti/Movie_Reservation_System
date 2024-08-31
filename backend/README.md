
# Movie Reservation Service

This project is a Laravel-based backend system for a movie reservation service. It allows users to sign up, log in, browse movies, reserve seats for specific showtimes, and manage their reservations.

## Project Structure

The repository is organized into three main folders:

- `backend`: Contains the Laravel backend code.
- `frontend`: Will contain the frontend code (not yet implemented).
- `doc`: Contains documentation, including UML diagrams.

## Backend Setup and Usage

### Prerequisites

- PHP 8.0 or higher
- Composer
- MySQL or any other supported database
- Node.js and npm (for running Vite or other assets)

### Installation

1. **Clone the Repository:**

   ```bash
   git clone https://github.com/elmahdibouaiti/Movie_Reservation_System
   cd movie-reservation-service/backend
   ```

2. **Install Dependencies:**

   ```bash
   composer install
   ```

3. **Environment Setup:**

   Copy the `.env.example` file to `.env` and update the environment variables as needed:

   ```bash
   cp .env.example .env
   ```

   Update the following settings in the `.env` file:

   ```env
   APP_NAME=MovieReservationService
   APP_ENV=local
   APP_KEY=base64:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
   APP_DEBUG=true
   APP_URL=http://localhost

   DB_CONNECTION=mysql
   DB_HOST=127.0.0.1
   DB_PORT=3306
   DB_DATABASE=movie_reservation_db
   DB_USERNAME=root
   DB_PASSWORD=yourpassword
   ```

4. **Generate Application Key:**

   ```bash
   php artisan key:generate
   ```
5. **Database Schema:**

The following UML diagram illustrates the database schema:

![Database Schema](Docs/db_schema.png)

## User Authentication Flow

The sequence diagram below illustrates the user authentication process:

![User Authentication Sequence](Docs/user_schema.png)
6. **Run Migrations:**

   Run the following command to create the database schema:

   ```bash
   php artisan migrate
   ```

7. **Serve the Application:**

   Start the Laravel development server:

   ```bash
   php artisan serve
   ```

   The backend should now be running at `http://localhost:8000`.

## Manually Assigning Admin Role

In a seeder or by using a command, you can create an admin user like this:

   ```bash
   php artisan tinker
   ```
Then, in the Tinker environment:
   ```bash
   $user = App\Models\User::create([
      'name' => 'Admin Name',
      'email' => 'admin@example.com',
      'password' => Hash::make('password'),
      'role' => 'admin', // Assign admin role
   ]);
   ```
### API Usage

Once the backend is up and running, you can interact with the API using tools like Postman or cURL. Here are some example requests:

- **Register a User:**

  ```bash
  POST http://localhost:8000/api/register
  {
      "name": "John Doe",
      "email": "john@example.com",
      "password": "secret123"
  }
  ```

- **Login:**

  ```bash
  POST http://localhost:8000/api/login
  {
      "email": "john@example.com",
      "password": "secret123"
  }
  ```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License. Created by [El Mahdi Bouaiti](https://github.com/elmahdibouaiti)
