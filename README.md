<div align="center">

### _Bridging the Gap Between Farmers and Buyers_

<br>
<br/>
<br>
<br/>
<br>
<br/>
<br>
<br/>



<br/>

> **AgriContract** is a modern web platform that digitizes and streamlines contract farming — connecting verified farmers and buyers through secure, transparent, and legally-binding digital agreements.

<br/>
</div>

---

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Problem Statement](#-problem-statement)
- [Key Features](#-key-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [API Reference](#-api-reference)
- [Screenshots](#-screenshots)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 🌱 About the Project

AgriContract was built to address a critical gap in India's agricultural ecosystem — the disconnect between farmers and buyers that leads to unstable incomes, lack of transparency, and inefficient trade.

By bringing contract farming onto a digital platform, AgriContract enables:

- **Farmers** to secure guaranteed buyers before even sowing their crops
- **Buyers** to source reliable, quality produce directly from farms
- **Both parties** to transact with full legal transparency and zero ambiguity

This project was developed as part of **Smart India Hackathon 2024 (SIH 2024)** — Problem Statement ID: **1640**, by Team **NERD NINJAS**.

---

## 🚨 Problem Statement

Contract farming in India faces several persistent challenges:

| Problem                         | Impact                                               |
| ------------------------------- | ---------------------------------------------------- |
| 🎲 Uncertain Market Access      | Farmers face unpredictable sales and volatile income |
| 🤝 Lack of Trust & Transparency | Disputes over undocumented verbal agreements         |
| ⏳ Time-Consuming Negotiations  | Inefficient back-and-forth between parties           |
| 📊 Limited Market Intelligence  | Farmers make uninformed decisions without price data |

**AgriContract solves all of these** through a unified digital platform with secure contracting, verified profiles, and real-time market information.

---

## ✨ Key Features

### 👨‍🌾 For Farmers

- 📝 **Digital Contract Creation** — Create and sign legally-binding contracts online
- 📊 **Dashboard** — Centralized view of all active, pending, and completed contracts
- 🧑‍💼 **Profile Management** — Build a credible farming profile for buyers to discover
- 📈 **Market Insights** — Access real-time market data to price produce competitively

### 🏢 For Buyers

- 🔍 **Farmer Discovery** — Browse verified farmer profiles and their produce offerings
- 📋 **Contract Management** — Initiate, negotiate, and manage contracts at scale
- 🛒 **Marketplace** — Explore available agricultural produce listings
- 📬 **Contract Tracking** — Stay updated on contract status with live notifications

### 🔒 Platform-wide

- 🔐 **JWT Authentication** — Secure, role-based access for farmers and buyers
- 📱 **Fully Responsive UI** — Optimized for mobile, tablet, and desktop
- ⚡ **Real-Time Updates** — Instant status changes and notifications
- 🗄️ **MongoDB Backend** — Robust, scalable data management

---

## 🛠 Tech Stack

<div align="center">

| Layer                | Technology                      |
| -------------------- | ------------------------------- |
| **Frontend**         | Next.js 14, React, Tailwind CSS |
| **Backend**          | Node.js, Next.js API Routes     |
| **Database**         | MongoDB, Mongoose               |
| **Authentication**   | Custom JWT implementation       |
| **Deployment**       | Vercel                          |
| **Design**           | Figma                           |
| **Containerization** | Docker                          |

</div>

---

## 📁 Project Structure

```
AgriContract/
├── public/                     # Static assets & images
├── src/
│   ├── app/
│   │   ├── api/                # Backend API routes
│   │   │   ├── buyers/         # Buyer auth & profile APIs
│   │   │   ├── farmers/        # Farmer auth & profile APIs
│   │   │   └── contracts/      # Contract management APIs
│   │   ├── buyers/             # Buyer-facing pages
│   │   │   ├── dashboard/
│   │   │   ├── markets/
│   │   │   ├── myContracts/
│   │   │   └── profile/
│   │   ├── farmers/            # Farmer-facing pages
│   │   │   ├── dashboard/
│   │   │   ├── myContracts/
│   │   │   └── profile/
│   │   ├── contract/[farmerId]/ # Dynamic contract pages
│   │   └── create-contract/    # Contract creation flow
│   ├── components/             # Reusable React components
│   ├── context/                # Global state (Auth, Contracts)
│   ├── models/                 # Mongoose data models
│   │   ├── Farmer.js
│   │   ├── Buyer.js
│   │   └── Contract.js
│   └── utils/                  # Helper utilities (DB, JWT)
├── Dockerfile
├── .env
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites

Make sure you have the following installed:

- [Node.js](https://nodejs.org/) v18+
- [npm](https://npmjs.com/) v9+
- A [MongoDB](https://www.mongodb.com/) instance (local or Atlas)

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/Harithakur77/AgriContract.git
cd AgriContract
```

**2. Install dependencies**

```bash
npm install
```

**3. Configure environment variables**

Create a `.env` file in the root directory:

```env
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
```

> 💡 For MongoDB Atlas, your URI will look like:
> `mongodb+srv://<username>:<password>@cluster.mongodb.net/agricontract`

**4. Run the development server**

```bash
npm run dev
```

**5. Open in browser**

Visit [`http://localhost:3000`](http://localhost:3000) 🎉

### 🐳 Running with Docker

```bash
# Build the image
docker build -t agricontract .

# Run the container
docker run -p 3000:3000 --env-file .env agricontract
```

---

## 📡 API Reference

### Farmer Endpoints

| Method | Endpoint                | Description                |
| ------ | ----------------------- | -------------------------- |
| `POST` | `/api/farmers/register` | Register a new farmer      |
| `POST` | `/api/farmers/signin`   | Farmer login               |
| `GET`  | `/api/farmers/me`       | Get current farmer profile |
| `PUT`  | `/api/farmers/profile`  | Update farmer profile      |
| `GET`  | `/api/farmers/all`      | List all farmers           |

### Buyer Endpoints

| Method | Endpoint               | Description               |
| ------ | ---------------------- | ------------------------- |
| `POST` | `/api/buyers/register` | Register a new buyer      |
| `POST` | `/api/buyers/signin`   | Buyer login               |
| `GET`  | `/api/buyers/me`       | Get current buyer profile |

### Contract Endpoints

| Method | Endpoint                  | Description              |
| ------ | ------------------------- | ------------------------ |
| `POST` | `/api/contracts`          | Create a new contract    |
| `GET`  | `/api/contracts/[userId]` | Get contracts for a user |
| `PUT`  | `/api/contracts/update`   | Update contract status   |

---

---

## 🤝 Contributing

Contributions make the open-source community thrive. Any contributions you make are **greatly appreciated**!

1. **Fork** the repository
2. Create your feature branch: `git checkout -b feature/AmazingFeature`
3. Commit your changes: `git commit -m 'Add some AmazingFeature'`
4. Push to the branch: `git push origin feature/AmazingFeature`
5. Open a **Pull Request**

Please make sure to update tests as appropriate and follow the existing code style.

---

## 📄 License

Distributed under the MIT License. See [`LICENSE`](LICENSE) for more information.

---

## 📬 Contact

**Hari Mohan** — Developer & Project Lead

<div align="left">

**GitHub:** [github.com/Harithakur77](https://github.com/Harithakur77)

</div>

**Project Repository:** [https://github.com/Harithakur77/AgriContract](https://github.com/Harithakur77/AgriContract)

---

<div align="center">

Made with ❤️ for Indian Farmers 🌾

⭐ **Star this repo** if you found it useful — it means a lot!

</div>
