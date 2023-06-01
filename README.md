# todoapp
App.js
--------------
import './App.css';
import TodoListItem from'./TodoListItem.js';
import todos from './todos.js';
import Todoinsert from './Todoinsert.js';

function App() {
  return (
    <div>
        <Todoinsert/>
      </div>
  );
}

export default App;
--------------------------------------------
TodoInsert.js
--------------------------------------------
import React,{useState} from 'react';
const Todoinsert=()=>{
const[todos,setTodos]=useState([]);
const[newTodo,setNewTodo]=useState('');

const handleInputChange = (event) => {
    setNewTodo(event.target.value);
  };

  const handleFormSubmit = (event) => {
    event.preventDefault();
    if (newTodo.trim() !== '') {
      setTodos([...todos, newTodo]);
      setNewTodo('');
    }
  };


return(
    <div>
        <h1>Todo List</h1>
      <form onSubmit={handleFormSubmit}>
        <input
          type="text"
          placeholder="Enter a new todo"
          value={newTodo}
          onChange={handleInputChange}
        />
        <button type="submit">Add</button>
      </form>
      <ul>
        {todos.map((todo, index) => (
          <li key={index}>{todo}</li>
        ))}
      </ul>
    </div>
);
}
export default Todoinsert;

--------------------------------------------------
------------------------------------------------------
const todos = [
    { id: 1, text: 'Finish homework', completed: false },
    { id: 2, text: 'Go for a run', completed: false },
    { id: 3, text: 'Buy groceries', completed: true }
  ];
  
  export default todos;
  ------------------------------------------------
