### Theory

#### Overview of Broken Authentication
**Broken Authentication** occurs when an application fails to correctly implement authentication or session management. This can allow attackers to bypass login mechanisms, hijack sessions, or gain access to sensitive accounts or functionality (like administrative dashboards).  

Common causes include:  
- Weak or guessable passwords  
- Exposed session IDs  
- Reuse of credentials across multiple accounts  
- Poorly implemented login mechanisms (e.g., no rate limiting)  

##### Key Concepts
1. **Session Management**  
   - Refers to how applications handle user sessions after a successful login.  
   - Proper session management ensures that session IDs are unique, randomly generated, expire after inactivity, and are protected from interception or tampering.  
   - Example of poor session management: using predictable session IDs like `user123` or `session1`.  

2. **Authentication**  
   - The process of verifying a user’s identity.  
   - Methods include passwords, multi-factor authentication (MFA), and biometric verification.  
   - Weak authentication mechanisms make it easier for attackers to impersonate legitimate users.  

3. **Authorization**  
   - Determines what resources a user can access once authenticated.  
   - Broken authorization can allow normal users to perform administrative actions or access confidential data.  


#### Cookie-Based Authentication
Cookies are commonly used to manage user sessions in web applications. When a user logs in:  
1. The server creates a session and generates a unique **session ID**.  
2. The session ID is stored in a **cookie** on the client-side.  
3. Every time the client makes a request, the cookie is sent to the server to validate the session.  

##### Key Points
- **Session Cookie**  
  - Stores the session ID to maintain continuity between requests.  
  - Should be set with secure flags like `HttpOnly` and `Secure` to prevent theft via XSS or network interception.  

- **Base64 Encoding**  
  - Converts binary data (like session tokens) into ASCII strings for safe transmission.  
  - Important: Base64 is *not encryption*—it does not protect sensitive information from attackers. If an attacker captures a Base64-encoded session ID, they can still use it to impersonate the user.  


#### Additional Considerations
- **Session Expiration:** Sessions should automatically expire after a certain period of inactivity.  
- **Logout Mechanism:** Users must be able to log out, which should invalidate the session on the server.  
- **MFA Integration:** Using multi-factor authentication adds an extra layer of security, reducing the impact of credential theft.  
- **Monitoring:** Detect suspicious login attempts, unusual session activity, and repeated failed login attempts.
