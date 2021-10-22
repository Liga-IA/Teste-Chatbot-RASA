# Teste-Chatbot-RASA

Apenas um repositorio para guardar os testes com o framework

## Como colocar o chatbot em um site

### Por script tag

<script>!(function () {
  let e = document.createElement("script"),
    t = document.head || document.getElementsByTagName("head")[0];
  (e.src =
    "https://cdn.jsdelivr.net/npm/rasa-webchat@1.x.x/lib/index.js"),
    // Replace 1.x.x with the version that you want
    (e.async = !0),
    (e.onload = () => {
      window.WebChat.default(
        {
          customData: { language: "en" },
          socketUrl: "https://bf-botfront.development.agents.botfront.cloud", // só trocar o link
          // add other props here
        },
        null
      );
    }),
    t.insertBefore(e, t.firstChild);
})();
</script>

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
