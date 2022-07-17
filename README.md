# taskIOT-1-2
Setting up an ESP32 with Arduino IDE-Code to convert Speech to Text
## task1 Setting up an ESP32 with Arduino IDE

# First download Arduino IDE
```
1. file
2. preferences
3. paste the following link in Additinoal Boards Manager URLs:
https://dl.espressif.com/dl/package_esp32_index.json
```
### Now go to 
```
4. board "Aurduino Uno"
5. board manager
6. type esp32 and install the latest version
```
### After download 
```
7. board "Aurduino Uno"
8. ESP32 Aurduino
9. select ESP32 Dev Module
10. and the right com port 
```
### To check everything is working
```
11. go to example
12. go to esp32
13. go to ChipID
```
### Now connect the ESP32 to the right port
```
14. press upload
15. finally see the output
```
## task2 Code to convert Speech to Text
```
<!DOCTYPE html>
<html lang="en">

<head>
	<meta charset="UTF-8">
	<meta name="viewport" content=
		"width=device-width, initial-scale=1.0">

	<title>Speech to Text</title>
</head>

<body>
	<div class="words" contenteditable>
		<p id="p"></p>
	</div>

	<script>
		var speech = true;
		window.SpeechRecognition = window.SpeechRecognition
						|| window.webkitSpeechRecognition;

		const recognition = new SpeechRecognition();
		recognition.interimResults = true;
		const words = document.querySelector('.words');
		words.appendChild(p);

		recognition.addEventListener('result', e => {
			const transcript = Array.from(e.results)
				.map(result => result[0])
				.map(result => result.transcript)
				.join('')

			document.getElementById("p").innerHTML = transcript;
			console.log(transcript);
		});
		
		if (speech == true) {
			recognition.start();
			recognition.addEventListener('end', recognition.start);
		}
	</script>
</body>

</html>
```

