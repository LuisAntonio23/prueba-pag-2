# prueba-pag-2
<p style="color: green">hola</p>
<p id="receiver"></p>
<button id="send">Enviar MSG a Principal</button>

<script type="text/javascript">
function reciveMessage(e){
	if(e.data == 'getUrlLocation'){
		sendMessage('' + document.location);
	}
}

var sendMessage = function (msg) {
	window.parent.postMessage(msg, '*');
};

window.addEventListener('message',reciveMessage);
</script>
