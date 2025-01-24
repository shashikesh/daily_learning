# Common HTTP Status Codes

---

### **1xx: Informational**
- **100 Continue**: The server has received the request headers and the client can proceed to send the request body.
- **101 Switching Protocols**: The server switches to a different protocol as requested by the client.

---

### **2xx: Success**
- **200 OK**: The request was successful, and the server returned the requested data.
- **201 Created**: The request was successful, and a new resource was created.
- **204 No Content**: The server successfully processed the request but returned no content.

---

### **3xx: Redirection**
- **301 Moved Permanently**: The requested resource has been moved to a new URL permanently.
- **302 Found**: The resource is temporarily located at a different URL.
- **304 Not Modified**: The requested resource has not been modified since the last access.

---

### **4xx: Client Errors**
- **400 Bad Request**: The server cannot process the request due to client-side errors.
- **401 Unauthorized**: Authentication is required but missing or invalid.
- **403 Forbidden**: The server refuses to fulfill the request, even with authentication.
- **404 Not Found**: The requested resource could not be found on the server.
- **405 Method Not Allowed**: The HTTP method is not allowed for the resource.

---

### **5xx: Server Errors**
- **500 Internal Server Error**: The server encountered an unexpected condition.
- **501 Not Implemented**: The server does not support the requested functionality.
- **502 Bad Gateway**: The server received an invalid response from an upstream server.
- **503 Service Unavailable**: The server is temporarily unable to handle the request.
- **504 Gateway Timeout**: The server did not receive a timely response from an upstream server.

---
