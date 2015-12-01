---
title: Test yourself
slug: test
lead:
icon: pencil
---
<script type="text/javascript">
CorrectAnswers = new Array();
CorrectAnswers[0]=4;
CorrectAnswers[1]=1;
CorrectAnswers[2]=1;
CorrectAnswers[3]=3;
CorrectAnswers[4]=1;
CorrectAnswers[5]=3;
CorrectAnswers[6]=2;
CorrectAnswers[7]=1;
CorrectAnswers[8]=2;
CorrectAnswers[9]=1;
CorrectAnswers[10]=3;
CorrectAnswers[11]=2;
CorrectAnswers[12]=3;
CorrectAnswers[13]=2;
CorrectAnswers[14]=3;
macrightchar='Yes';
macwrongchar='No';
winrightchar='Yes';
winwrongchar='No';
var platform = 'win'
if (navigator.appVersion.indexOf('Mac') != -1) {platform = 'mac'}
if (platform == 'mac') {
rightchar = unescape(macrightchar)
wrongchar = unescape(macwrongchar)
}
else {
rightchar = unescape(winrightchar)
wrongchar = unescape(winwrongchar)
}

function checkAnswer(){
var i = 0;
var TotalCorrect = 0;
var x = 0;
var Score = 0;
for (i=0; i<CorrectAnswers.length; i++){
if (document.Quizform.elements[i*2].selectedIndex == CorrectAnswers[i]){
	document.Quizform.elements[(i*2)+1].value = rightchar;
	TotalCorrect++;
}
else{
	document.Quizform.elements[(i*2)+1].value = wrongchar;
}
}
Score = Math.floor((TotalCorrect*100)/CorrectAnswers.length);
document.checkForm.Scorebox.value = Score + '%';
}
</script>

<center>
<form name="Quizform">
<center>
  <table border=0 cellpadding=5>

<tr>
<td>
	1) On October 4, 1957, what satellite was launched,
	becoming the first satellite to officially orbit the Earth?
</td>
<td><b>
	<select name="0"><option>Choose from here:
		<option>Vanguard 1<option>Explorer 1<option>Oscar 10<option>Sputnik 1
	</select>
</b></td>
<td>
	<input type="text" name="1" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
	2) Which type of modulation is used in satellite communication?
</td>
<td><b>
<select name="2"><option>Choose from here:
	 <option>AM <option>FM <option>FSK <option>PSK
</select>
</b></td>
<td>
<input type="text" name="3" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
	3) What non-profit organization is made up of worldwide ham radio operators
	that use their own membership-supported satellites?
</td>
<td><b>
	<select name="4"> <option>Choose from here:
<option>AMSAT<option>GLOBALSAT<option>HAMSAT<option>FUTURESAT
</select>
</b></td>
<td> <input type="text" name="5" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
4) The signal from a satellite is normally aimed at a specific area called the
</td>
<td><b>
<select name="6"> <option>Choose from here:
<option>Path <option>Effect <option>Footprint<option>None of the above
</select>
</b></td>
<td>
<input type="text" name="7" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
5) There is (are) _____ orbit(s) for a GEO satellite.
</td>
<td><b>
<select name="8"> <option>Choose from here:
<option>One <option>Two <option>Many <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="9" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
6) MEO satellites are located at altitudes between km.
</td>
<td><b>
<select name="10"> <option>Choose from here:
<option>3000 and 5000 <option>5000 and 10,000 <option>5000 and 15,000 <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="11" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
7) LEO satellites are normally below an altitude of ________ km.
</td>
<td><b>
<select name="12"> <option>Choose from here:
<option>1000<option>2000 <option>3000 <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="13" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
8) ______ is based on a principle called trilateration.
</td>
<td><b>
<select name="14"> <option>Choose from here:
<option>GPS <option>Teledesic <option>Iridium <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="15" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
9) Low-Earth-orbit (LEO) satellites have _____ orbits.
</td>
<td><b>
<select name="16"> <option>Choose from here:
<option>Equatorial <option>Polar <option>Inclined <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="17" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
10) ________ satellites provide time and location information for vehicles and ships.
</td>
<td><b>
<select name="18"> <option>Choose from here:
<option>GPS <option>Iridium <option>Teledesic <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="19" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
11) Iridium satellites are ________satellites.
</td>
<td><b>
<select name="20"> <option>Choose from here:
<option>GEO <option>MEO <option>LEO <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="21" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
12) ________ satellites can provide direct universal voice and data communications for handheld terminals.
</td>
<td><b>
<select name="22"> <option>Choose from here:
<option>GPS <option>Iridium <option>Teledesic <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="23" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
13) ________ satellites will provide universal broadband Internet access.
</td>
<td><b>
<select name="24"> <option>Choose from here:
<option>GPS <option>Iridium <option>Teledesic <option>None of the above
</select>
</b></td>
<td>
<input type="text" name="25" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
14) ____ system is positioned below the lower Van Allen belt
</td>
<td><b>
<select name="26"> <option>Choose from here:
<option>MEO<option>LEO<option>GEO<option>HEO
</select>
</b></td>
<td>
<input type="text" name="27" size=3 maxlength=3>
</td>
</tr>

<tr>
<td>
15) The big LEOs operate between
</td>
<td><b>
<select name="28"> <option>Choose from here:
<option>1 to 2 GHz<option>1 to 5 GHz<option>1 to 3 GHz<option>1 to 10 GHz
</select>
</b></td>
<td>
<input type="text" name="29" size=3 maxlength=3>
</td>
</tr>

</table></center></form>

