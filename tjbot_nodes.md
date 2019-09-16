# TJBot & Node-RED 

Les exemples suivants incluent des fichiers JSON pouvant être importés via l'élément de menu du presse-papiers dans Node-RED. 
Quelques exemples vous aideront à configurer les services dont vous avez besoin

## Assistant

Utiliser le service Watson Assistant pour traiter le texte en langage naturel dans les intentions et les entités.

![](/images/converse.png)

```
[{"id":"f2699e6b.ec1eb","type":"inject","z":"68e8b9a0.f2e068","name":"","topic":"","payload":"Wave your arm","payloadType":"str","repeat":"","crontab":"","once":false,"x":200,"y":840,"wires":[["c06673e.cc0c21"]]},{"id":"c06673e.cc0c21","type":"tjbot-converse","z":"68e8b9a0.f2e068","botId":"5c94911d.6e7cd","name":"","x":380,"y":840,"wires":[["51f5fff0.0db8c8"]]},{"id":"51f5fff0.0db8c8","type":"debug","z":"68e8b9a0.f2e068","name":"","active":true,"console":"false","complete":"response","x":560,"y":840,"wires":[]},{"id":"d8f23205.a5c5d","type":"comment","z":"68e8b9a0.f2e068","name":"TJBot Converses","info":"","x":180,"y":800,"wires":[]},{"id":"5c94911d.6e7cd","type":"tjbot-config","z":"","botGender":"male","name":"TJBot","listen":"en-US","speak":"en-US"}]
```

## Ecoute

Transcrire le son capturé du microphone à l’aide de Watson Speech to Text.

![](/images/listen.png)

```
[{"id":"fa9227ce.7e89","type":"tjbot-listen","z":"68e8b9a0.f2e068","botId":"5c94911d.6e7cd","name":"","x":490,"y":180,"wires":[["63ceb9d6.5b778"]]},{"id":"c6ce89f8.3ca3f","type":"inject","z":"68e8b9a0.f2e068","name":"Start","topic":"","payload":"start","payloadType":"str","repeat":"","crontab":"","once":false,"x":150,"y":160,"wires":[["383b8b79.e97bcc"]]},{"id":"39e1a756.e0d498","type":"inject","z":"68e8b9a0.f2e068","name":"Stop","topic":"","payload":"stop","payloadType":"str","repeat":"","crontab":"","once":false,"x":150,"y":200,"wires":[["383b8b79.e97bcc"]]},{"id":"383b8b79.e97bcc","type":"change","z":"68e8b9a0.f2e068","name":"","rules":[{"t":"set","p":"mode","pt":"msg","to":"payload","tot":"msg"}],"action":"","property":"","from":"","to":"","reg":false,"x":320,"y":180,"wires":[["fa9227ce.7e89"]]},{"id":"63ceb9d6.5b778","type":"debug","z":"68e8b9a0.f2e068","name":"","active":true,"console":"false","complete":"payload","x":650,"y":180,"wires":[]},{"id":"f1b265ff.90ce5","type":"comment","z":"68e8b9a0.f2e068","name":"TJBot Listens","info":"","x":150,"y":120,"wires":[]},{"id":"5c94911d.6e7cd","type":"tjbot-config","z":"","botGender":"male","name":"TJBot","listen":"en-US","speak":"en-US"}]
```

## Voir

Prendre une photo à l'aide de l'appareil photo Raspberry Pi et analyser à l'aide de Watson Visual Recognition.

![](/images/see.png)

