# Price Alert Application Documentation

## Introduction

This document provides an overview and documentation for the Price Alert Application. The application is designed to allow users to create price alerts for cryptocurrencies and receive email notifications when the target price is achieved.

## Features

- **Create Price Alerts:** Users can create price alerts for specific cryptocurrencies.
- **Delete Price Alerts:** Users can delete existing price alerts.
- **Fetch Alerts:** Users can fetch all alerts they have created, with filtering and pagination options.
- **Status Tracking:** Alerts have statuses (e.g., created, deleted, triggered) to track their state.
- **Pagination:** The response for fetching alerts includes pagination information.
- **Filtering:** Users can filter alerts based on their status.
- **User Authentication:** Endpoints are secured with JWT token-based authentication.
- **Real-time Price Updates:** Binance's WebSocket connection is used to get real-time price updates.
- **Alternative Price Endpoint:** An alternative endpoint is provided to fetch the latest cryptocurrency prices.

## Endpoints

### Create Alert

- **URL:** `/alerts/create/`
- **Method:** `POST`
- **Request Body:**
  - `user_id`: Integer (User ID of the requester)
  - `symbol`: String (Symbol of the cryptocurrency)
- **Response:** JSON Object representing the created alert.

### Delete Alert

- **URL:** `/alerts/delete/<int:alert_id>`
- **Method:** `DELETE`
- **Response:** JSON Object with a message indicating success or failure.

### Fetch Alerts

- **URL:** `/alerts/`
- **Method:** `GET`
- **Query Parameters:**
  - `page`: Integer (Optional, default is 1)
  - `status`: String (Optional, filter by alert status)
- **Response:** JSON Object containing alerts, total pages, and current page.

## Authentication

JWT token-based authentication is used to secure the endpoints.

## WebSocket Connection

Binance's WebSocket connection is utilized to get real-time price updates.

## Alternative Price Endpoint

An alternative endpoint provided by CoinGecko is available to fetch the latest cryptocurrency prices.

## Setup

1. Clone the repository.
2. Install dependencies (`pip install -r requirements.txt`).
3. Set up environment variables:
   - `SENDGRID_API_KEY`: API key for SendGrid email service.
   - `SECRET_KEY`: Secret key for JWT token.
4. Run the application (`python app.py`).

## Usage

Use the provided REST API endpoints to create, delete, and fetch alerts. Authenticate using JWT token to access the endpoints. Receive email notifications when price alerts are triggered.
