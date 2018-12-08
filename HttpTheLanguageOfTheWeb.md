# What is Http? And who uses it?

Http is a protocol used for communication on the web. Whether you're aware of it or not, you are probably using HTTP everyday.
When type something into your web browser and click enter, your browser forms an HTTP request and sends it off to the server
responsible for delivering the content you're used to seeing. If you make a request to Facebook.com, a server from Facebook
will answer your HTTP request with a HTTP response.

# What's inside a request and a response?
Within a request, there are fields of interest, mainly: 
1. The HTTP method (for the action you are requesting)
2. The address of the page you are requesting (a URL)
3. Form parameters (other arguments)

# What does the server send back?
When the server receives your request, it will send back the following:
1. A status code (to tell you whether the request was successful or not)
2. Content-type (the type of content it's sending back)
3. The content (the actualy content you requested)

# The main HTTP methods
There are various methods that the HTTP protocol supports. However, we'll begin our discussion with GET and POST.
1. **GET**  --> ask the server to send some resources back
2. **POST** --> ask the server to send some resources back + send data to the server

A little fun fact is that you can actually send data using GET. However, there are few caveats:
1. The total amount of characters are limited (set by the server)
2. The data you send is visible in the browser's address bar

So if you don't care about the information you're sending to the server, then it might be perfectly fine to use GET to send
small amounts of data. However, keep in mind that anyone can see the data you're sending in the address bar! Typically,
you will see the following format with a GET request that sends data: *http://address.com/page?data1&data2&data3*.
The "?" marks that the characters after it is the data you are sending with your request!

# The HTTP request and response body
There are various fields in the request and response body of a request or response, let's go over a few of the most important
fields.

1. The Request Line : **POST** **/address/to/resource/** **HTTP/1.1**
The request line contains the HTTP method, URL or address where the resource lives, and the version of the protocol its using.

2. The Request Headers: This is a group of data containing things like the Host, User-Agent, Keep-Alive timer, and various
other information. (We'll glaze of this for now)
3. The Message Body or Payload: language=english&color=red

Inside the payload, lies our request parameters. This could be things like the language of our choice, our name, and favorite
color. Note that since this is a POST request the parameters lay in our message payload. If it were a GET request, this 
information would be in the request line.

Once we form this request body, we then send it off the server which will then process our request and send back a response!
In that message we have the following:

1. The HTTP response headers, which starts with a line similar to our Request Line:

   **HTTP/1.1** (version) **200** (A HTTP status code) **OK** (Text status code)
2. The MIME type: **text/html** which tells the browser what type of data it's getting back
3. Payload/Body: In the payload the server returns the data requested if the request was successfully completed!

Again please note that this a very high level overview of the pieces of a request and response. You can spend years and years
studying them but this should suffice for the purpose of a high level understanding or what's going on.


