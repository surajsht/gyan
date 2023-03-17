# GoogleAuthProvider

#### Import GoogleAuthProvider and getAuth from firebase/auth

```javascript
import {GoogleAuthProvider, getAuth} from 'firebase/auth'
```

#### Initialize GoogleAuthProvider and getAuth in a variable and export it

```javascript
const auth = getAuth(app)
const googleProvider = new GoogleAuthProvider()

export {googleProvider, auth}
```

## How to use GoogleAuthProvider

### Import auth and googleProvider from **'firebase-config.jsx'** file

```javascript
import {auth, googleProvider} from 'firebase-config.jsx'
```

#### Import signInWithPopup from firebase/auth

```javascript
import {signInWithPopup} from 'firebase/auth'
```

#### Add "signup with google" button

```html
<button> signup with google </button>
```
#### when button is click call **signupwithgoogle** function

```html
<button onClick = {signupWithGoogle}> signup with google </button>
```

```javascript
let signupWithGoogle = async () => {
  try {
    await signInWithPopup(auth, googleProvider)
  } catch (error) {console.error(error)}
}
```
