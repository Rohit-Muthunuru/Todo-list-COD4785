# Todo-list-COD4785
**Title: CodTech IT solutions Internship- Task Documentation : creating a To-do List web application using HTML,CSS and Javascript.**

**Introduction:**
This documentation provides a detailed information of the task assigned during the CodTech IT Solutions Internship program. The task involves creating a creating a To-do List web application using HTML,CSS and Javascript .This documentation will cover the implementation details,rational behind the code structure, and insights into the programming techniques utilized. Additionally, it will include information about the intern,Rohit Muthunuru and his assigned id, COD4785.

**Intern Information**
The task assigned to Rohit Muthunuru during the CodTech IT solutions internship program is to create a To-do List web application using HTML,CSS and Javascript.

**Implementation**
The implementation of the task involves utilizing Javascript programming language and it involves various pages like index.html, style.css and script.js. Below is the code explanation:


<-----------------------index.html------------------------------>
<!DOCTYPE html>
<html>
<head>
	<title>TODO List</title>
	<link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
	<header> 
		<div class="nav">
			<div class="head">
				<h1>TODO List</h1>
			</div>
		</div>
	</header>
	<main>
        <form>
            <input type="text" id="new-item" placeholder="Add a new task">
			<button type="submit">Add</button>
		</form>
		<ul id="list"></ul>
	</main>

	<script src="script.js"></script>
</body>
</html>
1.This is the main HTML file of the application.
2.It includes a header with the title "TODO List" and a form to add new tasks.
3.The form contains an input field for entering a new task and a submit button.
4.Below the form, there is an unordered list (<ul>) with the id list, where the tasks will be displayed.
5.It imports an external stylesheet style.css and JavaScript file script.js.

<-----------------------------------style.css-------------------------------------->
body {
	background-color: #f2f2f2;
	font-family: Arial, sans-serif;
	margin: 0;
}

.nav{
	display: flex;
	justify-content: space-between;
}

.head{
	align-items: center;
}
header {
	background-color: peru;
	color: #fff;
	padding: 20px;
}

header h1 {
	margin-left: 0px;
}

main {
	padding: 20px;
}

form input[type="text"] {
	padding: 10px;
	border-radius: 5px;
	border: none;
	margin-right: 10px;
	width: 70%;
}

form button {
	padding: 10px;
	border-radius: 5px;
	border: none;
	background-color: gray;
	color: #fff;
	cursor: pointer;
}

ul {
	list-style: none;
	padding: 0;
}

li {
	background-color: #fff;
	padding: 10px;
	margin: 10px 0;
	border-radius: 5px;
	box-shadow: 0px 0px 5px #ccc;
	display: flex;
	justify-content: space-between;
	align-items: center;
}

li .actions {
	display: flex;
	align-items: center;
}

li .actions button {
	padding: 5px;
	margin-left: 5px;
	background-color: #fff;
	border: none;
	cursor: pointer;
}
1.This file contains the CSS styles for the application's layout and appearance.
2.It styles the body background, font, header, form, input field, buttons, list items, and actions for each task.

<-------------------------script.js--------------------------------->
const form = document.querySelector('form');
const input = document.querySelector('#new-item');
const list = document.querySelector('#list');

let items = [];

function renderList() {
	list.innerHTML = '';
	items.forEach((item, index) => {
		const li = document.createElement('li');
		const actions = document.createElement('div');
		const deleteButton = document.createElement('button');
		const editButton = document.createElement('button');
		const checkbox = document.createElement('input');

		li.textContent = item.text;

		checkbox.type = 'checkbox';
		checkbox.checked = item.completed;
		checkbox.addEventListener('change', () => {
			items[index].completed = checkbox.checked;
			renderList();
		});

		deleteButton.textContent = 'Delete';
		deleteButton.addEventListener('click', () => {
			items.splice(index, 1);
			renderList();
		});

		editButton.textContent = 'Edit';
		editButton.addEventListener('click', () => {
			const newText = prompt('Enter new text:', item.text);
			if (newText !== null && newText !== '') {
				items[index].text = newText;
				renderList();
			}
		});

		actions.appendChild(checkbox);
		actions.appendChild(editButton);
		actions.appendChild(deleteButton);

		li.appendChild(actions);
		if (item.completed) {
			li.classList.add('completed');
		}
		list.appendChild(li);
	});
}

form.addEventListener('submit', (event) => {
	event.preventDefault();
	const text = input.value.trim();
	if (text !== '') {
		items.push({
			text,
			completed: false,
		});
		renderList();
		input.value = '';
		input.focus();
	}
});

renderList();

1.This file contains the JavaScript code responsible for the dynamic behavior of the application.
2.It starts by selecting the necessary DOM elements: form, input field, and list.
3.It initializes an empty array items to store the tasks.
4.The renderList() function is defined to render the list of tasks.
5.Inside renderList(), each task is rendered as an <li> element.
6.It creates elements for the task text, a checkbox, delete button, and edit button.
7.Event listeners are attached to the checkbox, delete button, and edit button for handling user interactions.
8.The task's completion status is updated when the checkbox is clicked.
9.Tasks can be deleted or edited using the delete and edit buttons respectively.
10.An event listener is added to the form to handle the submission of new tasks.
11.When a new task is submitted, it is added to the items array, and the renderList() function is called to update the UI.
12.Finally, renderList() is called once to initialize the list when the page loads.


**Conclusion:**
In conclusion the task assigned to Rohit Muthunuru during the CodTech IT Solutions internship program involved creating a ToDo List web application. The implemented solution successfully accomplishes the task. The documentation provides insights into implementation details,code explanation. Rohit Muthunuru with intern ID : COD4785 has effectively completed the task as a part of internship program.

This concludes the documentation of the task to "create a To-do List web application using HTML,CSS and Javascript." assigned during the CodTech IT Solutions Internship program.

