Authentication Strategy
- **Flow:** JWT based (Access Token + Refresh Token).
- **Online:** Initial login and token refresh require internet.
- **Offline:** Access is granted if a valid (non-expired) Refresh Token exists in DataStore.
- **Mechanism:** - `AuthInterceptor`: Adds "Bearer <token>" to every request.
    - `TokenAuthenticator`: Intercepts 401 errors to call `/auth/refresh` and retry the original request.
- **Security:** If refresh fails or token is expired, clear all local session data and force redirect to Login Screen.