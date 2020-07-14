# Network Debugging

**How can we send and receive test network requests while working on an application?
**

1. How can we inspect any requests the browser is making on an HTML page?

<p>
We can do it by inspect network activity in Chrome's Devtools! 
</p>
a

Click on Demo to start: [Demo](https://devtools.glitch.me/network/getstarted.html)


<p>
Open DevTools by pressing Control+Shift+J or Command+Option+J (Mac)
</p>

![](https://i.imgur.com/M5YFfkr.png)

<h2>
Log network activity
</h2>

<p>
Reload the page. The Network panel logs all network activity in the Network Log
</p>

![](https://i.imgur.com/PeEKB10.png)

<ul>
<li>**Status**: The HTTP response code.</li>
<li>**Type**: The resource type.</li>
<li>**Initiator**: What caused a resource to be requested Clicking a link in the Initiator column takes you to the source code that caused the request.
</li>
<li>**Time**: How long the request took.</li>
<li>**Waterfall**: A graphical representation of the different stages of the request. Hover over a Waterfall to see a breakdown.</li>
</ul>

<p>
click the Get Data button in the demo to add a new data resource.
</p>

<h2>
Simulate a slower network connection
</h2>

Due to throttling, mobile connections are slower than desktop. To simulate the experience in your desktop browser:
1. Click the Throttling dropdown, which is set to Online by default.
2. Select Slow 3G

![](https://i.imgur.com/HtFV1FS.png)

<p>
if you want to experience the time load like a first time visiter.
</p>

3. Long-press Reload Reload and then select Empty Cache And Hard Reload.

<h2>
To inspect individual resource
</h2>

click it's name!
* Headers tab show you http request and response headers
* Preview show you basic render of the resource
* Response tab show you the HTML source code

![](https://i.imgur.com/6w7tpjQ.png)

<h2>
Search network headers and responses
</h2>

The Search pane opens to the left of the Network log.

![](https://i.imgur.com/RwFGu2A.png)

<h2>
Filter resources
</h2>

Filter by string, regular expression, or property

![](https://i.imgur.com/mbXHpPG.png)



# 2. How can we manually send test requests outside of our browser?

there are two ways we can accomplish this! 

my personal favorite is:

# Postman!

In Postman you can make API requests and examine the responses without using a terminal or writing any code. When you create a request and click Send, the API response appears inside the Postman user interface.

So we can examine the API's properties without needing to dig deep inside the returned response manually

Each API request uses an HTTP methods. The most common methods and the ones we've been using GET, POST, PATCH, PUT, and DELETE.

* GET methods retrieve data from an API.
* POST sends new data to an API.
* PATCH and PUT methods update existing data.
* DELETE removes existing data.

![reference link](https://assets.postman.com/postman-docs/anatomy-of-a-request.png)


lets take a familiar example!

Remember the workshop with the Pokemon api? 
well, heres how we can get all we need using postman!
which might save us alot of time when looking into what fields are we getting and helps us identifying the key feils we want to use in our site

![Pokemon Postman](https://i.imgur.com/l1upIee.png)

We Use GET method to recive a String representation of the JSON respone, postman automatically detects its a json and converts it to one for easy readability

notice we can view the recived data in different formats based on our likings -- see the drop down with "json" in the image
this can be changed


ofcourse postman is really powerful and can replicate POST, DELETE, PUT and other HTTP methods based on the API we need to test
above we gave a small example for how we handled the workshop with GET method

:::info
:pushpin: Read more about the Capabilites of Postman here:
[POSTMAN in details](https://learning.postman.com/docs/sending-requests/requests/#adding-request-detail)
:::

<hr>

### another way is with using the commandline TOOL(and Library) 
# cURL!

 which can be used to receive and send data between a client and a server or any two machines connected over the internet. It supports a wide range of protocols like HTTP, FTP, IMAP, LDAP, POP3, SMTP and many more
 
but we will mainly focus on HTTP(S)!
 
>few examples can of what this command line tool can be used in is to download files, testing APIs and debugging network problems.

:::info 
:pushpin: 
for a full elaborated guide on what curl is capable off see link: [CURL COMMANDLINE TUTORIAL](https://www.booleanworld.com/curl-command-tutorial-examples/)
<br>

PS. to install curl on you LINUX machine use:  
```
sudo apt update
sudo apt install curl
```
:::

### cURL basic usage
The basic syntax of using cURL is simply:

```javascript 
curl <url>
```
This fetches the content available at the given URL, and prints it onto the terminal. For example, if you run curl example.com, you should be able to see the HTML page printed, as shown below:
![](https://www.booleanworld.com/wp-content/webp-express/webp-images/doc-root/wp-content/uploads/2018/12/curl-basic.png.webp)



we've seen in the above section on Postman how we can send GET request, for varities sake, lets use POST method with cURL!

### Making POST requests with cURL
By default, cURL sends GET requests, but you can also use it to send POST requests with the -d or --data option. All the fields must be given as key=value pairs separated by the ampersand (&) character. As an example, you can make a POST request to httpbin.org with some parameters:

```
curl --data "firstname=boolean&lastname=world" https://httpbin.org/post
```
From the output, you can easily tell that we posted two parameters (this appears under the “form” key):
![](https://www.booleanworld.com/wp-content/webp-express/webp-images/doc-root/wp-content/uploads/2018/12/curl-post-1.png.webp)


this is really powerful and we can make sure we are sending the intended data properly!

when we get the desired results, using cURL or postman, we can start actually sending this data to our servers, and to save to our databases knowing we are using the right Query, because we tested those beforehand with the help of postman and cURl!

:::info 
:pushpin: 
Again CURL might be simpler and less fancy tool for network debugging oppose to POSTMAN but its just as powerful!
make sure you go over this short guide for the full details 
[CURL COMMANDLINE TUTORIAL](https://www.booleanworld.com/curl-command-tutorial-examples/)
:::

<hr>
---
Resources:
{%youtube e1gAyQuIFQo %}


---
---
# debugger
1. we can add to code  as showing in the img below- 

``` debugger ``` 

![](https://i.imgur.com/bdJ6E67.jpg)

1. What `console` methods are there other than `console.log`?

---
![](https://i.imgur.com/5es448K.png)
![](https://i.imgur.com/pFeLhKM.png)
---
![](https://i.imgur.com/Oie1dtw.png)
![](https://i.imgur.com/7DZZcFu.png)

![](https://i.imgur.com/HgRIGLG.png)

#group

![](https://i.imgur.com/V2gYNxo.png)
![](https://i.imgur.com/44aACpu.png)


# how much time it takes to block of code to execute

![](https://i.imgur.com/z2NRwJ3.png)


# stylie the console 
![](https://i.imgur.com/VB8IkNK.png)


