# HTML (index.html) 
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>To-Do List App</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="app">
    <h1>To-Do List</h1>
    <div class="input-group">
      <input type="text" id="taskInput" placeholder="Enter a new task" />
      <button id="addBtn">Add</button>
    </div>
    <ul id="taskList"></ul>
  </div>

  <script src="script.js"></script>
</body>
</html>

# CSS(style.css) 
body {
  font-family: Arial, sans-serif;
  background-color: #f4f6f8;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.app {
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  width: 350px;
}

h1 {
  text-align: center;
  margin-bottom: 1rem;
}

.input-group {
  display: flex;
  margin-bottom: 1rem;
}

#taskInput {
  flex: 1;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px 0 0 5px;
}

#addBtn {
  padding: 10px 15px;
  background-color: #007bff;
  color: white;
  border: none;
  border-radius: 0 5px 5px 0;
  cursor: pointer;
}

#addBtn:hover {
  background-color: #0056b3;
}

ul {
  list-style: none;
  padding: 0;
}

li {
  background: #e9ecef;
  margin-bottom: 10px;
  padding: 10px;
  border-radius: 5px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

li.completed {
  text-decoration: line-through;
  opacity: 0.6;
}

button.delete-btn {
  background: none;
  border: none;
  color: red;
  cursor: pointer;
  font-size: 1.1rem;
}

# Javascript (script.js) 
document.getElementById("addBtn").addEventListener("click", addTask);

function addTask() {
  const input = document.getElementById("taskInput");
  const taskText = input.value.trim();

  if (taskText === "") return;

  const li = document.createElement("li");
  li.textContent = taskText;

  // Toggle complete
  li.addEventListener("click", function () {
    li.classList.toggle("completed");
  });

  // Delete button
  const deleteBtn = document.createElement("button");
  deleteBtn.textContent = "✕";
  deleteBtn.className = "delete-btn";
  deleteBtn.addEventListener("click", function (e) {
    e.stopPropagation(); // Prevent mark as complete
    li.remove();
  });

  li.appendChild(deleteBtn);
  document.getElementById("taskList").appendChild(li);

  input.value = "";
}

# Setup basic HTML 
<input type="text" id="taskInput" placeholder="Enter task" />
<button id="addBtn">Add</button>
<ul id="taskList"></ul>

# Style layout with CSS 
body { font-family: sans-serif; }
input, button { padding: 10px; }
ul { list-style: none; padding: 0; }
li { margin: 5px 0; padding: 10px; background: #eee; }
li.completed { text-decoration: line-through; color: gray; }

# Use JS to add event listeners
 document.getElementById("addBtn").addEventListener("click", addTask);

 # Append new tasks dynamically 
function addTask() {
  const input = document.getElementById("taskInput");
  const taskText = input.value.trim();
  if (taskText === "") return;

  const li = document.createElement("li");
  li.textContent = taskText;
  document.getElementById("taskList").appendChild(li);
  input.value = "";
}

# Implement mark complete (toggle class)

li.addEventListener("click", () => li.classList.toggle("completed"));

# Add remove button 
const deleteBtn = document.createElement("button");
deleteBtn.textContent = "✕";
deleteBtn.onclick = (e) => {
  e.stopPropagation();
  li.remove();
};
li.appendChild(deleteBtn);


# Test functionality 

Add tasks ✅

Click to complete ✅

Delete with button ✅

# Ensure instant UI update 

all updates happen dynamically in the DOM using JavaScript.

# OUTPUT 
you can check in live 
Copy the HTML, CSS, and JS code from earlier

Create three files:

index.html

style.css

script.js

Open index.html in a browser

# i have used html css js for this task 2 
