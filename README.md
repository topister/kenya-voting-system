# kenya-voting-system

# Kenya Voting System - Complete Setup Guide

## Overview
This is a full-stack secure voting application with voter registration, authentication, voting, and real-time results.

## Architecture
- **Frontend**: React with Tailwind CSS
- **Backend**: Node.js + Express
- **Database**: SQLite
- **Authentication**: JWT (JSON Web Tokens)
- **Security**: Bcrypt password hashing, secure PIN storage

---

## Backend Setup

### 1. Prerequisites
- Node.js (v14 or higher)
- npm or yarn

## Database Schema

The system automatically creates the following tables:

### voters
- Stores voter registration information
- Includes encrypted PIN for authentication
- Tracks verification status

### elections
- Stores election details (title, dates, status)
- Supports multiple simultaneous elections

### candidates
- Links candidates to specific elections and positions
- Stores candidate details (name, party, biography)

### votes
- Records all cast votes
- Prevents duplicate voting per position
- Generates unique vote hashes for audit trails

### audit_log
- Tracks all system actions (registration, login, voting)
- Stores IP addresses and timestamps for security

## Security Features

### 1. Authentication & Authorization
- JWT tokens with 24-hour expiration
- Secure password hashing with bcrypt (10 rounds)
- Token verification middleware on protected routes

### 2. Vote Integrity
- Unique vote hashes prevent tampering
- One vote per position per voter enforcement
- Database constraints prevent duplicate votes

### 3. Audit Trail
- All actions logged with timestamps
- IP address and user agent tracking
- Comprehensive audit log for investigations

### 4. Data Protection
- PINs are never stored in plain text
- SQL injection protection via parameterized queries
- CORS enabled for frontend-backend communication

---

## Testing the Application

### 1. Register a New Voter
1. Click "Register as New Voter"
2. Fill in all required fields
3. Create a PIN (minimum 4 digits)
4. Submit registration
5. Note your voter card number

### 2. Login
1. Use your National ID and PIN
2. Access the voting ballot

### 3. Cast Votes
1. Select candidates for each position
2. Green checkmarks indicate your selections
3. View live results at any time

### 4. View Results
1. Click "View Live Results"
2. See real-time vote counts and percentages
3. Results update immediately as votes are cast

---


