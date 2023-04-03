```jsx
import { useState } from 'react'
import { collection, addDoc } from 'firebase/firestore'
import { db } from './FireConfig'

let AddData = () => {
  let [newName, setNewName] = useState('')
  let [newAge, setNewAge] = useState('')

  let dataCollection = collection(db, 'user')

  let createUser = async () => {
    await addDoc(dataCollection, {
      name : newName,
      age : newAge
    })
  }

  return (
    <>
      <input type = 'text' value = {newName} onChange = {e => setNewName(e.target.value)} />
      <input type = 'text' value = {newAge} onChange = {e => setNewAge(e.target.value)} />
      <button onClick = {createUser}> Add </button>
    </>
  )

}