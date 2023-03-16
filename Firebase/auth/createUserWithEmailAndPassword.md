## createUserWithEmailAndPassword

### Import getAuth from firebase/auth in firebase config file

```javascript
import {getAuth} from 'firebase/auth'
```

### Initialize app in getAuth method and export

```javascript
const auth = getAuth(app)

export {auth}
```

## How to use createUserWithEmailAndPassword

When a user signs in to your app, pass the user's email address and password to **createUserWithEmailAndPassword**

```javascript
import {auth} from 'firebase-config'
import { createUserWithEmailAndPassword } from 'firebase/auth'

  let signUp = async () => {
    try {
      await createUserWithEmailAndPassword(auth, email, password);
    } catch (error) { console.error(error); }
  };

  <button onClick = {signUp}> Sign up </button>
  ```