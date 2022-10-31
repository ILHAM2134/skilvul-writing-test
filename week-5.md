# Web Server & RESTful API

-   secara physical, web server terdiri dari 2 bagian :

    -   Hardware : On the hardware side, a web server is a computer that stores web server software and a website's component files. (for example, HTML documents, images, CSS stylesheets, and JavaScript files) A web server connects to the Internet and supports physical data interchange with other devices connected to the web.

    -   Software : On the software side, a web server includes several parts that control how web users access hosted files. At a minimum, this is an HTTP server. An HTTP server is software that understands URLs (web addresses) and HTTP (the protocol your browser uses to view webpages). An HTTP server can be accessed through the domain names of the websites it stores, and it delivers the content of these hosted websites to the end user's device.

-   ilustrasi cara kerja web server
    ![cara-kerja-web-server](./assets/week-5/1.%20ilustrasi%20web%20server.png "cara-kerja-web-server")

-   secara cara kerja, web server terbagi kedalam :

    -   Static Web Server : A static web server, or stack, consists of a computer (hardware) with an HTTP server (software). We call it "static" because the server sends its hosted files as-is to your browser.

    -   Dynamic Web Server : A dynamic web server consists of a static web server plus extra software, most commonly an application server and a database. We call it "dynamic" because the application server updates the hosted files before sending content to your browser via the HTTP server

-   Server Side Programming : Web servers wait for client request messages, process them when they arrive, and reply to the web browser with an HTTP response message. The response contains a status line indicating whether or not the request succeeded (e.g. "HTTP/1.1 200 OK" for success). The body of a successful response to a request would contain the requested resource (e.g. a new HTML page, or an image, etc...), which could then be displayed by the web browser.

-   Static Sites : The diagram on next slide shows a basic web server architecture for a static site (a static site is one that returns the same hard-coded content from the server whenever a particular resource is requested). When a user wants to navigate to a page, the browser sends an HTTP "GET" request specifying its URL.

-   Dynamic Site : A dynamic website is one where some of the response content is generated dynamically, only when needed. On a dynamic website HTML pages are normally created by inserting data from a database into placeholders in HTML templates (this is a much more efficient way of storing large amounts of content than using static websites).

-   A dynamic site can return different data for a URL based on information provided by the user or stored preferences and can perform other operations as part of returning a response (e.g. sending notifications).

-   Most of the code to support a dynamic website must run on the server. Creating this code is known as "server-side programming" (or sometimes "back-end scripting").