<P><form name="checkForm"> <center> Your score is: <input type=text name="Scorebox" size=4 maxlength=4><P>
<br><input type="button" value="Check" onClick="checkAnswer()"> </center></form><P>

<h2 style="text-align:left;">
Drag me to the correct place!
</h2>

<style>
#gameboard {
	position: relative;
	width: 750px;
	height: 350px;
	z-index: 1;
	border: solid 0.5px gray;}

#draggable1 {
	position: absolute;
	width: 150px;
	height: 150px;
	color: black;
	z-index: 3;
	left: 0px;
	margin-top: 0px;}

#droppable1 {
	position: absolute;
	width: 150px;
	height: 150px;
	margin-left: 0px;
	margin-top: 200px;
	z-index: 2;
	color: white;
	font-weight: bold;
	background-color: gray;}

#draggable2 {
	position: absolute;
	width: 150px;
	height: 150px;
	color: black;
	z-index: 3;
	left: 200px;
	top: 0px;}

#droppable2 {
	position: absolute;
	width: 150px;
	height: 150px;
	left: 200px;
	top: 200px;
	z-index: 2;
	color: white;
	font-weight: bold;
	background-color: gray;}

#draggable3 {
	position: absolute;
	width: 150px;
	height: 150px;
	color: black;
	z-index: 3;
	left: 400px;
	top: 0px;}

#droppable3 {
	position: absolute;
	width: 150px;
	height: 150px;
	left: 400px;
	top: 200px;
	z-index: 2;
	color: white;
	font-weight: bold;
	background-color: gray;}

#draggable4 {
	position: absolute;
	width: 150px;
	height: 150px;
	color: black;
	z-index: 3;
	left: 600px;
	top: 0px;}

#droppable4 {
	position: absolute;
	width: 150px;
	height: 150px;
	left: 600px;
	top: 200px;
	z-index: 2;
	color: white;
	font-weight: bold;
	background-color: gray;}

</style>
<script>
var counter = 0;
function verify()
{
if(counter > 3){
		alert('Well done!');
}
}
$(function() {
    $( "#draggable1" ).draggable();
    $( "#droppable3" ).droppable({
        drop: function( event, ui ) {
	if ($(ui.draggable).attr("id") == 'draggable1'){
    $( this )
    .find( "p" )
        .html( "Dropped!" );
        var med = $("#draggable1");
        var posleft = med.position().left;
        var postop = med.position().top;
        var x = 400 - posleft;
        var y = 200 - postop;
        counter++;
        $("#result").html(counter);
        $("#draggable1").css("margin-left", x);
        $("#draggable1").css("margin-top", y);
        $("#draggable1").draggable({ disabled: true });
        verify();
}
else{
}
      }
    });
});

$(function() {
   $( "#draggable2" ).draggable();
$( "#droppable1" ).droppable({
drop: function( event, ui ) {
if ($(ui.draggable).attr("id") == 'draggable2'){
    $( this )
    .find( "p" )
    .html( "Dropped!" );
    var med = $("#draggable2");
    var posleft = med.position().left;
    var postop = med.position().top;
    var x = 0 - posleft;
    var y = 200 - postop;
    counter++;
    $("#result").html(counter);
    $("#draggable2").css("margin-left", x);
    $("#draggable2").css("margin-top", y);
		$("#draggable2").draggable({ disabled: true });
    verify();
}
else{
}
}
});
});

$(function() {
   $( "#draggable3" ).draggable();
$( "#droppable4" ).droppable({
drop: function( event, ui ) {
if ($(ui.draggable).attr("id") == 'draggable3'){
    $( this )
    .find( "p" )
    .html( "Dropped!" );
    var med = $("#draggable3");
    var posleft = med.position().left;
    var postop = med.position().top;
    var x = 600 - posleft;
    var y = 200 - postop;
    counter++;
    $("#result").html(counter);
    $("#draggable3").css("margin-left", x);
    $("#draggable3").css("margin-top", y);
		$("#draggable3").draggable({ disabled: true });
    verify();
}
else{
}
}
});
});

$(function() {
   $( "#draggable4" ).draggable();
$( "#droppable2" ).droppable({
drop: function( event, ui ) {
if ($(ui.draggable).attr("id") == 'draggable4'){
    $( this )
    .find( "p" )
    .html( "Dropped!" );
    var med = $("#draggable4");
    var posleft = med.position().left;
    var postop = med.position().top;
    var x = 200 - posleft;
    var y = 200 - postop;
    counter++;
    $("#result").html(counter);
    $("#draggable4").css("margin-left", x);
    $("#draggable4").css("margin-top", y);
		$("#draggable4").draggable({ disabled: true });
    verify();
}
else{
}
}
});
});
</script>



<div id="result">...</div>
<div id="gameboard">
<div id="draggable1"><br><br>$\displaystyle\sqrt{\frac{k}{R_E+h}}$</div>
<div id="droppable1"><p><br><br>Angular speed</p></div>
<div id="draggable2"><br><br>$\displaystyle\sqrt{\frac{k}{(R_E+h)^3}}$</div>
<div id="droppable2"><p><br><br>Minimum number of satellites</p></div>
<div id="draggable3"><br><br>$\displaystyle 2\pi\sqrt{\frac{(R_E+h)^3}{k}}$</div>
<div id="droppable3"><p><br><br>Linear speed</p></div>
<div id="draggable4"><br><br>$\displaystyle\frac{2}{1-\cos\gamma}$</div>
<div id="droppable4"><p><br><br>Orbital period</p></div>
</div>
