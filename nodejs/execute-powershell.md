# How to run a Powershell script with Node.js

In order to execute a powershell script, you can spawn a child process `powershell.exe` and listen to output:

```javascript
var spawn = require("child_process").spawn,child;

child = spawn("powershell.exe",["c:\\temp\\helloworld.ps1"]);

child.stdout.on("data",function(data){
    console.log("Powershell Data: " + data);
});

child.stderr.on("data",function(data){
    console.log("Powershell Errors: " + data);
});

child.on("exit",function(){
    console.log("Powershell Script finished");
});

child.stdin.end();
```

References:
* https://stackoverflow.com/a/10181488/2524304