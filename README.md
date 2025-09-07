<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>To-Do App</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f7f7f7;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }
    .todo-container {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      width: 300px;
    }
    h2 {
      text-align: center;
    }
    input {
      width: 75%;
      padding: 8px;
      border: 1px solid #ddd;
      border-radius: 5px;
    }
    button {
      padding: 8px 12px;
      margin-left: 5px;
      border: none;
      background: #4CAF50;
      color: white;
      border-radius: 5px;
      cursor: pointer;
    }
    button:hover {
      background: #45a049;
    }
    ul {
      list-style: none;
      padding: 0;
      margin-top: 15px;
    }
    li {
      padding: 8px;
      margin: 5px 0;
      background: #f1f1f1;
      border-radius: 5px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    li.done {
      text-decoration: line-through;
      color: gray;
    }
    .delete {
      background: red;
      padding: 5px 8px;
      border-radius: 5px;
      cursor: pointer;
      color: white;
      font-size: 12px;
    }
  </style>
</head>
<body>
  <div class="todo-container">
    <h2>To-Do</h2>
    <div>
      <input type="text" id="taskInput" placeholder="Add new task...">
      <button onclick="addTask()"> new task </button>
    </div>
    <ul id="taskList"></ul>
  </div>

  <script>
    function addTask() {
      let taskInput = document.getElementById("taskInput");
      let taskText = taskInput.value.trim();

      if (taskText === "") {
        alert("Please enter a task!");
        return;
      }

      let li = document.createElement("li");
      li.textContent = taskText;

      li.addEventListener("click", function() {
        li.classList.toggle("done");
      });

      let delBtn = document.createElement("span");
      delBtn.textContent = "X";
      delBtn.classList.add("delete");
      delBtn.onclick = function() {
        li.remove();
      };

      li.appendChild(delBtn);
      document.getElementById("taskList").appendChild(li);

      taskInput.value = "";
    }
  </script>
</body>
</html>


