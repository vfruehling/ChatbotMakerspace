# ChatbotMakerspace

This repository provides a GitHub Codespace environment prepared to develop a transactional chatbot using **[Rasa Open Source](https://rasa.com/docs/rasa/)** for conversational flow and **[Node-RED](https://nodered.org)** for custom actions.

It is designed to accompany the hands-on **[AI Campus](https://www.ai-campus.org/)** course on conversational AI: [Step by Step zu deinem Chatbot - KI praktisch anwenden!](https://ki-campus.org/courses/conversational-ai).

### Setup Overview

This repository includes the setup for:

- A [GitHub Codespace](https://github.com/features/codespaces) environment
- A chatbot powered by [Rasa Open Source](https://rasa.com/docs/rasa/)
- An action server for the chatbot running on [Node-RED](https://nodered.org), which utilizes [node-red-contrib-rasa-actionserver](https://github.com/weberi/node-red-contrib-rasa-actionserver) nodes for integration

### Notes

#### Start Rasa

To start the Rasa server, use the following command:

   ```rasa run --port 5005 --cors "*"```

#### Using Chatroom.html
The following HTML code is a basic setup for a chatbot interface. Replace https://your-codespace-url-5005.preview.app.github.dev with the appropriate URL for your Codespace.
```
<!DOCTYPE html>
<html lang="en">

<head>
    <link rel="stylesheet" href="https://cdn.statically.io/gh/weberi/chatroom/master/dist/Chatroom.css" />
    <link rel="stylesheet" type="text/css" href="https://cdn.statically.io/gh/weberi/chatroom/master/index.css">
    <link rel="stylesheet" type="text/css" href="https://cdn.statically.io/gh/weberi/chatroom/master/themes/theme2.css" />
</head>
<body>
    <div class="chat-container"></div>
    <script src="https://cdn.statically.io/gh/weberi/chatroom/master/dist/Chatroom.js"></script>
    <script type="text/javascript">
    var chatroom = new window.Chatroom({
        host: "https://your-codespace-url-5005.preview.app.github.dev",   
        title: "Chat with a bot",
        container: document.querySelector(".chat-container"),
        welcomeMessage: "Nice to meet you.",
        speechRecognition: "en-US",
        voiceLang: "en-US"
    });
    chatroom.openChat();
    </script>
</body>
</html>
```
