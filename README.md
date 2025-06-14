# Spark Tank: Team-Based Business Pitching & Investment Platform

Welcome to **Spark Tank**, a dynamic web platform designed to support a one-of-a-kind business simulation event where teams pitch startup ideas and invest in each other's ventures using virtual currency.

This application powers the core interaction for the Spark Tank event—team registration, idea investment, wallet management, and transaction tracking.

## Event Overview

Spark Tank is an educational and entrepreneurial simulation event. Participating teams are given:

- A fixed virtual wallet (₹2000)
- A unique team identity
- The ability to invest in other teams’ ideas by purchasing shares

At the end of the event, performance is evaluated based on:
- Strategic investments
- Popularity of their idea
- Number and value of shares held

## Features

- Team Registration with pre-defined credentials and unique ObjectIds
- Wallet Management with real-time balance updates
- Shares & Investment System to simulate equity transactions
- Transaction History for full traceability
- Admin Control (future scope: round-wise control and moderation)

## Tech Stack

| Component      | Technology Used        |
|----------------|------------------------|
| Frontend       | React.js               |
| Styling        | CSS                    |
| Backend        | Node.js, Express       |
| Database       | MongoDB with Mongoose  |
| State Storage  | LocalStorage (Frontend), MongoDB (Backend) |
| Dev Tools      | Vite, ESLint, Nodemon  |

## Folder Structure

```
NISB_Spark_Tank/
│
├── client/                      # Frontend React application
│   ├── public/                 # Static files like index.html, favicon etc.
│   └── src/                    # Core React source code
│       ├── assets/             # Images and media used in the frontend
│       ├── components/         # Reusable UI components (Register, Dashboard, etc.)
│       ├── pages/              # Page-level components
│       ├── App.js              # Main App component
│       └── index.js            # Entry point for React
│
├── server/                     # Backend Node.js application
│   ├── models/                 # Mongoose schemas (Team, Transaction etc.)
│   ├── routes/                 # Express routes (e.g., /register, /transactions)
│   ├── controllers/            # Route logic and controller functions
│   ├── middleware/             # Middleware for error handling, validation
│   ├── config/                 # DB connection setup and configuration
│   └── index.js                # Server entry point
│
├── .env                        # Environment variables (not committed)
├── .gitignore                  # Files and folders to be ignored by git
├── package.json                # Project metadata and dependencies
├── README.md                   # Project overview and documentation
└── requirements.txt            # (If using Python utilities - optional)

```

## Installation and Setup

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/spark-tank.git
cd spark-tank
```

### 2. Install Backend Dependencies

```bash
cd server
npm install
```

### 3. Install Frontend Dependencies

```bash
cd ../client
npm install
```

### 4. Set Up MongoDB

Ensure MongoDB is installed and running locally or via Atlas. Update your MongoDB connection string in `server/.env`:

```
MONGO_URI=mongodb://localhost:27017/sparktank
```

### 5. Run the Application

Backend:

```bash
cd server
npm run start
```

Frontend:

```bash
cd client
npm start
```

Visit `http://localhost:5173` to access the application.

## MongoDB Models

### Team

```json
{
  "name": "String",
  "wallet": "Number",
  "availableShares": "Number"
}
```

### Transaction

```json
{
  "purchasingTeamId": "ObjectId",
  "sellingTeamId": "ObjectId",
  "sharesBought": "Number",
  "costPerShare": "Number",
  "totalCost": "Number"
}
```

## Predefined Teams

30 teams are initialized in localStorage with:

- Usernames: team-1 to team-30
- Passwords: password1 to password30
- Corresponding pre-injected MongoDB ObjectIds

## Future Scope

- Add admin panel for round-wise control and manual wallet resets
- Auto leaderboard generation
- Analytics dashboard for judges
- Notification system for investment updates

## Contributing

Pull requests are welcome. For significant changes, please open an issue to discuss your proposed enhancement or bug fix.

## License

This project is for internal event use and educational purposes. Contact  Karthikeya S before using or modifying for other events.

## Contact

For queries or suggestions, reach out to the Spark Tank organizing team.
