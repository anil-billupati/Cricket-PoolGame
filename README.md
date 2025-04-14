# 🏏 Cricket Betting Platform API

A Spring Boot REST API for a money pool-style cricket betting platform, where players can place bets on upcoming matches and winners split the pool of losing bets. Built with robust role-based access, JWT authentication, transactional wallet handling, and detailed match and payout logic.

---

## 🚀 Features

### 🔐 Authentication & Authorization
- JWT-based login (email & password)
- Role-based access control (PLAYER, ADMIN)

### 👥 User Management
- Manual user creation (no signup endpoint)
- Roles: PLAYER or ADMIN
- Wallet balance tracking

### 💼 Wallet Management
- Admin can credit user wallets
- Automatic balance updates on bet placement or payouts
- Full transaction logging

### 🏏 Match Management
- Admin creates matches with teams and bet amount
- Enforces time-based betting closure
- Only one result can be declared

### 🎯 Betting System
- Players place a single bet per match before it starts
- Bets are recorded with amount and chosen team
- Wallet balance is deducted immediately

### 💸 Payout Processing
- When match ends, winnings are distributed among correct bets
- Losers' bet amounts form the winning pool
- Admin can trigger payout with safety checks

---

## 🧰 Tech Stack

- **Java 20**
- **Spring Boot 2.7.7**
- **Spring Security**
- **JWT (JSON Web Tokens)**
- **JPA / Hibernate**
- **PostgreSQL**
- **Lombok**
- **MapStruct**
- **Maven**

---

## 📂 Project Structure

```bash
src/main/java/com/CricketBetting/Cricket/
├── controller         # REST API controllers
├── domain
│   ├── entity         # JPA entities (User, Match, Bet, WalletTransaction, etc.)
│   ├── request        # DTOs for API requests
│   ├── response       # DTOs for API responses
│   ├── enums          # Enum definitions (Team, Role, TransactionType, etc.)
├── mapper             # MapStruct mappers
├── repository         # Spring Data JPA repositories
├── security           # JWT and authentication configs
├── service            # Service interfaces
├── service/impl       # Service implementations


🛠️ Getting Started
✅ Prerequisites
Java 20+
Maven
MySQL

📦 Setup
Clone the repo
git clone https://github.com/your-username/cricket-betting-api.git
cd cricket-betting-api
Configure the database Update application.properties or application.yml with your PostgreSQL credentials.

Run the app
Command  : ./mvnw spring-boot:run
