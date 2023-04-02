# __Authentication__

## **create user with email and password**

### Import getAuth method from 'firebase/auth'

```javascript
import {getAuth} from 'firebase/auth'
```

### Initialize Firebase Authentication and get a reference to the service

```javascript
let auth = getAuth(app)

export {auth}
```

## **Signing up user with createUserWithEmailAndPassword**

### Import createUserWithEmailAndPassword from 'firebase/auth'

```jsx
import { createUserWithEmailAndPassword } from 'firebase/auth'
```

### Import auth from FireConfig.jsx file

```jsx
import { auth } from "./FireConfig"
```

### Create a state form email and password

```jsx
import { useState } from 'react'

let [email, setEmail] = useState('')
let [password, setPassword] = useState('')
```

### Use async await method to create a new user

```jsx
let signUpUser = async () => {
  try {
    await createUserWithEmailAndPassword(aut, email, password)
  } catch (e) {
    console.error(e)
  }
}
```

### Initialize signUpUser function in button

```jsx
<div>
  <input type = 'text' value = {e => setEmail(e.target.value)} />
  <input type = 'password' value = {e => setPassword(e.target.value)} />
  <button onClick = {signUpUser}> Sign up </button>
</div>
```

## Display user email after signing up

- Import useState from 'react'
- Import userEffect from 'react'
- Import onAuthStateChanged from 'firebase/auth'

```jsx
import { useState, useEffect } from 'react'
import { onAuthStateChanged } from 'firebase/auth'
```

### Create a state to store user info

```jsx
let [authUser, setAuthUser] = useState('')
```

### call onAuthStateChanged inside useEffect

```jsx
useEffect(() => {
  onAuthStateChanged(auth, (user) => {
    setAuthUser(user)
  })
}, [])
```

### Display user email

```jsx
 <div className="user-info">
        Logged in as : {loggedinUser.email}
      </div>
      