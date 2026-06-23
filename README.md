<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Professional Portfolio</title>

<link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" rel="stylesheet">

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:'Poppins',sans-serif;
scroll-behavior:smooth;
}

body{
background:linear-gradient(135deg,#0f172a,#1e293b);
color:white;
transition:.5s;
}

.light{
background:#f5f5f5;
color:#222;
}

header{
position:fixed;
width:100%;
top:0;
background:rgba(255,255,255,0.1);
backdrop-filter:blur(10px);
padding:15px 50px;
display:flex;
justify-content:space-between;
align-items:center;
z-index:1000;
}

.logo{
font-size:28px;
font-weight:bold;
color:#38bdf8;
}

nav a{
color:white;
text-decoration:none;
margin-left:25px;
font-weight:500;
}

.light nav a{
color:black;
}

.theme-btn{
padding:8px 15px;
border:none;
border-radius:20px;
cursor:pointer;
background:#38bdf8;
color:white;
}

section{
min-height:100vh;
padding:100px 10%;
display:flex;
justify-content:center;
align-items:center;
flex-direction:column;
}

.hero h1{
font-size:60px;
}

.hero span{
color:#38bdf8;
}

.typing{
font-size:28px;
margin-top:10px;
}

.btn{
margin-top:20px;
padding:12px 25px;
background:#38bdf8;
color:white;
text-decoration:none;
border-radius:30px;
}

.about{
text-align:center;
}

.skills-container{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
gap:20px;
width:100%;
margin-top:30px;
}

.skill{
background:rgba(255,255,255,0.1);
padding:20px;
border-radius:15px;
}

.bar{
background:#333;
height:10px;
border-radius:20px;
margin-top:10px;
overflow:hidden;
}

.progress{
height:100%;
background:#38bdf8;
}

.projects{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(300px,1fr));
gap:25px;
width:100%;
margin-top:30px;
}

.card{
background:rgba(255,255,255,0.1);
padding:25px;
border-radius:20px;
transition:.4s;
}

.card:hover{
transform:translateY(-10px);
}

.contact-form{
width:100%;
max-width:600px;
}

.contact-form input,
.contact-form textarea{
width:100%;
padding:15px;
margin:10px 0;
border:none;
border-radius:10px;
}

.contact-form button{
width:100%;
padding:15px;
border:none;
background:#38bdf8;
color:white;
border-radius:10px;
cursor:pointer;
}

footer{
text-align:center;
padding:20px;
}

.socials a{
font-size:25px;
color:#38bdf8;
margin:10px;
}

@media(max-width:768px){
.hero h1{
font-size:40px;
}
}
</style>
</head>
<body>

<header>
<div class="logo">Portfolio</div>

<nav>
<a href="#home">Home</a>
<a href="#about">About</a>
<a href="#skills">Skills</a>
<a href="#projects">Projects</a>
<a href="#contact">Contact</a>
<button class="theme-btn" onclick="toggleTheme()">Theme</button>
</nav>
</header>

<section id="home" class="hero">
<h1>Hello, I'm <span>Your Name</span></h1>
<div class="typing"></div>
<a href="#projects" class="btn">View Projects</a>
</section>

<section id="about" class="about">
<h2>About Me</h2>
<br>
<p>
Passionate Web Developer skilled in HTML, CSS, JavaScript,
creating responsive and interactive websites.
</p>
</section>

<section id="skills">
<h2>Skills</h2>

<div class="skills-container">

<div class="skill">
HTML
<div class="bar">
<div class="progress" style="width:95%"></div>
</div>
</div>

<div class="skill">
CSS
<div class="bar">
<div class="progress" style="width:90%"></div>
</div>
</div>

<div class="skill">
JavaScript
<div class="bar">
<div class="progress" style="width:85%"></div>
</div>
</div>

<div class="skill">
React
<div class="bar">
<div class="progress" style="width:80%"></div>
</div>
</div>

</div>
</section>

<section id="projects">
<h2>Projects</h2>

<div class="projects">

<div class="card">
<h3>Weather Dashboard</h3>
<p>Real-time weather app using API.</p>
</div>

<div class="card">
<h3>To-Do App</h3>
<p>Local storage based task manager.</p>
</div>

<div class="card">
<h3>Portfolio Website</h3>
<p>Responsive modern portfolio.</p>
</div>

</div>
</section>

<section id="contact">
<h2>Contact Me</h2>

<form class="contact-form" onsubmit="return validateForm()">
<input type="text" id="name" placeholder="Your Name">
<input type="email" id="email" placeholder="Your Email">
<textarea id="message" rows="5" placeholder="Message"></textarea>
<button type="submit">Send Message</button>
</form>

<div class="socials">
<a href="#"><i class="fab fa-linkedin"></i></a>
<a href="#"><i class="fab fa-github"></i></a>
<a href="#"><i class="fab fa-instagram"></i></a>
</div>

</section>

<footer>
© 2026 Your Portfolio | Designed with ❤️
</footer>

<script>
const words=[
"Frontend Developer",
"Web Designer",
"JavaScript Enthusiast",
"Problem Solver"
];

let i=0;
let j=0;
let current="";
let isDeleting=false;

function type(){
current=words[i];

if(!isDeleting){
document.querySelector(".typing").textContent=
current.substring(0,j++);
if(j>current.length){
isDeleting=true;
setTimeout(type,1000);
return;
}
}else{
document.querySelector(".typing").textContent=
current.substring(0,j--);
if(j<0){
isDeleting=false;
i=(i+1)%words.length;
}
}
setTimeout(type,100);
}
type();

function toggleTheme(){
document.body.classList.toggle("light");
}

function validateForm(){
let name=document.getElementById("name").value;
let email=document.getElementById("email").value;

if(name==="" || email===""){
alert("Please fill all fields");
return false;
}

alert("Message Sent Successfully!");
return true;
}
</script>

</body>
</html>
