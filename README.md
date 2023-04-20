# OBS Twitch transparent chat CSS

To use twitch chat window directly without any third-party software

Solution works for Twitch chat only.

Please follow instructions below to get transparent chat widget in your OBS translation without third party software:

1. Get your embedable chat window URL: 
  ```
  https://www.twitch.tv/embed/<channel>/chat?parent=<parent>
  ```
  where `<channel>` is your channel name, `<parent>` is "localhost". For me it is
  ```
  https://www.twitch.tv/embed/boggartmob/chat?parent=localhost
  ```
  [Twitch documentation](https://dev.twitch.tv/docs/embed/chat/)
  
2. Add "Browser" widget to your OBS scene for chat window, tune its size.
3. Use chat URL from (1.) for "Browser" widget "URL" property.
4. Use following CSS for "Browser" widget "Custom CSS" property:

```
* {
	background: transparent !important;
}

.stream-chat-header, #chat-room-header-label, .chat-input {
	display: none !important;
}

.chat-scrollable-area__message-container {
	font-size: 3em !important;
	line-height: 1.5em;
}

.text-fragment {
	color: white !important;
}

div[data-a-target="chat-welcome-message"], div[data-a-target="moderation-action"], .chat-line__status {
	display: none;
}
```

<img src="https://user-images.githubusercontent.com/495081/233375038-1d297fc0-3729-45f9-ada2-865ae552fcfa.png" width="75%"/>

5. Click OK and enjoy.

#OBS #chat #widget #transparent #css #transparentchat #chatcss #obschatwidget
