A modular AI assistant that processes natural language commands, executes system-level actions, and can be extended with voice and ML components. Receive basic commands and execute functions - Tell the time - Open apps - Control volume - Exit applications

```
InputHandler
→ TextProcessor
→ IntentDetector
→ EntityExtractor (target like "chrome")
→ CommandExecutor
```

The user will input a command using the console the command will trigger an action and it will be executed.

```
GET_TIME
OPEN_APP
CONTROL_VOLUME
EXIT_APP
UNKNOWN
```

```
Input: "Open Chrome"

Step 1: normalize → "open chrome"
Step 2: tokenize → ["open", "chrome"]
Step 3: detect intent → "open" → OPEN_APP
Step 4: extract target → "chrome"
Step 5: map → "chrome" → "chrome.exe"
Step 6: execute
```

```
Raw Input
→ Normalize text
→ Tokenize (split words)
→ Detect intent
→ Extract parameters (like "chrome")
→ Execute
```

Each command should have keywords that refine the prompt

```
- GET_TIME → “time”, “clock”
- OPEN_APP → “open”, “launch”, “start”
```