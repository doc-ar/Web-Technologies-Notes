# Table of Contents
1. [HTML](#HTML)
	1. [Tags](#Tags)
	2. [HTTP Request](<## HTTP Request>)
	3. [Forms](#Forms)
# HTML
- Hyper Text Markup Language
- HTML is a markup language used for structuring a webpage
- HTML is a tag based language
- All objects on a webpage are represented through tags in HTML
- The objects essentially build a tree like structure of elements called ***Document Object Model (DOM)***
- Any object tag that is enclosed inside another tag becomes a child tag
- HTML Documents are simple structures and they can be styled using [CSS](<Introduction to CSS>)

```
#This is the basic structure of an html code

<!DOCTYPE html>
<html>
<body>
    <div>
        <h1>This is Heading 1</h1>
        <h2>This is Heading 2</h2>
        <p>This is a paragraph</p>
        <a href="www.google.com">Google</a>
    </div>
</body>
</html>

In this example,
- <body> is a child of <html>
- <div> is a child of <body>
- <h1>, <h2>, <p>, and <a> have a parent tag <div>
```
## Tags
- All functions in HTML are done in tags
- The outermost tag is always ``</html>`` tag
- There are many different tags for the web
	- ``<p>`` tag for paragraph
	- ``<h1>`` tag for heading 1
	- ``<h2>`` tag for heading 2 and so on till heading 6
	- ``<div>`` tag for making a division which can be used for functions
	- ``<a>`` tag is short for anchor which is used for hyperlinks
- ``\<meta>`` tag is very important if a website is serious
	- Using ``<meta>`` tag to add Unicode (UTF-8) as a character set is optional but it is good business practice
	- Using keywords attribute can be used to add keywords to the website html
	- Using description tag
- Add images using ``</source>`` or ``</img>`` tag
	- Use **"src="** option to add image source
	- Use **"loading="** option to add lazy loading
	- use **"alt="** option to add information for handicapped and visually impaired people
	- Fix any **aspect ratio** issues while inserting the images
	- Its better practice to store multiple copies of an image in different aspect rations in the server instead of manually adjusting them in the html
	- Only use the required quality for the image. Using a larger size will use more bandwidth
	- The goal is to get better performance rather than using less storage
## HTTP Request
- Before moving on we need to understand how HTTP Requests work
- Whenever an ***HTTP request*** is made a URL is created and it has the following parts
	- The web server address
	- The request file address
	- The Query String
	- The request parameters are separated the by & operate after '?'
- An HTTP request is made with an HTTP request method. The HTTP request method can be any of the following four methods:
	- ***GET*** request is used to read data from the server
	- ***POST*** request is used to create a resource on the server
	- ***PUT*** request is used to update an existing resource on the server
	- ***DELETE*** request is used to remove a resource from the server
- There is a difference between POST and GET requests
	- In case of GET request, the data is sent in the header. In this case the data size is limited
	- In case of POST request, the data is sent in payload and there is no limit to the amount of data that can be transferred
- The *Host header*s from the HTTP request carries the IP address and some of the following information:
	- ***User Agent*** header is the browser, system details
	- ***Accept*** header is used to convey what file types are acceptable by the browser
	- ***Connection*** header requests the server to keep the connection alive
	- ***Refer*** Header states the last URL when the request was made
- ***HTTP Status Code*** is the response from the server. The common status codes are:
	- Status Code 200 means OK / Success
	- Status Code 404 means "Not Found"
	- Status Code 500 means "Error at Server"
	- Status Code 302 means "Permanent Redirect" which is used to redirect to a different URL

==Question:== What is the structure of the payload when a POST request has one or more files?
==Answer:== When ``Input type="file"`` is used, the ***Content Type*** of payload in request header is multi-part content
- The payload is structured each part of data is separated by payload boundaries. The packet structure of payload is as follows:
```
--------------------------- [Address 1]
Content information
[Content]
--------------------------- [Address 2]
Data information
[Content]
```
## Forms
- Forms in HTML are created under the ``<form>`` tag
	- Form tags have an *"action"* attribute where we can specify how we want to use the form
	- The *"method"* attribute is used to specify HTTP method
- ``<label>`` tag is used to create a label for the form input
- ``<input>`` tag is used to create an input type in the html
	- The input "type" attribute can be used to specify what we want to use as input
	- For Example: Checkbox, Textbox, File Picker, Submit Button etc.
- ``<br>`` tag is used for break / next line. It is used without a closing tag

```
This is a sample form code

<!DOCTYPE html>
<html>
	<body>
	        <form class="form">
	            <label>Name</label><br>
	            <input type="text" placeholder="First Name"><br>
	            <input type="text" placeholder="Last Name">
	            <br><br>
	
	            <label>Gender</label><br>
	            <input id="male-button" type="radio"><label for="male-button">Male</label>
	            <input id="female-button" type="radio"><label for="female-button">Female</label>
	            <br><br>
	
	  
	
	            <label>Date of Birth</label>
	            <input type="date">
	            <br><br>
	
	  
	
	            <label>Credit Card Number Information</label><br>
	            <input type="text" placeholder="Card Number">
	            <input type="text" size="3" placeholder="CVV"><br>
	            <label>Expiration date</label>
	            <input type="date">
	            <br><br>
	
	            <button>Submit</button>
	        </form>
	</body>
</html>
```

- ***Radio button*** sends a value of "on" in the HTTP request. This is not enough information most of the times
	- The radio button "value" attribute is used to tackle this issue
	- If we want to send a different value than the option to be sent in the request, we can also use the "value" attribute
		- Increases the performance of the query process
		- Decreases the size of query
- ***Hidden input field***
	- An input field that is not visible in the form but is sent as a parameter in the request query
- An input field can be converted to a submit button using ***type="button"***
	- The name attribute on this button can be used to add a name which is visible in the query
	- The default query value for this button is "Submit query" in a form
	- The value can be changed using the "value" attribute
