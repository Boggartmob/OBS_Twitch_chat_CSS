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

```css
* {
	background: transparent !important;

	font-family: "Calibri" !important;
	/* font-family: "Segoe Print" !important; */
	/* font-family: "Comic Sans MS" !important; */
}

.chat-line__message-container * {
	font-size: 2rem !important;
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

6. You can tune font style updating very first section of the CSS, following lines:
```css
font-family: "Calibri" !important;
/* font-family: "Segoe Print" !important; */
/* font-family: "Comic Sans MS" !important; */
```
To uncomment line just remove "/\*" and "\*/" in the start and the end of the line.
To add new font - just add line like
```css
font-family: "FONT NAME HERE" !important;
```
Please note very last available font will apply to chat window. Windows default fonts list could be found here: https://en.wikipedia.org/wiki/List_of_typefaces_included_with_Microsoft_Windows

7. You can adjust font size changing following part of css:
```css
.chat-line__message-container * {
	font-size: 2rem !important;
}
```
Replace `2rem` with `<NUMBER>rem` including floats like `2.5rem`. `1rem` is default twitch defined font size.

#OBS #chat #widget #transparent #css #transparentchat #chatcss #obschatwidget
