## Aim:Build a To-Do List Application Using ES6 JavaScript
## program:
```
<!DOCTYPE html>
<html>
<head>
  <title>To-Do List</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #c6c90f;
    }

    .container {
      max-width: 1000px;
      margin: 500px auto;
      padding: 50px;
      background-color: #fff;
      border: 1px solid #ddd;
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    }

    .header {
      background-color: #333;
      color: #fff;
      padding: 30px;
      text-align: center;

    }

    .header h1 {
      font-size: 50px;
      margin: 10;
    }
    .header span {
      font-size: 16px;
      margin-right: 10px;
    }

   .header span.instruction {
      font-size: 32px;
      color: #ccc;
    }

    .input-field {
      padding: 30px;
      width: 95%;
      font-size: 40px;
      border: 1px solid #ccc;
    }

    .add-button {
      background-color: #4CAF50;
      color: #fff;
      padding: 30px 50px;
      border: none;
      border-radius: 15px;
      cursor: pointer;
      font-size: 30px;
    }

    .add-button:hover {
      background-color: #3e8e41;
    }

    .todo-list {
      list-style: none;
      padding: 0;
      margin: 0;
      font-size: 30px;

    }

    .todo-list li {
      padding: 10px;
      border-bottom: 1px solid #ccc;
    }

    .todo-list li:last-child {
      border-bottom: none;
    }

    .todo-list li span {
      margin-right: 10px;
    }

    .todo-list li button {
      
      background-color: #145ac4;
      border: none;
      padding: 25px 70px;
      font-size: 30px;
      cursor: pointer;
    }

    .todo-list li button:hover {
      background-color: #cccccc;
    }

    .todo-list li.completed {
      text-decoration: line-through;
      color: #ccc;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">
      <h1>To-Do List</h1>
      <span class="instruction">Enter a new task and click "Add Task" to add it to your list.</span>
      <span class="instruction">Click "Done" when you've completed a task to mark it as finished.</span>
      <span class="instruction">Click "Delete" to remove a task from your list.</span>
     </div>
    <input type="text" id="new-task" class="input-field" placeholder="Enter new task">
    l
    <button id="add-task" class="add-button">Add Task</button>
    <ul id="todo-list" class="todo-list"></ul>
  </div>

  <script>
    let todoList = [];

    document.getElementById("add-task").addEventListener("click", addTask);

    function addTask() {
      let newTask = document.getElementById("new-task").value;
      if (newTask !== "") {
        todoList.push({ task: newTask, completed: false });
        document.getElementById("new-task").value = "";
        renderList();
      }
    }

    function renderList() {
      let listHTML = "";
      todoList.forEach((task, index) => {
        listHTML += `
          <li ${task.completed ? "class='completed'" : ""}>
            <span>${task.task}</span>
            <button onclick="toggleCompleted(${index})">${task.completed ? "Undo" : "Done"}</button>
            <button onclick="deleteTask(${index})">Delete</button>
          </li>
        `;
      });
      document.getElementById("todo-list").innerHTML = listHTML;
    }

    function toggleCompleted(index) {
      todoList[index].completed = !todoList[index].completed;
      renderList();
    }

    function deleteTask(index) {
      todoList.splice(index, 1);
      renderList();
    }
    
  </script>
</body>
</html>
```
## Output:
![Screenshot (574)](https://github.com/chgeethika/to-do-list/assets/142209368/e17296f5-769f-4c18-904e-27da87706a28)

![Screenshot (575)](https://github.com/chgeethika/to-do-list/assets/142209368/667146b3-cbc1-40eb-95e7-5fae6518f06e)
