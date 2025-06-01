<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Movie Card Generator</title>
    <style>
        body {
            font-family: sans-serif;
            padding: 20px;
            background: #f4f4f4;
        }
        .card {
            width: 300px;
            background: white;
            border-radius: 10px;
            box-shadow: 0 0 10px #ccc;
            overflow: hidden;
            margin: 20px auto;
        }
        .card img {
            width: 100%;
        }
        .card-content {
            padding: 15px;
        }
        .card-title {
            font-weight: bold;
            font-size: 18px;
        }
        .download-btn {
            margin-top: 10px;
            background: #007BFF;
            color: white;
            border: none;
            padding: 10px;
            border-radius: 5px;
            cursor: pointer;
        }
        textarea {
            width: 100%;
            height: 200px;
            margin-top: 20px;
        }
    </style>
</head>
<body>

<h2>🎬 Movie Card Generator</h2>

<input type="text" id="searchInput" placeholder="Enter IMDb ID or Movie Name" style="width: 300px; padding: 10px;">
<button onclick="generateCard()">Generate Card</button>

<div id="result"></div>

<textarea id="htmlOutput" placeholder="HTML output will appear here..."></textarea>

<script>
    const apiKey = '46316a75'; // Replace with your OMDb API key if needed

    async function generateCard() {
        const input = document.getElementById('searchInput').value.trim();
        if (!input) return alert('Enter IMDb ID or Movie Name');

        let title, image;

        // Fetch from OMDb API
        let omdbUrl = input.startsWith('tt')
            ? `https://www.omdbapi.com/?apikey=${apiKey}&i=${input}`
            : `https://www.omdbapi.com/?apikey=${apiKey}&t=${encodeURIComponent(input)}`;

        const omdbRes = await fetch(omdbUrl);
        const omdbData = await omdbRes.json();

        if (omdbData.Response === "False") {
            alert("Movie not found in OMDb");
            return;
        }

        title = omdbData.Title;
        image = omdbData.Poster;

        // Fetch from stream scraper
        const searchUrl = `https://stream-scraper.onrender.com/search/${encodeURIComponent(title)}`;
        const streamRes = await fetch(searchUrl);
        const streamData = await streamRes.json();

        if (!streamData.success || !streamData.movies.length) {
            alert("No streaming links found.");
            return;
        }

        let hdLink = null;
        const episodes = streamData.movies[0].episodes || [];
        episodes.forEach(ep => {
            ep.watchLinks.forEach(link => {
                if (link.type === "HDStream") {
                    hdLink = link.url;
                }
            });
        });

        if (!hdLink) {
            alert("HDStream link not found.");
            return;
        }

        const cardHTML = `
<div class="card">
    <img src="${image}" alt="${title}">
    <div class="card-content">
        <div class="card-title" data-title="${title}">${title}</div>
        <div class="card-description">Download and Watch Online</div>
        <a href="player.html?video=${hdLink}" width="90%" height="600" allow="autoplay" target="_blank">
            <button class="download-btn">Watch online</button>
        </a>
    </div>
</div>
        `.trim();

        document.getElementById('result').innerHTML = cardHTML;
        document.getElementById('htmlOutput').value = cardHTML;
    }
</script>

</body>
</html>
