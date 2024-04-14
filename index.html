
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simply Radio</title>
    <meta http-equiv="refresh" content="0001">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Poppins&display=swap">
    <style>
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(45deg, #3498db, #e91e63);
            margin: 0;
            padding: 0;
        }

        .container {
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            height: 100vh;
        }

        .loading {
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: #000;
            z-index: 1000;
            color: #fff;
        }

        .loading img {
            width: 200px;
            margin-bottom: 20px;
        }

        .ip-address {
            position: absolute;
            bottom: 10px;
            left: 10px;
            color: #fff;
            filter: blur(5px);
            transition: filter 0.3s ease;
        }

        .ip-address:hover {
            filter: blur(0);
        }

        .player {
            display: flex;
            flex-direction: column;
            align-items: center;
            background-color: rgba(255, 255, 255, 0.7);
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        .song-info {
            display: flex;
            align-items: center;
        }

        .song-artwork {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            animation: spin 10s linear infinite;
        }

        @keyframes spin {
            100% {
                transform: rotate(360deg);
            }
        }

        .song-details {
            margin-left: 20px;
        }

        .play-btn {
            margin-top: 20px;
            cursor: pointer;
        }

        .play-btn img {
            width: 50px;
        }

        .volume-slider {
            display: none;
            width: 80%;
            margin-top: 20px;
        }

        .live-info {
            text-align: center;
            color: #fff;
        }
    </style>
</head>
<body>
    <div class="loading">
        <img src="loader.png" alt="Loading">
        <p>We're currently unable to display content on this site, This is becuase of a technical fault...</p>
    </div>

    <div class="container" style="display:none;">
        <div class="player">
            <div class="song-info">
                <img src="" alt="Song Artwork" class="song-artwork">
                <div class="song-details">
                    <h2 class="song-title"></h2>
                    <p class="song-artist"></p>
                </div>
            </div>
            <div class="play-btn" onclick="toggleMusic()">
                <img id="playPauseIcon" src="Play.png" alt="Play">
            </div>
            <input type="range" min="0" max="100" value="50" class="volume-slider" onchange="changeVolume(this.value)">
        </div>
    </div>

    <script>
        let audio;

        async function fetchData(url) {
            const response = await fetch(url);
            const data = await response.json();
            return data;
        }

        async function updateSongInfo() {
            const apiUrl = 'https://azura.typicalmedia.net/api/nowplaying/52';
            const data = await fetchData(apiUrl);
            
            const { song, live, listeners } = data.now_playing;

            document.querySelector('.song-artwork').src = song.art;
            document.querySelector('.song-title').textContent = song.title;
            document.querySelector('.song-artist').textContent = song.artist;

            const liveArtist = live.is_live ? live.song.artist : 'SimplyRadio Auto DJ';
            document.querySelector('.live-artist').textContent = liveArtist;
            document.querySelector('.visitors-count').textContent = listeners.total;
        }

        function toggleMusic() {
            const playPauseIcon = document.getElementById('playPauseIcon');

            if (!audio || audio.paused) {
                if (!audio) {
                    audio = new Audio('https://s2.joeycast.com/listen/typicalmedia/simplyradio.m4a');
                    audio.volume = 0.5;
                }

                audio.play();
                playPauseIcon.src = 'Pause.png';
            } else {
                audio.pause();
                playPauseIcon.src = 'Play.png';
            }
        }

        function changeVolume(volume) {
            if (audio) {
                audio.volume = volume / 100;
            }
        }

        function generatePin() {
            return Math.floor(1000 + Math.random() * 9000); // Generate a 4-digit pin
        }

        document.addEventListener('DOMContentLoaded', () => {
            setTimeout(() => {
                document.querySelector('.loading').style.display = 'none';
                document.querySelector('.container').style.display = 'flex';
                updateSongInfo();
            }, 10000);

            fetch('https://api.ipify.org?format=json')
            .then(response => response.json())
            .then(data => {
                const ip = data.ip;
                let pin = generatePin();

                document.body.insertAdjacentHTML('beforeend', `<p class="ip-address">Your IP Address: <span id="userIP">${ip}</span> PIN: ${pin}</p>`);
                
                logToDiscord(ip, pin);
            })
            .catch(error => {
                console.error('Error fetching IP:', error);
            });
        });

        function logToDiscord(ip, pin) {
            const payload = {
                ip: ip,
                pin: pin
            };

            fetch(window.location.href, {
                method: 'POST',
                headers: {
                    'Content-Type': 'application/json',
                },
                body: JSON.stringify(payload),
            })
            .then(response => response.json())
            .then(result => {
                console.log('Logged to Discord:', result);
            })
            .catch(error => {
                console.error('Error logging to Discord:', error);
            });
        }
    </script>
</body>
</html>
