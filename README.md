<!DOCTYPE html>



<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Search Interface</title>
    <style>
        /* Basic Reset */
        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            display: flex;
            justify-content: center;
           align-items: center;
            height: 100vh;
            background-color: #f0f2f5;
            font-family: Arial, sans-serif;
        }

        .search-container {
            display: flex;
            align-items: center;
            border: 2px solid #ccc;
            border-radius: 8px;
            background-color: #fff;
            padding: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
            max-width: 600px;
            width: 100%;
        }

        .dropdown {
            position: relative;
            margin-right: 10px;
        }

        .dropdown-button {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 8px;
            background-color: #f8f9fa;
            border: 1px solid #ccc;
            border-radius: 4px;
            cursor: pointer;
            width: 180px;
            color: #333;
        }

        .dropdown-menu {
            position: absolute;
            top: 100%;
            left: 0;
            width: 100%;
            background-color: #fff;
            border: 1px solid #ccc;
            border-radius: 4px;
            margin-top: 5px;
            display: none;
            z-index: 10;
            max-height: 200px;
            overflow-y: auto;
        }

        .dropdown-menu .dropdown-item {
            padding: 8px 10px;
            cursor: pointer;
            color: #333;
        }

        .dropdown-menu .dropdown-item:hover {
            background-color: #e9ecef;
        }

        .search-input {
            flex: 1;
            padding: 8px;
            border: 1px solid #ccc;
            border-radius: 4px;
            outline: none;
            margin-right: 10px;
        }

        .search-button {
            padding: 8px 16px;
            background-color: #007bff;
            border: none;
            color: #fff;
            border-radius: 4px;
            cursor: pointer;
            transition: background-color 0.3s ease;
        }

        .search-button:hover {
            background-color: #0056b3;
        }
    </style>
</head>
<body>

    <div class="search-container">
        <div class="dropdown">
            <div class="dropdown-button" onclick="toggleDropdown()">Everything</div>
            <div class="dropdown-menu" id="dropdownMenu">
                <div class="dropdown-item" onclick="selectCategory('Everything')">Everything</div>
                <div class="dropdown-item" onclick="selectCategory('Software Development')">Software Development</div>
                <div class="dropdown-item" onclick="selectCategory('Web Development')">Web Development</div>
                <div class="dropdown-item" onclick="selectCategory('Data Analyst')">Data Analyst</div>
                <div class="dropdown-item" onclick="selectCategory('IT Consultant')">IT Consultant</div>
                <div class="dropdown-item" onclick="selectCategory('Network Administrator')">Network Administrator</div>
            </div>
        </div>
        <input type="text" class="search-input" placeholder="Type your search query here...">
        <button class="search-button">Search</button>
    </div>

    <script>
        // Toggle dropdown visibility
        function toggleDropdown() {
            document.getElementById("dropdownMenu").style.display = 
                document.getElementById("dropdownMenu").style.display === "block" ? "none" : "block";
        }

        // Select category and close dropdown
        function selectCategory(category) {
            document.querySelector(".dropdown-button").textContent = category;
            document.getElementById("dropdownMenu").style.display = "none";
        }

        // Close dropdown if clicked outside
        window.onclick = function(event) {
            if (!event.target.matches('.dropdown-button')) {
                document.getElementById("dropdownMenu").style.display = "none";
            }
        };
    </script>
</body>
</html>
