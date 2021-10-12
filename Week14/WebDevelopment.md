## Week 14 Homework: Web Development

### Overview

In this homework, we will review the many of the concepts and tools covered in the Web Development unit. If needed, refer to the  reference sheets provided to you.

* [HTTP Reference Sheet](./HTTP_Reference.md)
* [curl Reference Sheet](./cURL_Reference.md)

---

### Questions 

Before you work through the questions below, please create a new file and record your answers there. This will be your homework deliverable.

#### HTTP Requests and Responses

Answer the following questions about the HTTP request and response process.

1. What type of architecture does the HTTP request and response process occur in?

    `Client-server architecture.`

2. What are the different parts of an HTTP request? 

    `There are 3 parts to a HTTP request:
     - Request line
     - Header 
     - Body.` 

<br>

3. Which part of an HTTP request is optional?

    `The request body is otional.` 

4. What are the three parts of an HTTP response?

    `The 3 parts to a HTTP response are:
     - Status line
     - Headers 
     - Response Body.`

5. Which number class of status codes represents errors?

    `400.`

6. What are the two most common request methods that a security professional will encounter?

    `The two most common request methods are the GET and POST requests.` 

7. Which type of HTTP request method is used for sending data?

    `The POST method is used to send data.`

8. Which part of an HTTP request contains the data being sent to the server?

    `The body of the HTTP request contains the data being sent to the server.`

9. In which part of an HTTP response does the browser receive the web code to generate and style a web page?

    `The browser receives the web code to generate and style a web page from the body of the HTTP response.`

#### Using curl

Answer the following questions about `curl`:

10. What are the advantages of using `curl` over the browser?

    `The curl command allows us to quickly test HTTP requests through automation.` 

11. Which `curl` option is used to change the request method?

    `Using curl from the command line has the ability to change the request method.`

12. Which `curl` option is used to set request headers?

    `-H is the option that is used to set request headers.` 

13. Which `curl` option is used to view the response header?
    `curl -i is used to view the response heaader.` 

14. Which request method might an attacker use to figure out which HTTP requests an HTTP server will accept?

    `An attacker can use cookies to to figure out which HTTP requests and HTTP server will accept.` 

#### Sessions and Cookies

Recall that HTTP servers need to be able to recognize clients from one another. They do this through sessions and cookies. 

Answer the following questions about sessions and cookies:

15. Which response header sends a cookie to the client?

    ```HTTP
    HTTP/1.1 200 OK
    Content-type: text/html
    Set-Cookie: cart=Bob
    ```

    `A Set-Cookie: cart=Bob header sends a cookie to the client.`

16. Which request header will continue the client's session?

    ```HTTP
    GET /cart HTTP/1.1
    Host: www.example.org
    Cookie: cart=Bob
    ```

    `The Cookie: cart=Bob header will continue the client's session on a un a new personalizes webpage.`

#### Example HTTP Requests and Responses

Look through the following example HTTP request and response and answer the following questions:

**HTTP Request**

```HTTP
POST /login.php HTTP/1.1
Host: example.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 34
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.132 Mobile Safari/537.36

username=Barbara&password=password
```

17. What is the request method?

    `POST is the request method.`

18. Which header expresses the client's preference for an encrypted response?

    `The Upgrade-Insecure-Request expresses the client's preference for an encrypted response.` 

19. Does the request have a user session associated with it?

    `Yes, the connection: keep alive indcates there is an active session.`

20. What kind of data is being sent from this request body? 

    `Login data is being sent from this request.`

**HTTP Response**

```HTTP
HTTP/1.1 200 OK
Date: Mon, 16 Mar 2020 17:05:43 GMT
Last-Modified: Sat, 01 Feb 2020 00:00:00 GMT
Content-Encoding: gzip
Expires: Fri, 01 May 2020 00:00:00 GMT
Server: Apache
Set-Cookie: SessionID=5
Content-Type: text/html; charset=UTF-8
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type: NoSniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block

[page content]
```

21. What is the response status code?

    `The response code is 200=success.`

22. What web server is handling this HTTP response?

    `Apache.`

23. Does this response have a user session associated to it?

    `Yes, there is a user session associated. This is indicated by the Set-Cookie: SessionID=5.` 

24. What kind of content is likely to be in the [page content] response body?

    `The response body is likely to contain the GET request.`

25. If your class covered security headers, what security request headers have been included?

    `The Strict-Transport-Security: max-age=31536000  header has been included, indicating to the client to use HTTPS over HTTP. In addition, X-XSS-Protection: 1; mode=block was also included, indicating cross-site scripting protection.`


#### Monoliths and Microservices

Answer the following questions about monoliths and microservices:

26. What are the individual components of microservices called?
    ```
    - Front end 
    - Back End 
    - Database 
    ```

27. What is a service that writes to a database and communicates to other services?

    `The API (Aplication Programming Interface) writes to a database and communicates to other services. An example of this is pushing a file to Github using the command line instead of a file upload button on the Github website interface.`

28. What type of underlying technology allows for microservices to become scalable and have redundancy?

`Docker containers allow for microservices to become scalable and redundant.`


#### Deploying and Testing a Container Set

Answer the following questions about multi-container deployment:

29. What tool can be used to deploy multiple containers at once?

    `Docker has ability to deply multiple containers simultaneously.`

30. What kind of file format is required for us to deploy a container set?

    `A YAML file format is required for deployment of a container set.`
    <br>

#### Databases

31. Which type of SQL query would we use to see all of the information within a table called `customers`?

`SELECT * FROM CUSTOMERS will display all information in the customers table.`

32. Which type of SQL query would we use to enter new data into a table? (You don't need a full query, just the first part of the statement.)

    `INSERT INTO will allow us to enter new data into a table.`

33. Why would we never run `DELETE FROM <table-name>;` by itself?

    `Running this query without a WHERE clause can result in deleting an entire table and all it's contents forever.` 
---

