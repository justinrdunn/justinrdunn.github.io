---
layout: page
title: About
permalink: /guitar/
---

<style type="text/css">
ul.menu {
	display: inline-block;
	padding: 0;
    margin: auto;
	width: 100%;
}

.menu li {
	display: inline-block;
}

.menu a{
	display: inline-block;
	padding: 10px;
	margin: 5px;
	text-align: center;
	height: 50px;
	background-color: #A6B1FF;
	font-size: 1.2em;
	color: white;
	border-radius: 10px;
}
.menu a:hover {
	background-color: #8090FF;
}

.activity {
    display: inline-block;
    text-align: center;
    margin: auto;
    width: 100%;
    padding: 60px 0;
}

.chord {
    padding: 70px;
    background-color: rgba(1,1,1,0.3);
    display: inline-block;
    font-size: 1.4em;
    font-family: Century Gothic;
}

.button {
    background-color: #FF9999;
    width: 100px;
    text-align: center;
    margin: auto;
    padding: 10px;
    border-radius: 22px;
    margin-top: 5px;
    box-shadow: 0px 0px 5px rgba(0, 0, 0, 0.14);
}

.button:hover {
	background-color: #F96565;
}
</style>

<ul class="menu">
	<li><a class="MaC">Major Chords</a></li>
	<li><a class="MiC">Minor Chords</a></li>
	<li><a class="MaS">Major Scales</a></li>
	<li><a class="strum">Strumming</a></li>
	<li><a class="rand">Random</a></li>
</ul>

<div class="activity">
</div>

<script   src="https://code.jquery.com/jquery-2.2.3.min.js"   integrity="sha256-a23g1Nt4dtEYOj7bR+vTu7+T8VP13humZFBJNIYoEJo="   crossorigin="anonymous"></script>
<script type="text/javascript">
	$('.menu a').click(function() {
		console.log(this)
		if($(this).hasClass('MaC')){
			$(".activity").html("\
                     <div class='MaCactivity'>\
                     	<div class='chord'>\
                     	</div>\
                     	<div class='button' onclick='newChord(\"Ma\")'>\
                     		New Chord\
                     	</div>\
                     </div>\
				");
			newChord("Ma")
		}
		else if ($(this).hasClass('MiC')){
			$(".activity").html("\
                     <div class='MiCactivity'>\
                     	<div class='chord'>\
                     	</div>\
                     	<div class='button' onclick='newChord(\"Mi\")'>\
                     		New Chord\
                     	</div>\
                     </div>\
				");
			newChord("Mi")
		}
		else if ($(this).hasClass('MaS')){
			$(".activity").html("\
                     <div class='MaSactivity'>\
                     	<div class='chord'>\
                     	</div>\
                     	<div class='button' onclick=\"newChord('Ma')\">\
                     		New Scale\
                     	</div>\
                     </div>\
				");
			newChord("Ma")
		}
		else if ($(this).hasClass('strum')){
			$(".activity").html("\
                     <div class='MiCactivity'>\
                     	<div class='chord'>\
                     	</div>\
                     	<div class='button' onclick=\"newChord('strum')\">\
                     		New Pattern\
                     	</div>\
                     </div>\
				");
			newChord("strum")
		}
		else if ($(this).hasClass('rand')){
			$(".activity").html("\
                     <div class='randactivity'>\
                     	<div class='chord'>\
                     	</div>\
                     	<div class='button' onclick=\"newChord('rand')\">\
                     		New Random\
                     	</div>\
                     </div>\
				");
			newChord("rand")
		}

	});

	function newChord(a) {
		notes = ["A", "A#", "Bb", "B", "C", "C#", "Db", "D", "D#", "Eb", "E", "F", "F#", "Gb", "G", "G#", "Ab"];
		scales = ["Major", "Minor"];
		strums = ["D","U","o"];
		rands = ["Ma", "Mi", "strum"];
		randNote = notes[Math.floor(Math.random() * 16)];
		if (a=="Ma"){
			$('.chord').html(randNote + " " + scales[0]);
		}
		else if (a=="Mi"){
			$('.chord').html(randNote + " " + scales[1]);
		}
		else if (a=="strum"){
			bars = "";
			for (var i = 0; i < 4; i++) {
				for (var j = 0; j < 4; j++) {
					if (j%2==0){
						bars = bars + strums[Math.round(Math.random()) ? 0 : 2];
					} else {
						bars = bars + strums[Math.round(Math.random()) ? 1 : 2];
					}
				}
				if(i != 3) {bars = bars + "|";}
			}
			$('.chord').html("[" + bars + "]");
		}
		else {
			newChord(rands[Math.floor(Math.random() * 3)])
		}
	}
</script>