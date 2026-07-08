# Knobull Platform

A student-focused news and discussion platform built for the Knobull startup. Features a message board, curated student news, and JWT-authenticated user accounts.

## Features

- **Message board** — posts with upvotes/downvotes and threaded comments
- **User auth** — registration, login, JWT sessions (60-day expiry)
- **Student news feed** — aggregated resources and news for students
- **Sections** — Home, Message Board, About, Contact, Resources

## Stack

Node.js · Express · MongoDB (Mongoose) · Passport.js · JWT · EJS templates

## Data models

**Post** — title, text, upvotes, downvotes, views, author, comments[]
**Comment** — linked to Post via ObjectId ref
**User** — username, bcrypt hash + salt, JWT generation

## Running

```bash
npm install
# Set MONGODB_URI environment variable
node app.js
```

## Auth flow

Passwords are stored as PBKDF2 hashes with random salts. Login returns a JWT valid for 60 days.
