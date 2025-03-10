### FS (FileSystem)
`fs` module is used to store the data from the file, read from the file, Here there are two type of functions are available
- Asyncronus fs functions
- Syncronus fs functions

and the common use of file systems
- Read files
- Create files
- Update files
- Delete files
- Rename files
#### Read Files
demo.html
```html
<html>  
<body>  
<h1>My Header</h1>  
<p>My paragraph.</p>  
</body>  
</html>
```

node file used to read the demo.html
```node
var fs = require('fs');
var http = require('http');

http.createServer(function(req,res)=>{
	fs.readFile('demo.html',function(err,data)=>{
		res.writeHead(200,{'content-type':'html/css'})
		res.write(data)
		return res.end();
	})
}).listen(3000,()=>console.log('server is listned'))
```

Here `fs.readFile` Takes two arguments `filename`,`function`  That function have two arguments if file is readed `error` ,`data`  
#### Create Files
The File System module has methods for creating new files:

- `fs.appendFile()`
- `fs.open()`
- `fs.writeFile()`
- 
The `fs.appendFile()` method appends specified content to a file. If the file does not exist, the file will be created:

```node
var fs = require('fs')

fs.appendFile('demo.text','Hello-Content!',function(err)=>{
	if(err) throw err
	console.log('Saved')
})
```

The `fs.open()` method takes a "flag" as the second argument, if the flag is "w" for "writing", the specified file is opened for writing. If the file does not exist, an empty file is created:

```node
var fs = require('fs');  
  
fs.open('mynewfile2.txt', 'w', function (err, file) {  
  if (err) throw err;  
  console.log('Saved!');  
});
```

The `fs.writeFile()` method replaces the specified file and content if it exists. If the file does not exist, a new file, containing the specified content, will be created:

```node
var fs = require('fs');  
  
fs.writeFile('mynewfile3.txt', 'Hello content!', function (err) {  
  if (err) throw err;  
  console.log('Saved!');  
});
```

#### Update Files
The file module has methods for updating files:
- fs.appendFile()
- fs.writeFile()

The `fs.appendFile()` add the content without deleting the old content, it joins the content at end of the file

myfile.txt
```txt
This is the first data
```

```node
var fs = require('fs')

fs.appendFile('myfile.txt','This is the data',function(err){
	if(err) throw err;
	console.log('File updated successfully')
})
```

output:
```txt
This is the fist data
this is the data
```

But `fs.writeFile` replace the content with given new content

```node
var fs = require('fs')

fs.writeFile('myfile.txt','This is the data',function(err){
	if(err) throw err;
	console.log('File writed successfully')
})
```

output:

```txt
This is the data
```

It remove the `This is the first data`  content 

#### Delete Files

The delete a file with the File System module. use the `fs.unlink()` method.

The `fs.unlink()` method deletes the specified files.

```jsx
var fs = require('fs')

fs.unlink('demo.txt',function(err){
	if(err) throw err;
	console.log('File Deleted')
})
```

#### Rename Files

To rename a file with the File System module, use the `fs.rename()` method.

The `fs.rename()` method renames the specified here.

**Example**
```jsx
var fs = require('fs')

fs.rename('mynewfile.txt','myrenamedFile.txt',function(err){
	if(err) throw err
	console.log('File Renamed')
})
```

The above all function are worked on asynchronous behaviour. If you want to synchronous behaviour based function. [>>>FS File Sync](FS%20Sync.md)
