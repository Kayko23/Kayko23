<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Diplomatic Portal</title>
    <link rel="stylesheet" href="styles.css">
    <script>
        // JavaScript to toggle content visibility
        document.addEventListener("DOMContentLoaded", () => {
            const menuLinks = document.querySelectorAll(".menu a");
            const sections = document.querySelectorAll(".main-content section");

            menuLinks.forEach(link => {
                link.addEventListener("click", (event) => {
                    event.preventDefault();

                    // Hide all sections
                    sections.forEach(section => section.style.display = "none");

                    // Remove active class from all links
                    menuLinks.forEach(menu => menu.classList.remove("active"));

                    // Show the clicked section
                    const target = link.getAttribute("href").substring(1); // Remove '#' from ID
                    document.getElementById(target).style.display = "block";

                    // Add active class to clicked link
                    link.classList.add("active");
                });
            });

            // Initially display the first section
            sections.forEach((section, index) => {
                section.style.display = index === 0 ? "block" : "none";
            });
        });
    </script>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            display: flex;
        }

        .sidebar {
            width: 20%;
            background-color: #08b5c2;
            color: #ffffff;
            padding: 20px;
            height: 100vh;
        }

        .sidebar h2 {
            margin-bottom: 20px;
            font-size: 20px;
        }

        .sidebar ul {
            list-style: none;
        }

        .sidebar ul li {
            margin-bottom: 15px;
        }

        .sidebar ul li a {
            color: #ffffff;
            text-decoration: none;
            font-size: 16px;
            transition: color 0.3s;
        }

        .sidebar ul li a:hover {
            color: #94eb19;
        }

        .main-content {
            flex: 1;
            padding: 20px;
        }

        .container {
            max-width: 1200px;
            width: 100%;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
        }

        .card {
            background-color: #ffffff;
            width: 30%;
            border-radius: 10px;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
            margin: 20px 0;
            padding: 20px;
        }

        .card h3 {
            margin-bottom: 15px;
            font-size: 18px;
            color: #333333;
        }

        .card button {
            background-color: #67a60e;
            color: #ffffff;
            border: none;
            border-radius: 5px;
            padding: 10px 15px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        .card button:hover {
            background-color: #de940b;
        }

        .notification {
            background-color: #ffcccc;
            color: #ff0000;
            padding: 10px;
            border-radius: 5px;
            margin-bottom: 20px;
        }

        .notification.expire {
            background-color: #ffedcc;
            color: #cc8400;
        }
    </style>
</head>
<body>
    <div class="sidebar">
        <h2>Dashboard</h2>
        <ul>
            <li><a href="#">Home Page</a></li>
            <li><a href="#">Mission Info</a></li>
            <li><a href="#">Personnel</a></li>
            <li><a href="#">Local Staff</a></li>
            <li><a href="#">Airport Entrance Card List</a></li>
            <li><a href="#">%VAT</a></li>
            <li><a href="#">Tax Exemption Cards (détaxe)</a></li>
            <li><a href="#">Vehicles</a></li>
            <li><a href="#">Vehicles Applications</a></li>
            <li><a href="#">VIP Application</a></li>
            <li><a href="#">Announcements</a></li>
            <li><a href="#">Diplomatic & Consular List</a></li>
            <li><a href="#">Deputy Mission Chief List</a></li>
            <li><a href="#">Form</a></li>
            <li><a href="#">Documents</a></li>
        </ul>
    </div>

    <div class="main-content">
        <!-- Home Page Section -->
        <section id="home">
            <header class="section-header">
                <h1>Home Page</h1>
            </header>
            <div class="notification expire">
                <p>Your ID card is about to expire. Please renew it soon.</p>
            </div>
        
            <div class="container">
                <div class="card">
                    <h3>Add Request</h3>
                    <button>New Card</button>
                </div>
            </div>
                <div class="card">
                    <h3>ID Card Renewal</h3>
                    <button>Renew ID Card</button>
                </div>

                <div class="card">
                     <h3>Notifications</h3>
                     <button>View All</button>
                </div>
            </div>    
        </section>
    
    </div>
</body>
</html>
