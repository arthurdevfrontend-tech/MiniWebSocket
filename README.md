💬 MiniWebSocket 1.2.2
---
Um mini framework de WebSocket super leve e poderoso — agora com funções de chat estilo WhatsApp, suporte a salas, mensagens privadas, status, imagens e reconexão automática!
---
⚡️ Recursos Principais

✅ Conexão WebSocket simples e estável
✅ Auto-reconexão com fila de mensagens
✅ Salas e broadcast global
✅ Mensagens privadas entre usuários
✅ Histórico de mensagens local
✅ Envio de imagens (Base64)
✅ Sistema de status ("online", "digitando", etc.)
✅ Alteração de apelido (nickname)
✅ Ping automático e logs inteligentes
---
🧩 Instalação
```bash
npm install @arthurdevfrontend/miniwebsocket
```
Ou se preferir baixar manualmente:
```text
miniwebsocket.js
server.js
client.js
```

---

# 🚀 Como Usar
# 💻 Servidor (`server.js`)

```javascript
const { WebSocketServer } = require("./miniwebsocket");


const server = new WebSocketServer({ port: 8080 });


server.on("message", (msg) => {
  console.log("📩 Servidor recebeu:" , msg)
});
```
# 💻 Cliente (`client.js`)

```javascript
const { MiniWebSocket } = require("./miniwebsocket");

const client = new MiniWebSocket("ws://localhost:8080", {
  nick: "Arthur",
  debug: true
});

client.on("open", () => {
  client.joinRoom("geral");
  client.sendToRoom("geral", "Olá, galera 😄");
});

```

# 💡 Exemplo de Funções Disponíveis

| 🧩 Função | 💬 Descrição |
|------------|---------------|
| `joinRoom("geral")` | Entra em uma sala de chat |
| `leaveRoom("geral")` | Sai de uma sala |
| `sendToRoom("geral", "Oi!")` | Envia mensagem para a sala |
| `broadcast("Aviso para todos!")` | Envia mensagem para todos os conectados |
| `sendPrivate("Maria", "Oi, tudo bem?")` | Envia mensagem privada |
| `setNick("ArthurDev")` | Define um apelido (nickname) |
| `setStatus("digitando...")` | Atualiza o status atual do usuário |
| `sendImage("geral", base64)` | Envia imagem (em base64) como mensagem |
| `getRoomHistory("geral")` | Mostra o histórico da sala |

---

🧠 Estutura do Projeto
```bash
📁 Projeto
 ┣ 📜 miniwebsocket.js    # Biblioteca principal
 ┣ 📜 server.js            # Servidor WebSocket
 ┣ 📜 client.js            # Cliente de exemplo
 ┗ 📘 README.md            # Este arquivo 😎
```
---
🌐 Exemplo de Integração com Interface HTML
```html
<div id="chat">
  <ul id="messages"></ul>
  <input id="msg" placeholder="Digite uma mensagem..." />
  <button id="send">Enviar</button>
</div>
```

---

# 🧩 Logs e Debug
Ative o modo debug:
```javascript
const client = new MiniWebSocket("ws://localhost:8080", { debug: true });
```
Saída:
```yaml
🧩 MiniWebSocket: 🔗 Conectado!
🧩 MiniWebSocket: 🏠 Entrou na sala: geral
🧩 MiniWebSocket: 💌 Enviada mensagem privada para Maria
```

---

# 💬 Créditos
Feito com ❤ por **ArthurDevFrontend**
Desenvolvido com foco em aprendizado, simplicidade e performance.

---

🧱 Licença
Este projeto é de codigo aberto sob a licença MIT.
Sinta-se livre para usar, modificar e contribuir! for