```
[{"id":"f6a99b3.38cab68","type":"inject","z":"56b28383.2dda4c","name":"","topic":"","payload":"","payloadType":"str","repeat":"","crontab":"","once":false,"x":150,"y":2320,"wires":[["ea2ace8a.6543f8","20096a70.a7fe46","bdd60ccc.8263b"]]},{"id":"ea2ace8a.6543f8","type":"tjbot-see","z":"56b28383.2dda4c","botId":"d3235679.be9cf","mode":"see","name":"","x":410,"y":2320,"wires":[["669aaba0.8388c4","8006af16.839f88"]]},{"id":"669aaba0.8388c4","type":"function","z":"56b28383.2dda4c","name":"","func":"msg.payload = 'Watson sees '+msg.payload.map(function(c) {\n    return c['class'];\n}).join(', ');\nreturn msg;","outputs":1,"noerr":0,"x":550,"y":2320,"wires":[["bf982347.b2aa9","363bfe68.95b8fa"]]},{"id":"bf982347.b2aa9","type":"debug","z":"56b28383.2dda4c","name":"","active":true,"console":"false","complete":"payload","x":730,"y":2320,"wires":[]},{"id":"aa869506.9206f8","type":"comment","z":"56b28383.2dda4c","name":"TJBot Sees","info":"","x":150,"y":2280,"wires":[]},{"id":"d3235679.be9cf","type":"tjbot-config","z":"","botGender":"male","name":"TJBot","listen":"en-US","speak":"en-US"}]
```

## Parler

Prononcer le contenu à l'aide du service de synthèse vocale Watson et du haut-parleur associé.

![](/images/speak.png)

```
[{"id":"567b1db3.f891e4","type":"inject","z":"68e8b9a0.f2e068","name":"","topic":"","payload":"Hello!","payloadType":"str","repeat":"","crontab":"","once":false,"x":250,"y":560,"wires":[["743a2025.96edd8"]]},{"id":"35aae517.095c72","type":"comment","z":"68e8b9a0.f2e068","name":"TJBot Speaks","info":"","x":250,"y":520,"wires":[]},{"id":"743a2025.96edd8","type":"tjbot-speak","z":"68e8b9a0.f2e068","botId":"5c94911d.6e7cd","name":"","x":390,"y":560,"wires":[[]]},{"id":"5c94911d.6e7cd","type":"tjbot-config","z":"","botGender":"male","name":"TJBot","listen":"en-US","speak":"en-US"}]
```

## Traduire

Traduire le contenu à l'aide du service Watson Language Translator.

![](/images/translate.png)

```
[{"id":"5bec3dcd.f6ab44","type":"tjbot-translate","z":"56b28383.2dda4c","botId":"d3235679.be9cf","srcLang":"en","targetLang":"es","name":"","x":340,"y":420,"wires":[["2adaeca3.b813d4"]]},{"id":"8d48087a.cd78a","type":"inject","z":"56b28383.2dda4c","name":"","topic":"","payload":"Hello from TJBot!","payloadType":"str","repeat":"","crontab":"","once":false,"x":140,"y":420,"wires":[["5bec3dcd.f6ab44"]]},{"id":"2adaeca3.b813d4","type":"debug","z":"56b28383.2dda4c","name":"","active":true,"console":"false","complete":"response","x":520,"y":420,"wires":[]},{"id":"d55f416b.b83be","type":"comment","z":"56b28383.2dda4c","name":"Yo Hablo Español","info":"","x":130,"y":380,"wires":[]},{"id":"d3235679.be9cf","type":"tjbot-config","z":"","botGender":"male","name":"TJBot","listen":"en-US","speak":"en-US"}]
```

## Mouvement du bras

Agiter le bras dans différentes positions.

![](/images/wavearm.png)

```
[{"id":"9b139cbc.1fac4","type":"inject","z":"56b28383.2dda4c","name":"","topic":"","payload":"","payloadType":"date","repeat":"","crontab":"","once":false,"x":120,"y":80,"wires":[["6b4be4fb.32602c"]]},{"id":"6b4be4fb.32602c","type":"tjbot-wave","z":"56b28383.2dda4c","botId":"d3235679.be9cf","motion":"wave","name":"","x":250,"y":80,"wires":[]},{"id":"47c05df5.89ebbc","type":"comment","z":"56b28383.2dda4c","name":"Wave Arm","info":"","x":100,"y":40,"wires":[]},{"id":"d3235679.be9cf","type":"tjbot-config","z":"","botGender":"male","name":"TJBot","listen":"en-US","speak":"en-US"}]
```
