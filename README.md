# Ex03 To-Do List using JavaScript
## Date:24.08.2026

## AIM
To create a To-do Application with all features using JavaScript.

## ALGORITHM
### STEP 1
Build the HTML structure (index.html).

### STEP 2
Style the App (style.css).

### STEP 3
Plan the features the To-Do App should have.

### STEP 4
Create a To-do application using Javascript.

### STEP 5
Add functionalities.

### STEP 6
Test the App.

### STEP 7
Open the HTML file in a browser to check layout and functionality.

### STEP 8
Fix styling issues and refine content placement.

### STEP 9
Deploy the website.

### STEP 10
Upload to GitHub Pages for free hosting.

## PROGRAM
index.html
~~~
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>TaskFlow</title>

<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>

<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

<link rel="stylesheet" href="style.css">
</head>

<body>

<div class="blob blob1"></div>
<div class="blob blob2"></div>

<div class="container">

    <div class="header">
        <h1>TaskFlow</h1>
        <p>Organize your day beautifully.</p>
    </div>

    <div class="inputBox">
        <input
        id="taskInput"
        type="text"
        placeholder="Add a new task...">

        <button onclick="addTask()">
            Add Task
        </button>
    </div>

    <ul id="taskList"></ul>

</div>

<script src="script.js"></script>

</body>
</html>
~~~
style.css
~~~
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:'Poppins',sans-serif;
}

body{

    height:100vh;

    display:flex;
    justify-content:center;
    align-items:center;

    background:linear-gradient(135deg,#09090F,#151933,#232C5A);

    overflow:hidden;
}

.blob{

    position:absolute;
    border-radius:50%;
    filter:blur(100px);
}

.blob1{

    width:300px;
    height:300px;
    background:#6C63FF;
    top:-80px;
    left:-80px;
}

.blob2{

    width:280px;
    height:280px;
    background:#00D2FF;
    right:-70px;
    bottom:-70px;
}

.container{

    width:450px;

    background:rgba(255,255,255,.08);

    border:1px solid rgba(255,255,255,.15);

    backdrop-filter:blur(20px);

    border-radius:25px;

    padding:30px;

    color:white;

    box-shadow:0 15px 40px rgba(0,0,0,.35);

    z-index:10;
}

.header{

    text-align:center;
    margin-bottom:30px;
}

.header h1{

    font-size:35px;
    font-weight:700;
}

.header p{

    opacity:.7;
    margin-top:8px;
}

.inputBox{

    display:flex;
    gap:12px;
}

.inputBox input{

    flex:1;

    padding:14px;

    border:none;

    outline:none;

    border-radius:12px;

    background:rgba(255,255,255,.12);

    color:white;

    font-size:15px;
}

.inputBox input::placeholder{

    color:#d5d5d5;
}

.inputBox button{

    border:none;

    padding:14px 22px;

    border-radius:12px;

    background:linear-gradient(135deg,#6C63FF,#7B4DFF);

    color:white;

    cursor:pointer;

    font-weight:600;

    transition:.3s;
}

.inputBox button:hover{

    transform:translateY(-3px);

    box-shadow:0 10px 20px rgba(108,99,255,.4);
}

#taskList{

    margin-top:25px;
}

#taskList li{

    list-style:none;

    display:flex;

    justify-content:space-between;

    align-items:center;

    background:rgba(255,255,255,.10);

    margin-bottom:15px;

    padding:15px 18px;

    border-radius:15px;

    animation:fade .4s;
}

@keyframes fade{

    from{

        opacity:0;
        transform:translateY(20px);
    }

    to{

        opacity:1;
        transform:translateY(0);
    }
}

.task{

    display:flex;
    align-items:center;
    gap:12px;
}

.completed span{

    text-decoration:line-through;
    opacity:.5;
}

.actions{

    display:flex;
    gap:10px;
}

.actions button{

    width:38px;
    height:38px;

    border:none;

    border-radius:10px;

    color:white;

    cursor:pointer;

    transition:.25s;
}

.complete{

    background:#00C853;
}

.complete:hover{

    transform:scale(1.08);
}

.delete{

    background:#FF3D57;
}

.delete:hover{

    transform:scale(1.08);
}




~~~

script.js
~~~
function addTask(){

    const input=document.getElementById("taskInput");

    if(input.value.trim()==""){

        alert("Enter a task");
        return;
    }

    const li=document.createElement("li");

    li.innerHTML=`

        <div class="task">
            <span>${input.value}</span>
        </div>

        <div class="actions">

            <button class="complete">✓</button>

            <button class="delete">🗑</button>

        </div>

    `;

    li.querySelector(".complete").onclick=()=>{

        li.classList.toggle("completed");

    }

    li.querySelector(".delete").onclick=()=>{

        li.style.transform="translateX(100px)";
        li.style.opacity="0";

        setTimeout(()=>{

            li.remove();

        },250);

    }

    document.getElementById("taskList").appendChild(li);

    input.value="";
}

~~~
## OUTPUT
![alt text](image.png)

## RESULT
The program for creating To-do list using JavaScript is executed successfully.
