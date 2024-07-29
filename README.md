
# Exchange Platform

Welcome to the Exchange Platform! This project is a comprehensive application for simulating asset exchanges, featuring a `sol_usdc` market. It includes a backend API, an in-memory engine for trade and order book management, and a frontend with real-time updates using WebSockets and lightweight charts.

![photo1](photo1.png)

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Folder Structure](#folder-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Features

- **Real-Time Communication:** WebSocket integration for live updates and notifications.
- **Real-Time Data Updates:** Redis pub/sub for efficient data broadcasting.
- **In-Memory Engine:** Manages trades and order book with in-memory variables.
- **Modern Frontend:** Responsive and dynamic UI with Next.js and lightweight charts.
- **Scalable Backend:** Express.js for handling server-side logic and WebSocket connections.
- **Persistent Storage:** PostgreSQL for storing asset and transaction data.

## Tech Stack

- **Frontend:** Next.js, React, Lightweight Charts
- **Backend API:** Express.js
- **Database:** PostgreSQL
- **ORM:** Prisma
- **Caching and Pub/Sub:** Redis
- **Real-Time Communication:** WebSockets
- **In-Memory Management:** Engine server for trades and order book

## Folder Structure

```
/exchange-platform
│
├── /api                   # Express server for API requests and redis management 
│
├── /db                    # Database client and setup
│
├── /engine                # Express server for in-memory trade and order book management
│
├── /frontend              # Next.js frontend application
│   ├── /components        # React components
│   └── /app            # Next.js pages
│
├── /ws                    # WebSocket server
```

## Installation

1. **Clone the repository:**

    ```bash
    git clone https://github.com/yourusername/asset-exchange-platform.git
    cd asset-exchange-platform
    ```

2. **Install dependencies for each component:**

    ```bash
    # Install dependencies for API server
    cd api
    npm install

    # Install dependencies for database client
    cd ../db
    npm install

    # Install dependencies for engine server
    cd ../engine
    npm install

    # Install dependencies for frontend
    cd ../frontend
    npm install

    # Install dependencies for WebSocket server
    cd ../ws
    npm install
    ```

3. **Set up environment variables:**

    Create a `.env` file in the root directory and each component directory with the following contents:

    ```env
    # .env (root)
    NEXT_PUBLIC_API_URL=http://localhost:5000
    ```

    ```env
    # api/.env
    DATABASE_URL=postgresql://user:password@localhost:5432/asset_exchange
    REDIS_URL=redis://localhost:6379
    ```

    ```env
    # engine/.env
    DATABASE_URL=postgresql://user:password@localhost:5432/asset_exchange
    ```

    ```env
    # ws/.env
    REDIS_URL=redis://localhost:6379
    WEBSOCKET_PORT=5001
    ```

4. **Run database migrations:**

    ```bash
    cd db
    npx prisma migrate deploy
    ```

## Usage

1. **Start Redis server:**

    ```bash
    redis-server
    ```

2. **Start the API server:**

    ```bash
    cd api
    npm start
    ```

3. **Start the in-memory engine server:**

    ```bash
    cd ../engine
    npm start
    ```

4. **Start the WebSocket server:**

    ```bash
    cd ../ws
    npm start
    ```

5. **Start the frontend server:**

    ```bash
    cd ../frontend
    npm run dev
    ```

6. **Access the application:**

    Open `http://localhost:3000` in your web browser to use the platform.

## WebSocket Integration

The backend server supports WebSocket connections for real-time updates. Ensure the WebSocket server is running on the specified port (default: 5001).

## Contributing

Feel free to submit issues, fork the repository, and contribute to the project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

Feel free to adjust this template based on your specific project setup and requirements.