![static-server-side](./assets/week-5/2.%20server-client%20side.png "static-server-side")

    - Requests for static resources are handled in the same way as for static sites (static resources are any files that don't change —typically: CSS, JavaScript, Images, pre-created PDF files etc).

    - A simplified diagram of a web server that uses server-side programming to get information from a database and construct HTML from templates. This is the same diagram as is in the Client-Server overview. Requests for dynamic resources are instead forwarded to server-side code (shown in the diagram as a Web Application).

    - For "dynamic requests" the server interprets the request, reads required information from the database.

    - Combines the retrieved data with HTML templates and sends back a response containing the generated HTML (5,6)

-   What can you do on the server-side?

    -   Efficient storage and delivery of information : Imagine how many products are available on Amazon, and imagine how many posts have been written on Facebook? Creating a separate static page for each product or post would be completely impractical.

    -   Customised user experience : Servers can store and use information about clients to provide a convenient and tailored user experience. For example, many sites store credit cards so that details don't have to be entered again. Sites like Google Maps can use saved or current locations for providing routing information, and search or travel history to highlight local businesses in search results.

    -   Controlled access to content : Server-side programming allows sites to restrict access to authorized users and serve only the information that a user is permitted to see. Social networks like Facebook allow users to fully control their own data but only allow their friends to view or comment on it. The user determines who can see their data, and by extension, whose data appears in their feed — authorization is a central part of the user experience!

    -   Store session/state information : Server-side programming allows developers to make use of sessions — basically, a mechanism that allows a server to store information on the current user of a site and send different responses based on that information. This allows, for example, a site to know that a user has previously logged in and display links to their emails or order history, or perhaps save the state of a simple game so that the user can go to a site again and carry on where they left it.

    -   Notifications and communication : Servers can send general or user-specific notifications through the website itself or via email, SMS, instant messaging, video conversations, or other communications services.
        -   Facebook and Twitter send emails and SMS messages to notify you of new communications.
        -   Amazon regularly sends product e-mails that suggest products similar to those already bought or viewed that you might be interested in.
    -   Data analysis : A website may collect a lot of data about users: what they search for, what they buy, what they recommend, how long they stay on each page. Server-side programming can be used to refine responses based on analysis of this data. Amazon and Google both advertise products based on previous searches (and purchases)

-   REST : REpresentational State Transfer, is an architectural style for providing standards between computer systems on the web, making it easier for systems to communicate with each other. REST-compliant systems, often called RESTful systems, are characterized by how they are stateless and separate the concerns of client and server

-   In the REST architectural style, the implementation of the client and the implementation of the server can be done independently without each knowing about the other. This means that the code on the client side can be changed at any time without affecting the operation of the server, and the code on the server side can be changed without affecting the operation of the client.

-   By using a REST interface, different clients hit the same REST endpoints, perform the same actions, and receive the same responses. Clients can be web platform, mobile platform, or desktop platform.

-   Communication between Client and Server

    -   Making Requests : REST requires that a client make a request to the server in order to retrieve or modify data on the server. A request generally consists of:

        -   an HTTP verb, which defines what kind of operation to perform
        -   a header, which allows the client to pass along information about the request
        -   a path to a resource
        -   an optional message body containing data
        -   REQ terdiri dari :
            -   GET — retrieve a specific resource (by id) or a collection of resources
            -   POST — create a new resource
            -   PUT — update a specific resource (by id)
            -   DELETE — remove a specific resource by id

    -   Headers and Accept Parameters

        -   In the header of the request, the client sends the type of content that it is able to receive from the server. This is called the Accept field, and it ensures that the server does not send data that cannot be understood or processed by the client. The options for types of content are MIME Types (or Multipurpose Internet Mail Extensions, which you can read more about in the MDN Web Docs

        -   Other types and commonly used subtypes:
            -   image — image/png, image/jpeg, image/gif
            -   audio — audio/wav, audio/mpeg
            -   video — video/mp4, video/ogg
            -   application — application/json, application/pdf, application/xml, application/octet-stream

    -   Paths

        -   Requests must contain a path to a resource that the operation should be performed on. In RESTful APIs, paths should be designed to help the client know what is going on.

        -   A path like skilvulstore.com/customers/223/orders/12 is clear in what it points to, even if you’ve never seen this specific path before, because it is hierarchical and descriptive. We can see that we are accessing the order with id 12 for the customer with id 223.

    -   Response

        -   Content Types : For example, when a client is accessing a resource with id 23 in an articles resource with this GET Request:

            ```
            GET /articles/23 HTTP/1.1
            Accept: text/html, application/xhtml
            ```

        -   The server might send back the content with the response header:

            ```
            HTTP/1.1 200 (OK)
            Content-Type: text/html
            ```

        -   Response Codes : Responses from the server contain status codes to alert the client to information about the success of the operation. As a developer, you do not need to know every status code (there are many of them), but you should know the most common ones and how they are used.

        ![response-code](./assets/week-5/3.%20status-response.png "response-code")

# Node JS

## Intro

-   Node.js is an open-source, cross-platform, back-end JavaScript runtime environment that runs on the V8 engine and executes JavaScript code outside a web browser. Node.js lets developers use JavaScript to write command line tools and for server-side scripting—running scripts server-side to produce dynamic web page content before the page is sent to the user's web browser.

-   Arsitektur Node JS

    -   Single Thread : Thread dalam ilmu komputer adalah eksekusi menjalankan beberapa tugas atau program secara bersamaan. Setiap unit yang mampu mengeksekusi kode disebut thread. Javascript menggunakan konsep single thread, yang berarti hanya memiliki satu tumpukan panggilan yang digunakan untuk menjalankan program.

    -   Javascript menggunakan call stack untuk melakukan manajemen single thread. Ketika terdapat perintah baru maka akan ditambahkan (push) dan akan di keluarkan ketika perintahnya sudah selasai (pop)

    ![js-single-thread](./assets/week-5/4.js-single-thread.png "js-single-thread")

    -   Even Loop : Dengan menggunakan konsep arsitektur javascript, walaupun menggunakan single thread tetapi kita dapat melihat javascript seperti menggunakan multi thread Terdapat event queue yang berguna sebagai penampung ketika terdapat perintah baru yang akan dieksekusi. Event loop akan memfasilitasi kondisi ini, event loop akan memeriksa terus menerus, ketika antrian kosong di call stack maka akan menambah antrian baru dari event queue sampai semua perintah selesai di eksekusi.

    -   Server side scripting : Sejatinya javascript merupakan bahasa pemrograman yang digunakan di front end side. Sehingga kita hanya bisa mengerjakan javascript dengan menggunakan browser untuk menampilkan hasil eksekusinya. Tetapi dengan menggunakan NodeJS kita dapat menjalankan javascript di server side menggunakan terminal command line menggunakan perintah “node”.

## Instalasi NodeJS

-   install Node JS pada Debian-based Linux menggunakan command pada terminal

    ```
    sudo apt update

    sudo apt install nodejs
    ```

-   untuk mengecek versi, digunakan command

    ```
    node -v

    npm-v
    ```

-   untuk menjalankan REPL NodeJS, bisa menggunakan command

    ```
    node
    ```

    ![REPL-node](./assets/week-5/5.node-REPL.png "REPL-node")

-   beberapa built-in module pada node JS
    -   console : menampilkan kode / debug
    -   process : menampilkan / mengontrol proses Node JS yg sedang dijalankan
    -   os : menyediakan informasi terkait sistem operasi komputer yang digunakan user.
    -   util : Module Util merupakan alat bantu / utilities untuk mendukung kebutuhan internal API di Node JS
    -   errors : modules yang dapat digunakan untuk mendefinisikan error di Node JS sehingga lebih informatif. Kita juga dapat menghandle error menggunakan try catch
    -   fs : module yang dapat membantu berinteraksi dengan file yang ada diluar code. FS paling sering digunakan untuk membaca file dengan ekstensi .txt, .csv, dan .json

## NodeJS for Back End Development

-   Node.js memiliki built-in modul yang disebut HTTP, built-in modul ini memungkinkan Node JS mentransfer data melalui Hyper Text Transfer Protocol (HTTP). Modul HTTP dapat membuat server HTTP yang mendengarkan port server dan memberikan respons kembali ke klien.
-   Node JS Web Server

    -   Untuk menggunakan modul HTTP, gunakan require()
    -   Gunakan method createServer() untuk membuat server HTTP
    -   Callback function yang digunakan pada method http.createServer(), akan dijalankan ketika seseorang mencoba mengakses komputer pada port 8080.

    ```
    const http = require('http');

    http.createServer((req, res) => {
        res.write('hello from server');
        res.end();
    }).listen(8080);
    ```

-   Menambahkan HTTP Header

    -   Kita bisa menggunakan method res.writeHead() untuk menambahkan header HTTP.
    -   Argumen pertama dari method res.writeHead() adalah status code, 200 berarti semuanya OK
    -   Argumen kedua adalah objek yang berisi header respons.
    -   Contoh : Jika respons dari server HTTP seharusnya ditampilkan sebagai HTML, maka kita harus menambahkan header HTTP dengan tipe konten yang benar

    ```
    const http = require('http')

    http.createServer((req, res) => {
        res.writeHead(200, {'Content-Type': 'text/html'});
        res.write('hello dari server');
        res.end();
    }).listen(8080);
    ```

-   Membaca Query String

    -   Callback function pada method http.createServer() memiliki argumen req yang mewakili request dari klien, sebagai objek (objek http.IncomingMessage).

    -   Objek ini memiliki sebuah properti yang disebut "url" yang menyimpan informasi url yang sedang mengakses.

    ```
    const http = require('http');

    http.createServer((req, res) => {
        res.writeHead(200, {'Content-Type': 'text/html'});
        res.write(req.url);
        res.end();
    }).listen(8080);
    ```

# Express JS

## Intro

-   Express.js, or simply Express, is a back end web application framework for Node.js, released as free and open-source software under the MIT License. It is designed for building web applications and APIs. It has been called the de facto standard server framework for Node.js.

-   Back end app adalah aplikasi yang berjalan di server-side yang bekerja untuk memberikan informasi berupa data sesuai request dari client / browser / front end app. Umumnya server-side app membuat REST API
-   Kelebihan dari framework ini terletak pada fitur caching, support dengan Google V8 Engine, JavaScript, serta didukung oleh komunitas dan skalabilitas aplikasi yang baik.
-   REST (Representional State Transfer) adalah sebuah arsitektur metode komunikasi yang menggunakan protokol HTTP untuk pertukaran data dimana metode ini sering diterapkan dalam pengembangan aplikasi. Dengan tujuannya untuk menjadikan sistem memiliki performa yang baik, cepat dan mudah untuk di kembangkan (scale) terutama dalam pertukaran dan komunikasi data.
-   RESTFUL API memiliki 4 komponen penting yaitu:

    -   URL Design
    -   HTTP Verbs
    -   HTTP Response Code
    -   Format Response

-   Instalasi menggunakan npm

    ```
    npm install express --save
    ```

-   nodemon juga perlu diinstall (opsional) untuk memudahkan proses development

    ```
    npm install --save-dev nodemon
    ```

## Syntax

-   syntax dasar

    ```
    const express = require('express');
    const app = express();
    const PORT = 3000;

    app.get('/', (req, res) => {
        res.send('hello from server');
    });

    app.listen(PORT, () => {
        console.log(`app berjalan pada http://localhost:${PORT}`);
    });
    ```

-   Routes : sebuah end point yang diapat kita akses menggunakan URL di website. Didalam routes kita perlu menentukan method API, alamat dan response apa saja yang akan dikeluarkan

-   Response : Di dalam route kita dapat mengirim response menggunakan parameter dari route express.js yaitu “res.Send()” untuk mengirim plain text ketika kita mengakses route tersebut. Terdapat banyak response yang bisa kita buat selain yang dicontohkan.

-   Kita dapat mengirim response berupa output json yang biasa dipakai untuk back end application. Dengan menggunakan output json maka kita dapat mengirim data yang mudah diakses

```
app.get('/hello', (req, res) => {
    res.json({
        name: 'budi',
        age: 23,
        greeting: 'halo, salam kenal'
    })
})
```

-   Middleware function adalah sebuah fungsi yang memiliki akses ke object request (req), object response (res), dan sebuah fungsi next didalam request-response cycle.
-   yang bisa dilakukan oleh function middleware
    -   Menjalankan kode apapun.
    -   Memodifikasi Object Request dan Object Response.
    -   Menghentikan request-response cycle.
    -   Melanjutkan ke middleware function selanjutnya atau ke handler function dalam suatu request response cycle.
-

# Database MySQL
