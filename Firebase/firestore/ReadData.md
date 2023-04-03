```jsx
import { useState, useEffect } from 'react'
import { db } from '/.fireConfig'
import { collection, getDocs } from 'firebase/firestore'

let ReadData = () => {
  let [user, setUser] = useState([])

  let dataCollection = collection(db, 'users')

  let getData = async () => {
    let data = await getDocs(dataCollection)
    setUser(data.docs.map((doc) => ({...doc.data(), id : doc.id})))
  }

  useEffect(() => {
    getData()
  }, [user])

  return (
    <div>
      {users.map((data) => {
        return <div className="item" key={data.id}>
          <h2> {data.name} </h2>
          <p> {data.age} </p>
        </div>;
      })}
    </div>
  );
}