# Keyboard Events

## keydown/ keyup

- fired when a key is pressed
- fired for all keys, no matter produce a char or not
- no difference for upper/lower case, get value from e.code

## keypress (Deprecated)

- indicate which char was entered 
- does not fired by Alt, Shift, Ctrl and Meta
- e.g. "a" reported as 97 and "A" as 65

## input 

- fire when value of <input>, <select> or <textarea> changed 