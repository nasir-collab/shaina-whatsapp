# WhatsApp CRM & Campaign Automation Platform

A full-stack solution for managing WhatsApp Business campaigns using the Meta Cloud API.

## Features
- **Campaign Automation**: Schedule and send template-based messages.
- **Real-time CRM**: Manage customer replies and view delivery status.
- **Meta Integration**: Sync approved templates and connect WABA.
- **Analytics**: Track sent, delivered, and read rates.
- **Queue System**: Robust message delivery using BullMQ and Redis.

## Prerequisites
- Node.js & npm
- PostgreSQL
- Redis
- Meta Business Portfolio with WhatsApp Cloud API access

## Setup

### 1. Database Setup
Create a PostgreSQL database and run the schema:
```bash
psql -U your_user -d your_db -f backend/schema.sql
```

### 2. Backend Configuration
Navigate to `backend/` and install dependencies:
```bash
cd backend
npm install
```
Edit `.env` with your credentials:
- `DATABASE_URL`
- `REDIS_URL`
- `META_VERIFY_TOKEN` (Any string to match what you set in Meta App)
- `JWT_SECRET`

Start the server:
```bash
npm run dev
```

### 3. Frontend Configuration
Navigate to `frontend/` and install dependencies:
```bash
cd frontend
npm install
```
Start the development server:
```bash
npm run dev
```

### 4. Webhook Setup
- Use a tool like `ngrok` to expose your local server: `ngrok http 5000`
- In Meta Developer Portal, set Your Webhook URL: `https://your-ngrok-url.ngrok-free.app/webhook`
- Set the Verify Token to match your `.env`.
- Subscribe to `messages` and `message_deliveries` under WhatsApp Business Account.

## Architecture
- **Backend**: Node.js, Express, BullMQ (Queueing), PostgreSQL.
- **Frontend**: React, Vite, Recharts, Lucide Icons.
- **Styling**: Vanilla CSS (Modern Glassmorphic Design).
