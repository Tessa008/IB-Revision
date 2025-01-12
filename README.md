<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>IB TOK Resource Hub</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            color: #333;
        }

        header {
            background-color: #4CAF50;
            color: white;
            padding: 1rem;
            text-align: center;
        }

        .container {
            margin: 20px;
            padding: 20px;
            background-color: white;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
        }

        h1, h2 {
            color: #4CAF50;
        }

        .category {
            margin: 10px 0;
            padding: 15px;
            border: 1px solid #ddd;
            border-radius: 5px;
            cursor: pointer;
            background-color: #f5f5f5;
        }

        .category:hover {
            background-color: #e0f7e0;
        }

        .resources {
            margin-top: 15px;
            display: none;
        }

        .resources a {
            display: block;
            margin: 8px 0;
            color: #4CAF50;
            text-decoration: none;
        }

        .resources a:hover {
            text-decoration: underline;
        }

        footer {
            text-align: center;
            padding: 10px;
            margin-top: 20px;
            background-color: #4CAF50;
            color: white;
        }

        #search-container {
            margin: 20px 0;
        }

        #search-input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
        }

        #search-results {
            margin-top: 20px;
        }
    </style>
</head>
<body>
    <header>
        <h1>IB TOK Resource Hub</h1>
        <p>Comprehensive Resources for Theory of Knowledge</p>
    </header>

    <div class="container">
        <div id="search-container">
            <input
                type="text"
                id="search-input"
                placeholder="Search for TOK resources..."
                onkeyup="filterResources()"
            />
        </div>

        <h2>Categories</h2>

        <div class="category" onclick="toggleResources('essays')">
            TOK Essays
        </div>
        <div id="essays" class="resources">
            <a href="https://www.ibtokessayexamples.com" target="_blank">Sample TOK Essays</a>
            <a href="https://tokessayguide.com" target="_blank">TOK Essay Writing Guide</a>
            <a href="https://drive.google.com/sample-essay-collection" target="_blank">Download Sample Essays</a>
        </div>

        <div class="category" onclick="toggleResources('exhibitions')">
            TOK Exhibitions
        </div>
        <div id="exhibitions" class="resources">
            <a href="https://www.tokexhibitionexamples.com" target="_blank">Exhibition Examples</a>
            <a href="https://www.tokexhibitioncommentary.com" target="_blank">Sample Exhibition Commentaries</a>
            <a href="https://drive.google.com/tok-exhibition-resources" target="_blank">Download Commentaries</a>
        </div>

        <div class="category" onclick="toggleResources('books')">
            TOK Books and Guides
        </div>
        <div id="books" class="resources">
            <a href="https://www.toktextbooks.com" target="_blank">TOK Textbooks</a>
            <a href="https://ibresources.org" target="_blank">Free TOK eBooks</a>
            <a href="https://drive.google.com/tok-reading-materials" target="_blank">Downloadable TOK Resources</a>
        </div>

        <div class="category" onclick="toggleResources('rubrics')">
            TOK Rubrics and Guides
        </div>
        <div id="rubrics" class="resources">
            <a href="https://www.ibo.org/programmes/diploma-programme/theory-of-knowledge/" target="_blank">Official TOK Rubrics</a>
            <a href="https://tokrubricsguide.com" target="_blank">TOK Assessment Rubrics</a>
        </div>
    </div>

    <div id="search-results" class="container" style="display:none;">
        <h2>Search Results</h2>
        <ul id="results-list"></ul>
    </div>

    <footer>
        <p>&copy; 2025 IB TOK Resource Hub | Made for IB Students</p>
    </footer>

    <script>
        // Toggle visibility of resources
        function toggleResources(categoryId) {
            const resources = document.getElementById(categoryId);
            if (resources.style.display === "none" || !resources.style.display) {
                resources.style.display = "block";
            } else {
                resources.style.display = "none";
            }
        }

        // Filter resources based on search input
        function filterResources() {
            const input = document.getElementById("search-input").value.toLowerCase();
            const allResources = document.querySelectorAll(".resources a");
            const resultsList = document.getElementById("results-list");
            const searchResults = document.getElementById("search-results");

            resultsList.innerHTML = "";
            let found = false;

            allResources.forEach((resource) => {
                const text = resource.textContent.toLowerCase();
                if (text.includes(input)) {
                    const li = document.createElement("li");
                    const link = document.createElement("a");
                    link.href = resource.href;
                    link.target = "_blank";
                    link.textContent = resource.textContent;
                    li.appendChild(link);
                    resultsList.appendChild(li);
                    found = true;
                }
            });

            searchResults.style.display = found ? "block" : "none";
        }
    </script>
</body>
</html>
