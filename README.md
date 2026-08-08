student-management-system/
│
├── index.html
├── register.html
├── login.html
├── dashboard.html
├── students.html
├── style.css
├── script.js
├── README.md
└── images/
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Student Registration</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

    <div class="container">
        <h2>Student Registration</h2>

        <form id="registrationForm">
            <input type="text" id="name" placeholder="Student Name" required>

            <input type="email" id="email" placeholder="Email" required>

            <input type="text" id="rollNo" placeholder="Roll Number" required>

            <input type="text" id="course" placeholder="Course" required>

            <input type="password" id="password" placeholder="Password" required>

            <button type="submit">Register</button>
        </form>

        <p>Already registered?
            <a href="login.html">Login</a>
        </p>
    </div>

    <script src="script.js"></script>
</body>
</html>
document.getElementById("registrationForm").addEventListener("submit", function(event) {
    event.preventDefault();

    const student = {
        name: document.getElementById("name").value,
        email: document.getElementById("email").value,
        rollNo: document.getElementById("rollNo").value,
        course: document.getElementById("course").value,
        password: document.getElementById("password").value
    };

    localStorage.setItem("student", JSON.stringify(student));

    alert("Student registered successfully!");

    window.location.href = "login.html";
});
