# myTempRepo
<!DOCTYPE HTML>
<html>
<head>
<meta http-equiv="content-type" content="text/html; charset=utf-8" />
<meta name="viewport" content="user-scalable=no, width=device-width, initial-scale=1.0, maximum-scale=1.0"/>
<meta name="apple-mobile-web-app-capable" content="yes" />
<meta name="apple-mobile-web-app-status-bar-style" content="black" />
<meta name="interface" content="desktop" />
<title>Slots</title>
<link href='http://fonts.googleapis.com/css?family=Slackey' rel='stylesheet' type='text/css'/>
<style>
html, body, div, span, applet, object, iframe,
h1, h2, h3, h4, h5, h6, p, blockquote, pre,
a, abbr, acronym, address, big, cite, code,
del, dfn, em, font, img, ins, kbd, q, s, samp,
small, strike, strong, sub, sup, tt, var,
dl, dt, dd, ol, ul, li,
fieldset, form, label, legend,
table, caption, tbody, tfoot, thead, tr, th, td {
margin: 0;
padding: 0;
border: 0;
outline: 0;
font-weight: inherit;
font-style: inherit;
font-size: 100%;
font-family: inherit;
vertical-align: baseline;
}
/* remember to define focus styles! */
:focus {
outline: 0;
}
body {
line-height: 1;
color: black;
background: white;
font-family:Lucida Grande,trebuchet ms,verdana,arial,helvetica,sans-serif;
}
ol, ul {
list-style: none;
}
/* tables still need 'cellspacing="0"' in the markup */
table {
border-collapse: separate;
border-spacing: 0;
}
caption, th, td {
text-align: left;
font-weight: normal;
}
blockquote:before, blockquote:after,
q:before, q:after {
content: "";
}
blockquote, q {
quotes: "" "";
}
html , body
{
height:100%;
-webkit-tap-highlight-color: rgba(0,0,0,0);
font-family: 'Slackey';
}
#viewport
{
background-color:#cdcdcd;
background-image:-moz-linear-gradient(#bbb,#eee,#bbb);
background-image:-webkit-linear-gradient(#bbb,#eee,#bbb);
overflow:hidden;
width: 100%;
height: 100%;
display:block;
}
#viewport.mobile
{
position:absolute;
top:0px;
left:0px;
}
#viewport.tablet
{
position:absolute;
top:0px;
left:0px;
}
#viewport.desktop
{
position:fixed;
top:0px;
left:0px;
right:0px;
bottom:0px;
}
#container
{
position:absolute;
width: 320px;
height: 340px;
left: 50%;
top: 50%;
margin-left: -160px;
margin-top: -160px;
}
#container h1
{
font-size: large;
text-align: center;
color: white;
}
#container #header
{
text-align: center;
}
#container #header h1
{
text-align: center;
font: 26px Slackey;
text-shadow:#000 0px 0px 1px , #000 0px 0px 1px;
}
#container #header h3
{
color: #555;
padding-bottom: 10px;
text-shadow:rgba(255,255,255,0.6) 0px 1px 0px;
}
#container #buttons
{
margin-top:3px;
}
#container #buttons #play
{
font-family: 'Slackey';
position:absolute;
bottom:10px;
left:30px;
right:30px;
text-align: center;
height: 40px;
line-height: 40px;
font-size: 24px;
border-radius:10px;
background-size:auto 62px;
}
#container #reels
{
display:block;
position:relative;
height: 180px;
overflow: hidden;
text-align: center;
background:#000;
border: 10px solid;
border-color: #777 #999 #666 #999;
border-radius:3px;
-moz-box-shadow:#fff 0px 1px 0px;
}
#container #reels canvas
{
width: 87px;
height: 300px;
position: relative;
background: white;
border: 2px solid gold;
}
#container #overlay
{
width: 100%;
height: 100%;
position: absolute;
top: 0px;
opacity: 0.3;
background-image: -moz-linear-gradient(#555,#fff,#fff,#555);
background-image: -webkit-gradient(linear, 0 25%, 0 100%, from(grey), color-stop(0.5, white), to(grey));
display: none;
}
#container #overlay #winline
{
width: 100%;
height: 5px;
background: red;
position: relative;
top: 50%;
}
#reels #results
{
display: none;
background: white;
border: 3px solid gold;
height: 120px;
width: 250px;
left: 20px;
top: 15px;
position: absolute;
font-size: x-large;
}
#results #score {
margin: 5px;
}
#results #score img {
vertical-align: middle;
}
.button
{
position:relative;
display:block;
text-align: center;
color: #fff;
box-shadow: inset rgba(255,255,255,0.15) 0px 1px 0px;
border: 1px solid rgba(0,0,0,0.15);
background-image: -moz-linear-gradient(rgba(255,255,255,0.15),rgba(0,0,0,0.15));
background-image:-webkit-gradient(linear, left top, left bottom, from(rgba(255,255,255,0.15)), to(rgba(0,0,0,0.15)));
background-position: 0px -1px;
text-shadow:#000 0px 0px 1px;
text-decoration: none;
}
.button.button-default
{
background-image:-moz-linear-gradient(#77e0fb,#3f93ac);
background-image:-webkit-gradient(linear, left top, left bottom, from(#77e0fb), to(#3f93ac));
}
.button.button-default:hover
{
background-image:-moz-linear-gradient(#ffd539,#af861e);
background-image:-webkit-gradient(linear, left top, left bottom, from(#ffd539), to(#af861e));
cursor:pointer;
}
.button.button-default:active
{
background-image:-moz-linear-gradient(#ffb133,#b3671a);
background-image:-webkit-gradient(linear, left top, left bottom, from(#ffb133), to(#b3671a));
}
</style>
<script type="text/javascript">
var IMAGE_HEIGHT = 64;
var IMAGE_TOP_MARGIN = 5;
var IMAGE_BOTTOM_MARGIN = 5;
var SLOT_SEPARATOR_HEIGHT = 2
var SLOT_HEIGHT = IMAGE_HEIGHT + IMAGE_TOP_MARGIN + IMAGE_BOTTOM_MARGIN + SLOT_SEPARATOR_HEIGHT; // how many pixels one slot image takes
var RUNTIME = 3000; // how long all slots spin before starting countdown
var SPINTIME = 1000; // how long each slot spins at minimum
var ITEM_COUNT = 6 // item count in slots
var SLOT_SPEED = 15; // how many pixels per second slots roll
var DRAW_OFFSET = 45 // how much draw offset in slot display from top
var BLURB_TBL = [
'No win!',
'Good!',
'Excellent!',
'JACKPOT!'
];
function shuffleArray( array ) {
for (i = array.length - 1; i > 0; i--) {
var j = parseInt(Math.random() * i)
var tmp = array[i];
array[i] = array[j]
array[j] = tmp;
}
}
// Images must be preloaded before they are used to draw into canvas
function preloadImages( images, callback ) {
function _preload( asset ) {
asset.img = new Image();
asset.img.src = 'http://www.cdn925.com/CampImg/474/slotmachine/' + asset.id+'.png';
asset.img.addEventListener("load", function() {
_check();
}, false);
asset.img.addEventListener("error", function(err) {
_check(err, asset.id);
}, false);
}
var loadc = 0;
function _check( err, id ) {
if ( err ) {
alert('Failed to load ' + id );
}
loadc++;
if ( images.length == loadc )
return callback()
}
images.forEach(function(asset) {
_preload( asset );
});
}
function copyArray( array ) {
var copy = [];
for( var i = 0 ; i < array.length; i++) {
copy.push( array[i] );
}
return copy;
}
function SlotGame() {
var game = new Game();
var items = [
{id: 'energy-64'},
{id: 'staff-64'},
{id: 'cash-64'},
{id: 'build-64'},
{id: 'goods-64'},
{id: 'gold-64'}
];
$('canvas').attr('height', IMAGE_HEIGHT * ITEM_COUNT * 2);
$('canvas').css('height', IMAGE_HEIGHT * ITEM_COUNT * 2);
game.items = items;
// load assets and predraw the reel canvases
preloadImages( items, function() {
// images are preloaded
// draws canvas strip
function _fill_canvas( canvas, items ) {
ctx = canvas.getContext('2d');
ctx.fillStyle = '#ddd';
for (var i = 0 ; i < ITEM_COUNT ; i++) {
var asset = items[i];
ctx.save();
ctx.shadowColor = "rgba(0,0,0,0.5)";
ctx.shadowOffsetX = 5;
ctx.shadowOffsetY = 5;
ctx.shadowBlur = 5;
ctx.drawImage(asset.img, 3, i * SLOT_HEIGHT + IMAGE_TOP_MARGIN);
ctx.drawImage(asset.img, 3, (i + ITEM_COUNT) * SLOT_HEIGHT + IMAGE_TOP_MARGIN);
ctx.restore();
ctx.fillRect(0, i * SLOT_HEIGHT, 70, SLOT_SEPARATOR_HEIGHT);
ctx.fillRect(0, (i + ITEM_COUNT) * SLOT_HEIGHT, 70, SLOT_SEPARATOR_HEIGHT);
}
}
// Draw the canvases with shuffled arrays
game.items1 = copyArray(items);
shuffleArray(game.items1);
_fill_canvas( game.c1[0], game.items1 );
game.items2 = copyArray(items);
shuffleArray(game.items2);
_fill_canvas( game.c2[0], game.items2 );
game.items3 = copyArray(items);
shuffleArray(game.items3);
_fill_canvas( game.c3[0], game.items3 );
game.resetOffset = (ITEM_COUNT + 3) * SLOT_HEIGHT;
game.loop();
});
$('#play').click(function(e) {
// start game on play button click
$('h1').text('Rolling!');
game.restart();
});
// Show reels for debugging
var toggleReels = 1;
$('#debug').click(function() {
toggleReels = 1 - toggleReels;
if ( toggleReels ) {
$('#reels').css('overflow', 'hidden' );
} else {
$('#reels').css('overflow', 'visible' );
}
});
}
function Game() {
// reel canvases
this.c1 = $('#canvas1');
this.c2 = $('#canvas2');
this.c3 = $('#canvas3');
// set random canvas offsets
this.offset1 = -parseInt(Math.random() * ITEM_COUNT ) * SLOT_HEIGHT;
this.offset2 = -parseInt(Math.random() * ITEM_COUNT ) * SLOT_HEIGHT;
this.offset3 = -parseInt(Math.random() * ITEM_COUNT ) * SLOT_HEIGHT;
this.speed1 = this.speed2 = this.speed3 = 0;
this.lastUpdate = new Date();
// Needed for CSS translates
this.vendor =
(/webkit/i).test(navigator.appVersion) ? '-webkit' :
(/firefox/i).test(navigator.userAgent) ? '-moz' :
(/msie/i).test(navigator.userAgent) ? 'ms' :
'opera' in window ? '-o' : '';
this.cssTransform = this.vendor + '-transform';
this.has3d = ('WebKitCSSMatrix' in window && 'm11' in new WebKitCSSMatrix())
this.trnOpen = 'translate' + (this.has3d ? '3d(' : '(');
this.trnClose = this.has3d ? ',0)' : ')';
this.scaleOpen = 'scale' + (this.has3d ? '3d(' : '(');
this.scaleClose = this.has3d ? ',0)' : ')';
// draw the slots to initial locations
this.draw( true );
}
// Restar the game and determine the stopping locations for reels
Game.prototype.restart = function() {
this.lastUpdate = new Date();
this.speed1 = this.speed2 = this.speed3 = SLOT_SPEED
// function locates id from items
function _find( items, id ) {
for ( var i=0; i < items.length; i++ ) {
if ( items[i].id == id ) return i;
}
}
this.result1 = _find( this.items1, 'gold-64' );
this.result2 = _find( this.items2, 'gold-64' );
this.result3 = _find( this.items3, 'gold-64' );
// get random results
/*
this.result1 = parseInt(Math.random() * this.items1.length)
this.result2 = parseInt(Math.random() * this.items2.length)
this.result3 = parseInt(Math.random() * this.items3.length)
*/
// Clear stop locations
this.stopped1 = false;
this.stopped2 = false;
this.stopped3 = false;
// randomize reel locations
this.offset1 = -parseInt(Math.random( ITEM_COUNT )) * SLOT_HEIGHT;
this.offset2 = -parseInt(Math.random( ITEM_COUNT )) * SLOT_HEIGHT;
this.offset3 = -parseInt(Math.random( ITEM_COUNT )) * SLOT_HEIGHT;
$('#results').hide();
this.state = 1;
}
window.requestAnimFrame = (function(){
return window.requestAnimationFrame ||
window.webkitRequestAnimationFrame ||
window.mozRequestAnimationFrame ||
window.oRequestAnimationFrame ||
window.msRequestAnimationFrame ||
function(/* function */ callback, /* DOMElement */ element){
window.setTimeout(callback, 1000 / 60);
};
})();
Game.prototype.loop = function() {
var that = this;
that.running = true;
(function gameLoop() {
that.update();
that.draw();
if (that.running) {
requestAnimFrame( gameLoop );
}
})();
}
Game.prototype.update = function() {
var now = new Date();
var that = this;
// Check slot status and if spun long enough stop it on result
function _check_slot( offset, result ) {
if ( now - that.lastUpdate > SPINTIME ) {
var c = parseInt(Math.abs( offset / SLOT_HEIGHT)) % ITEM_COUNT;
if ( c == result ) {
if ( result == 0 ) {
if ( Math.abs(offset + (ITEM_COUNT * SLOT_HEIGHT)) < (SLOT_SPEED * 1.5)) {
return true; // done
}
} else if ( Math.abs(offset + (result * SLOT_HEIGHT)) < (SLOT_SPEED * 1.5)) {
return true; // done
}
}
}
return false;
}
switch (this.state) {
case 1: // all slots spinning
if (now - this.lastUpdate > RUNTIME) {
this.state = 2;
this.lastUpdate = now;
}
break;
case 2: // slot 1
this.stopped1 = _check_slot( this.offset1, this.result1 );
if ( this.stopped1 ) {
this.speed1 = 0;
this.state++;
this.lastUpdate = now;
}
break;
case 3: // slot 1 stopped, slot 2
this.stopped2 = _check_slot( this.offset2, this.result2 );
if ( this.stopped2 ) {
this.speed2 = 0;
this.state++;
this.lastUpdate = now;
}
break;
case 4: // slot 2 stopped, slot 3
this.stopped3 = _check_slot( this.offset3, this.result3 );
if ( this.stopped3 ) {
this.speed3 = 0;
this.state++;
}
break;
case 5: // slots stopped
if ( now - this.lastUpdate > 3000 ) {
this.state = 6;
}
break;
case 6: // check results
var ec = 0;
$('#results').show();
if (that.items1[that.result1].id == 'gold-64') {
ec++;
}
if (that.items2[that.result2].id == 'gold-64') {
ec++;
}
if (that.items3[that.result3].id == 'gold-64') {
ec++;
}
$('#multiplier').text(ec);
$('#status').text(BLURB_TBL[ec]);
this.state = 7;
break;
case 7: // game ends
break;
default:
}
this.lastupdate = now;
}
Game.prototype.draw = function( force ) {
if (this.state >= 6 ) return;
// draw the spinning slots based on current state
for (var i=1; i <= 3; i++ ) {
var resultp = 'result'+i;
var stopped = 'stopped'+i;
var speedp = 'speed'+i;
var offsetp = 'offset'+i;
var cp = 'c'+i;
if (this[stopped] || this[speedp] || force) {
if (this[stopped]) {
this[speedp] = 0;
var c = this[resultp]; // get stop location
this[offsetp] = -(c * SLOT_HEIGHT);
if (this[offsetp] + DRAW_OFFSET > 0) {
// reset back to beginning
this[offsetp] = -this.resetOffset + SLOT_HEIGHT * 3;
}
} else {
this[offsetp] += this[speedp];
if (this[offsetp] + DRAW_OFFSET > 0) {
// reset back to beginning
this[offsetp] = -this.resetOffset + SLOT_HEIGHT * 3 - DRAW_OFFSET;
}
}
// translate canvas location
this[cp].css(this.cssTransform, this.trnOpen + '0px, '+(this[offsetp] + DRAW_OFFSET)+'px' + this.trnClose);
}
}
}
</script>
</head>
<body>
<div id="viewport">
<div id="container">
<div id="header">
<h1>Slots Machine</h1>
<h3>Play and Win</h3>
</div>
<div id="reels">
<canvas id="canvas1" width="70" height="300"></canvas>
<canvas id="canvas2" width="70" height="300"></canvas>
<canvas id="canvas3" width="70" height="300"></canvas>
<div id="overlay">
<div id="winline"></div>
</div>
<div id="results">
<div id="score">
<span id="multiplier">0</span> x <img src="http://www.cdn925.com/CampImg/474/slotmachine/gold-64.png"/>
</div>
<div id="status"></div>
</div>
</div>
<div id="buttons">
<div id="play" class="button button-default">Play</div>
</div>
</div>
<input id="debug" type="button" value="Toggle Reels"/>
</div>
<script src="http://ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js" ></script>
<script type="text/javascript">$(function() { SlotGame(); });</script>
</body>
</html>
