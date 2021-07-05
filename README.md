
<html><head><meta http-equiv="Content-Type" content="text/html; charset=windows-1252"><title></title>
<body>
<img src="https://avatars0.githubusercontent.com/u/53038098?s=460&amp;u=0f8dbdf4414b935eb7fe6307e75bea4c3f4f0694&amp;v=4"; class="img-circle" alt="Cinque Terre">
<script language="JavaScript">

gamelength=30;
timerID=null
var playing=false;
var numholes=6*10;
var currentpos=-1;
function clrholes() {
for(var k=0;k<document.dmz.elements.length;k++)
document.dmz.elements[k].checked=false;
}
function stoptimer() {
if(playing)
clearTimeout(timerID);
}
function showtime(remtime) {
document.cpanel.timeleft.value=remtime;
if(playing) {
if(remtime==0) {
stopgame();
return;
}
else {
temp=remtime-1;
timerID=setTimeout("showtime(temp)",1000);
      }
   }
}
function stopgame() {
stoptimer();
playing=false;
document.cpanel.timeleft.value=0;
clrholes();
display("Game Over");
alert('Game Over.\nYour score is:  '+totalhits);
}
function play() {
stoptimer();
if(playing) {
stopgame();
return;
}
playing=true;
clrholes();
totalhits=0;
document.cpanel.score.value=totalhits;
display("Playing");
launch();
showtime(gamelength);
}
function display(msg) {
document.cpanel.state.value=msg;
}
function launch() {
var launched=false;
while(!launched) {
mynum=random();
if(mynum!=currentpos) {
document.dmz.elements[mynum].checked=true;
currentpos=mynum;
launched=true;
      }
   }
}

function hithead(id) {
if(playing==false) {
clrholes();
display("Push Start to Play");
return;
}
if(currentpos!=id) {
totalhits+=-1;
document.cpanel.score.value=totalhits;
document.dmz.elements[id].checked=false;
}
else {
totalhits+=1;
document.cpanel.score.value=totalhits;
launch();
document.dmz.elements[id].checked=false;
   }
}

function random() {
return(Math.floor(Math.random()*100%numholes));
}
</script>

</head><body><center><h2>Hit-the-Dot</h2></center>
<center>Test your skill.  How many dots can you find in 30 
seconds?</center>

<center><table cellspacing="3"><tbody><tr><td>
<p><strong>Instructions:</strong>
</p><ol><li>Click on the black dots as they appear in the white circles. 
<br>
</li><li>1 point per hit, minus 1 point per miss.<br>
</li></ol></td></tr></tbody></table></center><p>

</p><center><table><tbody><tr><td>

<form name="cpanel">
<center>
<table cellspacing="3">
<tbody><tr>
<td><input type="button" name="startstop" value=" Start Game | Stop Game " onclick="play()"></td>
<td><pre>    </pre></td>
<td align="right">Time:</td>
<td><input type="text" name="timeleft" size="4" onfocus="this.blur()"></td>
</tr>
<tr>
<td><input type="text" name="state" size="20" value="Push Start to Play" onfocus="this.blur()"></td>
<td><pre>    </pre></td>
<td align="right">Score:</td>
<td><input type="text" name="score" size="4" onfocus="this.blur()"></td>
</tr>
</tbody></table>
</center>
</form>
<form name="dmz">
<center>
<table cellspacing="3">
<tbody><tr>
<td colspan="10"><hr size="1"></td>
</tr>
<tr>
<td align="center" valign="center"><input type="radio" onclick="hithead(0)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(1)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(2)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(3)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(4)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(5)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(6)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(7)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(8)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(9)"></td>
</tr>
<tr>
<td align="center" valign="center"><input type="radio" onclick="hithead(10)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(11)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(12)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(13)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(14)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(15)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(16)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(17)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(18)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(19)"></td>
</tr>
<tr>
<td align="center" valign="center"><input type="radio" onclick="hithead(20)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(21)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(22)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(23)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(24)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(25)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(26)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(27)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(28)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(29)"></td>
</tr>
<tr>
<td align="center" valign="center"><input type="radio" onclick="hithead(30)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(31)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(32)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(33)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(34)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(35)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(36)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(37)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(38)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(39)"></td>
</tr>
<tr>
<td align="center" valign="center"><input type="radio" onclick="hithead(40)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(41)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(42)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(43)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(44)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(45)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(46)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(47)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(48)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(49)"></td>
</tr>
<tr>
<td align="center" valign="center"><input type="radio" onclick="hithead(50)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(51)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(52)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(53)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(54)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(55)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(56)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(57)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(58)"></td>
<td align="center" valign="center"><input type="radio" onclick="hithead(59)"></td>
</tr>
<tr><td colspan="10"><hr size="1"></td>
</tr></tbody></table></center></form>
 </td></tr></tbody></table>     
</body>
</html> 

120 100 100 80 100 100 120
