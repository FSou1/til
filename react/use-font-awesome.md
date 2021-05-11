# How to use font-awesome icons

Here are the packages that you need to install:
```
npm install --save @fortawesome/fontawesome-svg-core
npm install --save @fortawesome/free-solid-svg-icons
npm install --save @fortawesome/react-fontawesome
```

Here is a code example:
```javascript
import ReactDOM from 'react-dom'
import { FontAwesomeIcon } from '@fortawesome/react-fontawesome'
import { faCoffee } from '@fortawesome/free-solid-svg-icons'

const element = <FontAwesomeIcon icon={faCoffee} />
```

References:
* https://www.digitalocean.com/community/tutorials/how-to-use-font-awesome-5-with-react
* https://fontawesome.com/icons?d=gallery&p=2