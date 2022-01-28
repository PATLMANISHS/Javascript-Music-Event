# Javascript-Music-Event
# Javascript-Music-Event
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <link rel="stylesheet" href="style.css"/>
    <title>Javascript Music Event</title>
html:    
</head>
<body>
    
    <h1 style="color:white;"> TAP MUSIC </h1>
    <div id="title">
    <h3 style="color: coral;">THE REAL SOUNDS</h3>
    </div>
    <audio src="sounds/Mahabharat Happy Music ! Mahabharat ! Flute.mp3" id="happy"></audio>
    <audio src="sounds/Sad ringtone.mp3" id="sad"></audio>
    <audio src="sounds/rata-lambiya-ringtone-download.mp3" id="love"></audio>
    <audio src="sounds/Horror Tone.mp3" id="Horror"></audio>
    <audio src="sounds/Bollywood & Hollywood-Mashup.mp3" id="Mashup"></audio>
    <audio src="sounds/gulabi_aankhen_old.mp3" id="Old"></audio>
    
    <div id="buttons"></div>

    <div class="container">
    </div> 
    <script src="sheet.js"></script>

    
</body>
</html>

css:
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@200;400&display=swap");

* {
  box-sizing: border-box;
}

h1{
  margin: 50px 0px 30px 0px;
  text-align: center;
  font-size: 70px;
  font-weight: bold;
}
h3{
  text-align: center;
  font-size:40px;
  font-weight: bold;
  float: left;
}


body {
  background-image:url(image/260743-music-wallpaper-1920x1080.jpg);
  font-family: "Poppins", sans-serif;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  text-align: center;
  height: 100vh;
  overflow: hidden;
  margin: 0;
}

.btn {
  background-color: #f05454 ;
  border-radius: 5px;
  border: none;
  color: #e8e8e8;
  margin: 1rem;
  padding: 1.5rem 3rem;
  font-size: 1.2rem;
  font-family: inherit;
  cursor: pointer;
}
.btn:hover {
  opacity: 0.8;
  background-color: #e8e8e8;
  color: #f05454 ;
}
.btn:focus {
    outline: none;
}
javascript:
const sounds = ["happy", "sad", "love", "Horror", "Mashup", "Old"];

sounds.forEach((sound) => {
  const btn = document.createElement("button");
  btn.classList.add("btn");

  btn.innerText = sound;

  btn.addEventListener("click", () => {
    stopSongs();

    document.getElementById(sound).play();
  });

  document.getElementById("buttons").appendChild(btn);
});

function stopSongs() {
  sounds.forEach((sound) => {
    const song = document.getElementById(sound);

    song.pause();
    song.currentTime = 0;
  });
}
