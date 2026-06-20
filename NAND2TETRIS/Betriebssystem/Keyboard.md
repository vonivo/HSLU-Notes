Für die Eingabe über die Tastatur.
**API**
```java
function char keyPressed();
function char readChar();
function char readLine(String message);
function char readInt(String message);
```


## keyPressed
```
// returns the character of the currently pressed key on the 
// keyboard; if no key is currently pressed, returns 0;

keyPressed():
	if a keyboard key is pressed:
		return the key's character code
	else
		return 0
```
- `Memory.peek` verwenden.
## readChar
```java
// waits until a key is pressed on the keyboard and released, then 
// echoes the key to the screen and returns the character of the 
// pressed key;

readChar():
	display the cursor
	// wait until press
	while (keyPressed() == 0)
		do noting
	c = code of the currently pressed key
	// wait until release
	while (keyPressed() != 0)
		do noting
	display c at the current cursor location
	advance the cursor
	return c
```

## readLine
```java
// prints the message on the screen, reads the line (text until a 
// newline character is detected) from the keyboard, echoes the line 
// to the screen, and returns its value. This function also handles 
// user backspace
readLine( ):
	// Read and echo a ‘‘line’’ (until newline) 
	s = empty string 
	repeat 
		c = readChar( ) 
		if c = newline character 
			print newline 
			return s 
		else if c = backspace character 
			remove last character from s 
			move the cursor 1 position back 
		else 
			s = s.append(c)
```