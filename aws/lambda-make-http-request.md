# How to make an HTTP request with AWS Lambda

In order to make an HTTP request with AWS Lambda and Node.js 14.x, you can use the default Node.js `https` module:

```javascript
const https = require('https');

exports.handler = async (event) => {
    let dataString = '';
    
    const response = await new Promise((resolve, reject) => {
        const req = https.get("https://pokeapi.co/api/v2/pokemon/ditto", function(res) {
          res.on('data', chunk => {
            dataString += chunk;
          });

          res.on('end', () => {
            resolve({
                statusCode: 200,
                body: JSON.stringify(JSON.parse(dataString), null, 4)
            });
          });
        });
        
        req.on('error', (e) => {
          reject({
              statusCode: 500,
              body: 'Something went wrong!'
          });
        });
    });
    
    return response;
};
```

References:
* https://betterprogramming.pub/aws-tutorial-about-node-js-lambda-external-https-requests-logging-and-analyzing-data-e73137fd534c