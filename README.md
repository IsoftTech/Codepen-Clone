Code pen Editor clone built with reactjs

To test it out, use the following codes:

###   HTML
```
<html lang="en">

<head>

  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>ToDo List | Using HTML - CSS , JS | 2020</title>

  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="styles.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.14.0/css/all.min.css">

</head>

<body>

  <div class="todoList">
    <div class="cover-img">
      <div class="cover-inner">
        <h3 id="dayName">Sunday</h3>
      </div>
    </div>

    <div class="content">
      <form class="add">
        <input type="text" name="add" placeholder="Add item...">
        <div class="input-buttons">
          <a href="#0" class="add-todo">
            <i class="fas fa-plus add plus-icon"></i>
          </a>
        </div>
      </form>
      <ul class="todos align">
        
       
        
        <li>
          <input type="checkbox" id="todo_1">
          <label for="todo_1">
            <span class="check"></span>
            	Church Service
          </label>
          <i class="far fa-trash-alt delete"></i>
        </li>

       
      </ul>
    </div>
  </div>

</body>

<script src="main.js"></script>

</html>
```

### CSS:

```
*,
*::before,
*::after {
  box-sizing: border-box;
  margin: 0;
}

body {
  min-height: 450px;
  height: 100vh;
  margin: 0;
  background: /*radial-gradient(
    ellipse farthest-corner at center top,
    #4a4a4a 0%,
    #212121 100%
  ); */  #282828;
  color: #fff;
  font-family: "Nunito", sans-serif;
}

button,
input,
select,
textarea {
  font-family: inherit;
  font-size: inherit;
  line-height: inherit;
}

.todoList {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 320px;
  height: 500px;
  background: #171717;
  border-radius: 10px;
  box-shadow: 0 7px 30px rgba(75, 70, 6, 0.3);
}

.cover-img .cover-inner {
  background: url(https://images.unsplash.com/photo-1565172265978-aaa872e3f618?ixlib=rb-1.2.1&auto=format&fit=crop&w=564&q=80);
  height: 190px;
  background-size: cover;
  background-position: 10%;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
  position: relative;
}

.cover-img .cover-inner::after {
  background: rgba(0, 0, 0, 0.3);
  content: "";
  top: 0;
  left: 0;
  position: absolute;
  width: 100%;
  height: 100%;
  border-top-left-radius: 10px;
  border-top-right-radius: 10px;
}

.cover-img h3 {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  font-family: "Nunito", sans-serif;
  text-transform: uppercase;
  font-size: 2rem;
  z-index: 10;
  color: rgba(255, 255, 255, 0.9);
  font-weight: 700;
}

.content {
  padding: 10px 20px;
}

.content form {
  display: flex;
  justify-content: space-between;
  margin-bottom: 15px;
  padding: 0 10px 0 5px;
  border-bottom: 1px solid #cccccc;
}

.content form > * {
  background: transparent;
  border: none;
  height: 35px;
}

.content input[type="text"] {
  padding: 0 5px;
  font-weight: 700;
  font-size: 1.2rem;
  color: #c7c7c7;
  outline: none;
}

.content input-buttons a {
  text-decoration: none;
}

.content input-buttons i {
  margin-top: 5px;
  font-size: 20px;
  color: #eaeaea;
}

.content ul .todos {
  margin-left: 0;
  padding: 0;
  letter-spacing: none;
  height: 220px;
  overflow: auto;
}

.align {
  padding: 0;
}

.content li {
  user-select: none;
  margin-bottom: 10px;
  display: flex;
  justify-content: space-between;
}

.content li i {
  color: #c3c3c3;
  font-size: 15px;
  cursor: pointer;
  padding: 5px 10px;
}

.content input[type="checkbox"] {
  display: none;
}

.content input[type="checkbox"] + label {
  color: #ffffff;
  font-size: 15px;
  cursor: pointer;
  position: relative;
  border-radius: 3px;
  display: inline-block;
  padding: 5px 5px 5px 40px;
}

.content input[type="checkbox"] + label:hover {
  color: #bebebe;
  background-color: #3e3e3e;
}

.content input[type="checkbox"] + label span.check {
  left: 4px;
  top: 50%;
  position: absolute;
  transform: translatey(-50%);
  width: 18px;
  height: 18px;
  display: block;
  background: #171717;
  border-radius: 3px;
  border: 1px solid #ffb510;
  box-shadow: -2px -2px 2px rgba(67, 67, 67, 0.5),
    inset 2px 2px 4px rgba(0, 0, 0, 0.5),
    inset -2px -2px 2px rgba(67, 67, 67, 0.3), 2px 2px 4px rgba(0, 0, 0, 0.3);
}

.content input[type="checkbox"]:checked + label {
  color: #e8e8e8;
  text-decoration: line-through;
}

.content input[type="checkbox"]:checked + label span.check {
  background-color: transparent;
  border-color: transparent;
  box-shadow: none;
}

.content input[type="checkbox"] + label span.check::after {
  width: 100%;
  height: 100%;
  content: "";
  display: block;
  position: absolute;
  background-image: url("https://www.freepnglogos.com/uploads/tick-png/check-mark-tick-vector-graphic-21.png");
  background-repeat: no-repeat;
  background-position: center;
  background-size: 16px 16px;
  transform: scale(0);
  transition: transform 300ms cubic-bezier(0.3, 0, 0, 1.5);
}

.content input[type="checkbox"]:checked + label span.check::after {
  transform: scale(1);
}

.content input[type="checkbox"] + label span.check::before {
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  display: block;
  content: "";
  position: absolute;
  border-radius: 50%;
  background: #d9d9d9;
  opacity: 0.8;
  transform: scale(0);
}

.content input[type="checkbox"]:checked + label span.check::before {
  opacity: 0;
  transform: scale(1.3);
  transition: opacity 300ms cubic-bezier(0.2, 0, 0, 1),
    transform 400ms cubic-bezier(0.3, 0, 0, 1.4);
}

.plus-icon {
    color:  #ffb510;
}
```
###               JS

 ```
const submitForm = document.querySelector(".add");
const addButton = document.querySelector(".add-todo");
const todoList = document.querySelector(".todos");
const list = document.querySelectorAll(".todos li");

const lang = navigator.language;

let date = new Date();

let dayName = date.toLocaleString(lang, {
  weekday: "long"
});

let listLenght = list.lenght;

const generateTempalate = (todo) => {
  const html = `<li>
                  <input type="checkbox" id="todo_${listLenght}">
                  <label for="todo_${listLenght}">
                    <span class="check"></span>
                    ${todo}
                  </label>
                  <i class="far fa-trash-alt delete"></i>
                </li>`;
  todoList.innerHTML += html;
};

function addTodos(e) {
  e.preventDefault();
  const todo = submitForm.add.value.trim();
  if (todo.length) {
    listLenght = listLenght + 1;
    generateTempalate(todo);
    submitForm.reset();
  }
}

submitForm.addEventListener("submit", addTodos);
addButton.addEventListener("click", addTodos);

function deleteTodos(e) {
  if (e.target.classList.contains("delete")) {
    e.target.parentElement.remove();
  }
}

todoList.addEventListener("click", deleteTodos);


 ```   


### `npm start`

