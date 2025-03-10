
- `fs.readFileSync()`
- `fs.writeSync()`
- `fs.writeFileSync()`
- `fs.renameFileSync()`
- `fs.fsyncSync()`
- `fs.appendFileSync`
- `fs.statSync()`
- `fs.readdirSync()`
- `fs.existsSync()`

This above function didn't Inherits the streams ca

#### Read File
demo.txt
```jsx
This is the data of the file
```
main.js
```jsx
var fs = require('fs')

console.log('Synchronos read method')
var data = fs.readFileSync('sample.txt')
console.log('Data of the file is ='+ data.toString())
```
output
```cmd
Synchronos read method
Data of the file is = This is the data of the file
```

#### Create File
In Node `fs` module provide multi ways to create a file 
- `fs.writeFileSync`
- `fs.writeSync`
- `fs.`