### Theory 
<h4>Overview of Broken Authentication</h4>
Broken Authentication occurs when an application does not properly manage session or authentication credentials. This can allow an attacker to exploit vulnerabilities in session handling to gain unauthorized access to accounts or functionality, such as an administrative dashboard.


<li><b>Session Management:</b> Proper handling of session identifiers to ensure they cannot be easily guessed or manipulated.</li>
<li><b>Authentication:</b> Verifying the identity of a user or system to ensure they have access to certain resources or data.</li>
<li><b>Authorization:</b> Determining whether a user has the right to access a particular resource or perform an action.</li>

<h4>Cookie-Based Authentication</h4>
Cookies are often used to store session information on the client-side. When a user logs into a web application, the server typically creates a session and stores the session ID in a cookie. This cookie is then sent with each request to authenticate and maintain the session.

<li><b>Session Cookie:</b> A cookie that stores the session identifier which is used to maintain user state and session between requests.</li>
<li><b>Base64 Encoding:</b> A method to encode binary data into an ASCII string format using a set of 64 printable characters. This is often used for transmitting data in a readable format but does not inherently secure the data.</li>