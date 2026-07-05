# FAIR FLY API

Welcome to the official repository for the **FAIR FLY API**. This REST API allows clients to determine which sites from the DHV database have been linked to FAIR FLY by site operators and what their status is in FAIR FLY.


## URL
https://api.fair-fly.com


## Endpoints Summary

- **GET** `/user` - Retrieve the current authenticated user's profile.
- **GET** `/flyingsite/{id}` - Use the flying site's ID to check whether it is an active FAIR FLY site.
- **GET** `/flyingsite/status/{id}` - Retrieve the current FAIR FLY status of the flying site using its ID.


## Interactive Documentation

The full API specification and interactive test console are hosted via GitHub Pages. You can test endpoints, view required parameters, and check response formats directly in your browser:

**[View Interactive API Documentation](https://ustra-de.github.io/fair-fly)**


## 🔑 Authentication

All requests to the API endpoints require authentication via an API Key. 
Please include your key in the HTTP header of your requests.

API Key can be requested by email to info@fair-fly.com.

Please provide the following information:
1. First name
2. Last name
3. Email address
4. Purpose of use

Email requests with incomplete information will be automatically ignored.


## Autor

ustra – [@ustra-de](https://github.com/ustra-de)
