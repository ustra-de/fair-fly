# FAIR FLY API

Welcome to the official repository for the **FAIR FLY API**. This REST API allows clients to determine which sites from the DHV database have been linked to FAIR FLY by site operators and what their status is in FAIR FLY.


## URL
https://api.fair-fly.com


## Endpoints Summary

**Data endpoints** - called with the version prefix `/v1`, API key required:

- **GET** `/v1/user` - Retrieve the current authenticated user's profile.
- **GET** `/v1/flyingsite/{id}` - Use the flying site's ID to check whether it is an active FAIR FLY site.
- **GET** `/v1/flyingsite/status/{id}` - Retrieve the current FAIR FLY status of the flying site using its ID.

**Service endpoints** - called without version prefix, no API key required:

- **GET** `/version` - Retrieve the version and build number of the API.
- **GET** `/health` - Check whether the API and its database are operational.


## Version and Health

Both service endpoints are public: they need neither the `/v1` prefix nor an API key. Only `GET` is supported, any other method is answered with `405 Method Not Allowed`.

### `GET /version`

Returns the version and build number of the API, for example:

```json
{"version": "v1.0 build 26.1009"}
```

### `GET /health`

Reports whether the API and its database are operational. It is meant for uptime monitoring: the answer is always determined at the moment of the request and must not be cached (`Cache-Control: no-store`). The response format follows the IETF draft *Health Check Response Format for HTTP APIs* (`application/health+json`).

| HTTP status | Response body | Meaning |
|---|---|---|
| `200` | `{"status": "pass"}` | API and database are operational |
| `503` | `{"status": "fail"}` | API is not healthy, e.g. the database cannot be reached |


## Interactive Documentation

The full API specification and interactive test console are hosted via GitHub Pages. You can test endpoints, view required parameters, and check response formats directly in your browser:

**[View Interactive API Documentation](https://ustra-de.github.io/fair-fly)**


## 🔑 Authentication

All requests to the data endpoints (`/v1/...`) require authentication via an API Key.
Please include your key in the HTTP header of your requests.

API Key can be requested by email to info@fair-fly.com.

Please provide the following information:
1. First name
2. Last name
3. Email address
4. Purpose of use

Email requests with incomplete information will be automatically ignored.


## Author

ustra – [@ustra-de](https://github.com/ustra-de)
