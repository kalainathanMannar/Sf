<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Student Form</title>
<style>
    body {
        font-family: Arial, sans-serif;
        margin: 20px;
        background: #f2f2f2;
    }
    .container {
        width: 450px;
        margin: auto;
        padding: 20px;
        background: white;
        border-radius: 10px;
        box-shadow: 0 0 10px #aaa;
    }
    input, select, button {
        width: 100%;
        padding: 10px;
        margin: 8px 0;
        border-radius: 5px;
        border: 1px solid #555;
    }
    table {
        width: 100%;
        border-collapse: collapse;
        margin-top: 20px;
    }
    th, td {
        padding: 10px;
        border: 1px solid #333;
        text-align: center;
    }
    th {
        background: #333;
        color: white;
    }
    .delete-btn {
        background: red;
        color: white;
        padding: 5px 10px;
        border: none;
        border-radius: 4px;
        cursor: pointer;
    }
</style>
</head>
<body>

<div class="container">
    <h2>Student Registration Form</h2>

    <label>Name:</label>
    <input type="text" id="name">

    <label>Course:</label>
    <input type="text" id="course">

    <label>Gender:</label>
    <select id="gender">
        <option value="">Select</option>
        <option>Male</option>
        <option>Female</option>
        <option>Other</option>
    </select>

    <label>Age:</label>
    <input type="number" id="age">

    <label>Email ID:</label>
    <input type="email" id="email">

    <button onclick="addStudent()">Add Student</button>
</div>

<table id="studentTable">
    <tr>
        <th>Name</th>
        <th>Course</th>
        <th>Gender</th>
        <th>Age</th>
        <th>Email</th>
        <th>Delete</th>
    </tr>
</table>

<script>
function addStudent() {
    let name = document.getElementById("name").value;
    let course = document.getElementById("course").value;
    let gender = document.getElementById("gender").value;
    let age = document.getElementById("age").value;
    let email = document.getElementById("email").value;

    if (!name || !course || !gender || !age || !email) {
        alert("Please fill all fields");
        return;
    }

    let table = document.getElementById("studentTable");

    let row = table.insertRow();
    row.insertCell(0).innerHTML = name;
    row.insertCell(1).innerHTML = course;
    row.insertCell(2).innerHTML = gender;
    row.insertCell(3).innerHTML = age;
    row.insertCell(4).innerHTML = email;
    row.insertCell(5).innerHTML = 
        `<button class='delete-btn' onclick='deleteRow(this)'>Delete</button>`;

    // Clear input fields after adding
    document.getElementById("name").value = "";
    document.getElementById("course").value = "";
    document.getElementById("gender").value = "";
    document.getElementById("age").value = "";
    document.getElementById("email").value = "";
}

function deleteRow(btn) {
    let row = btn.parentNode.parentNode;
    row.remove();
}
</script>

</body>
</html>
