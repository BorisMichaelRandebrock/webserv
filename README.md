# 42Webserv - HTTP Server in C++98

## Overview  
This project involves implementing a custom HTTP server in C++98, adhering to the HTTP/1.1 protocol specifications. The server handles client requests, serves static files, manages dynamic content via CGI, and supports HTTP methods (GET, POST, DELETE).  

---

## Features  

✅ **Non-blocking I/O**: Uses `poll()` for efficient multi-client handling.  
✅ **Configuration File**: Customized:  
   - Ports/hosts, server names, error pages  
   - Client body size limits  
   - Route rules (HTTP methods, file uploads, directory listings)   

✅ **HTTP Methods**: GET, POST, DELETE  
✅ **Static Files**: Serve HTML/images/scripts from specified directories.  
✅ **File Uploads**: Accept client uploads to configured routes.  
✅ **CGI Support**: Execute scripts via `execve`.  
✅ **Error Handling**: Default error pages + accurate HTTP status codes.  
✅ **Directory Listings (Autoindex)**:  
   - Generates HTML directory listings when no index file exists  
   - Configurable per-route (on/off)  
   - Shows clickable files/subdirectories with metadata 

---

## Requirements  
- **Compiler**: `c++` with `-Wall -Wextra -Werror -std=c++98`.  
- **OS**: Unix.  

---

## Quick Start  

### 1. Build  
```bash
make
```


### 2. Run 
```bash
make run
```

### 3. Test
- **Browser**: navigate to ` Navigate to http://localhost:8042` .  
- **Curl**: 

```bash
curl -v -F "archivo=@test.txt" http://localhost:8042/cgi-bin/cgi_test.cgi
```

### 4. Stress-test
- **Siege**:  
```
siege -b http://localhost:8042  
```