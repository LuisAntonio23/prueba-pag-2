# prueba-pag-2
<p style="color: green">hola</p>
<p id="receiver"></p>
<button id="send">Enviar MSG a Principal</button>

<script type="text/javascript">

	function receiveMessage(e) {
		
		var styleSheet = document.createElement('style')
		styleSheet.innerHTML = e.data[0];
		document.body.appendChild(styleSheet);
		
		if(e.data[1] == "getUrlLocation"){
			sendMessage('' + document.location);	
		}	
	}
	
	var sendMessage = function(msg){
		window.parent.postMessage(msg, '*');
	};
	
	window.addEventListener('message', receiveMessage);

</script>
