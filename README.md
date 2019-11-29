# ApacheServer-weblog-Analytics
ApacheServer weblog Analytics done using databricks community edition

This project will demonstrate to perform web server log analysis with Apache Spark.

What are Weblogs? Weblogs are where web server (like apache) records events like visitors to your site and problems it's encountered. Your web server records all the visitors to your site. There you can see what files users are accessing, how the web server responded to requests, and other information like what kind of web browsers visitors are using, etc.


Log data comes from many sources, such as web, file, and compute servers, application logs, user-generated content,  and can be used for monitoring servers, improving business and customer intelligence, building recommendation systems, fraud detection, and much more.

Sample Weblog Data:
in24.inetnebr.com - - [01/Aug/1995:00:00:01 -0400] "GET /shuttle/missions/sts-68/news/sts-68-mcc-05.txt HTTP/1.0" 200 1839

Format of weblogs

| field         | meaning                                                                                                      |
| ------------- | -------------------------------------------------------------------------------------------------------------|
| _remotehost_  | Remote hostname (or IP number if DNS hostname is not available).                                             |
| _rfc931_      | The remote logname of the user. We don't really care about this field.                                       |
| _authuser_    | The username of the remote user, as authenticated by the HTTP server.We don't really care about this field.  |
| _[date]_      | The date and time of the request.                                                                            |
| _"request"_   | The request, exactly as it came from the browser or client.                                                  |
| _status_      | The HTTP status code the server sent back to the client.                                                     |
| _bytes_       | The number of bytes (`Content-Length`) transferred to the client.                                            |


KPI : Parse weblogs into structured format ('host', 'dateTime', 'request_string', 'status', 'content_size')

Then do following analysis:

1. we will find what are the average, minimum, and maximum content sizes of web logs.

2. To find which HTTP status values appear in the data and how many times.

3. Find the hosts that have accessed the server frequently. As with the response code analysis We then filter the result based on the count of accesses by each host. Then, we select the 'host' column and show few elements from the result.

4. Find the top paths/request-strings (URIs) in the log.

5. Find top ten error paths which did not have return code 200?

6. How many unique hosts are there in the entire log?

7. Number of Unique Daily Hosts

8. Number of Daily Requests per Unique Host

9. Counting 404 Response Codes

10. Find top twenty request_string/paths that generate the most 404 errors.

11. Visualizing the 404 Errors by Day

12. Top Five Days for 404 Errors
