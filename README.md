# prueba-pag-2
<p style="color: green">hola</p>
<p id="receiver"></p>
<button id="send">Enviar MSG a Principal</button>
<a href=""><button id="next">siguiente pag</button></a>

<script type="text/javascript">
function bindEvent(element, eventName, eventHandler) {
       	if (element.addEventListener) {
               	element.addEventListener(eventName, eventHandler, false);
      	} else if (element.attachEvent) {
               	element.attachEvent('on' + eventName, eventHandler);
       	}
}
	
var sendMessage = function (msg) {
	window.parent.postMessage(msg, '*');
};

var messageButton = document.getElementById('send');


bindEvent(messageButton, 'click', function (e) {
	doc = document;
	var random = Math.random();
	sendMessage('segundo ' + random);
});
</script>
