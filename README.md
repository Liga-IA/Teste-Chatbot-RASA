# Teste-Chatbot-RASA

Apenas um repositorio para guardar os testes com o framework

## Como colocar o chatbot em um site

Não esquece de habilitar o socket no credentials, se não vai ficar dando 404

### Por script tag

<body>
  <!--https://chat-widget-docs.rasa.com/?path=/docs/rasa-chat-widget--widget-->
  <div  
    data-root-element-id="storybook-preview-wrapper"
    data-websocket-url="https://5005-gray-stork-zkryg336.ws-us17.gitpod.io" id="rasa-chat-widget"></div>
  <script src="https://unpkg.com/@rasahq/rasa-chat" type="application/javascript"></script>

### COmo componente React

Pena que isso aqui não funciona direito

Install the npm package:

`npm install rasa-webchat`

```
import Widget from 'rasa-webchat';

function CustomWidget = () => {
  return (
    <Widget
      initPayload={"/get_started"}
      socketUrl={"http://localhost:5500"}
      socketPath={"/socket.io/"}
      customData={{"language": "en"}} // arbitrary custom data. Stay minimal as this will be added to the socket
      title={"Title"}
    />
  )
}
```

## Comandos

No pipenv acho que vou ter que usar `pipenv run`

- `$ pipenv install rasa`
  - Instala o RASA
  - Demora um pouco uns 20 min +/-
- `$ pipenv shell`
- `$ pipenv run rasa init`
  - inicia o projeto
- `$ pipenv run rasa shell`
  - Aqui ele executa o bot pra conversar pela CLI

### Para rodar o serv do bot e integrar com site

- `$ rasa run -m models --enable-api --cors "*"`
