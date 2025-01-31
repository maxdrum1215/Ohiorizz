<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Public Domain Movies</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            background-color: #222;
            color: #fff;
        }
        .container {
            max-width: 800px;
            margin: auto;
            padding: 20px;
        }
        .movie {
            margin-bottom: 20px;
            padding: 10px;
            background: #333;
            border-radius: 10px;
        }
        input {
            width: 100%;
            padding: 10px;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Public Domain Movies</h1>
        <input type="text" id="search" placeholder="Search movies..." onkeyup="searchMovies()">
        <div id="movies"></div>
    </div>

    <script>
        const movies = [
            { title: "Night of the Living Dead (1968)", url: "https://www.youtube.com/embed/vZy6P72Uu3Y" },
            { title: "Nosferatu (1922)", url: "https://www.youtube.com/embed/FC6jFoYm3xs" },
            { title: "Metropolis (1927)", url: "https://www.youtube.com/embed/on2H8Qt5fgA" }
        ];

        function displayMovies(filteredMovies) {
            const movieContainer = document.getElementById("movies");
            movieContainer.innerHTML = "";
            filteredMovies.forEach(movie => {
                movieContainer.innerHTML += `
                    <div class="movie">
                        <h2>${movie.title}</h2>
                        <iframe width="100%" height="315" src="${movie.url}" frameborder="0" allowfullscreen></iframe>
                    </div>
                `;
            });
        }

        function searchMovies() {
            const query = document.getElementById("search").value.toLowerCase();
            const filteredMovies = movies.filter(movie => movie.title.toLowerCase().includes(query));
            displayMovies(filteredMovies);
