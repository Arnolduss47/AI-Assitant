A modular AI assistant that processes natural language commands, executes system-level actions, and can be extended with voice and ML components.

Receive basic commands and execute functions 
- Tell the time
- Open apps
- Control volume 
- Exit applications

```
InputHandler
→ TextProcessor
→ IntentDetector
→ EntityExtractor (target like "chrome")
→ CommandExecutor
```

The user will input a command using the console the command will trigger an action and it will be executed.

```
GET_TIME → function getTime()
OPEN_APP → function openApp(target)
CONTROL_VOLUME
EXIT_APP
UNKNOWN
```

```
Input: "please open chrome"

Step 1: normalize → "please open chrome"
Step 2: tokenize → ["please", "open", "chrome"]
Step 3: remove filler → ["open", "chrome"]
Step 4: detect intent → "open" → OPEN_APP
Step 5: extract target → "chrome"
Step 6: map → "chrome" → "chrome.exe"
Step 7: execute
```

The system will only extract the first keyword and remove any fillers after
```
Raw Input
→ TextProcessor  
	- normalize  
	- tokenize  
	- remove filler words  
	→ IntentDetector  
→ EntityExtractor  
→ CommandExecutor
```

Each command should have keywords that refine the prompt
```
- GET_TIME → “time”, “clock”
- OPEN_APP → “open”, “launch”, “start”
```
