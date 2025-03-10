`HTTP` is used to create a server.

```node.js
const http = require('http');

const server = http.createServer((req,res)=>{
	res.writeHead(200,{'Content-Type':'text/html'});
	res.write('Hello world');
	res.end();
})

server.listen(5000,()=>{
	console.log('Server started to listen')
})
```

Here, `createServer` function takes one funtional argument, That
Function takes two argumet as `request` and `responds` 

`request` is helps to get the data from the client side.
`responds` is helps to show the data from the client side.

---
we can show the result for using respective `URLS` too,

```node.js
const http = require('http');

const server = http.createServer((req,res)=>{
	if(req.url=='/write'){
		fs.appendFile('hello.txt','hello-content',funtion(err){
			if(err) throw err

			res.writeHead(200,{'Content-type':'text/html'})
			res.write('File Writed and Saved success')
			res.end()
		})
	}
	else if(req.url=='/read'){
		fs.readFile('hello,txt',function(data,err){
			if(err) throw err

			res.writeHead(200,{'Content-type':'text/html'})
			res.write(data)
			res.end()
		})
	}
})
```

Here, server can present the result respectively for the `url` using `req.url`

`req.url` is a function is used to get the `urls` data of our web application

other than `fs.appendFile` and `fs.readFile` you can refer [[FS]]

```node
http.createServer((req,res)=>{
	res.writeHead(200,{'Content-type':'text/html'})
	res.write(req.url)
	res.end()
}).listen(3000,()=>console.log('server is listned'))
```
the output is 
![[Pasted image 20240807124255.png]]

