# Docker
Some Docker recipes

## Some Notes
Alpine container image does not use the traditional gcc libs, instead it uses something called "musl" for gcc . This means compiling code that uses gcc will b a lot slower.
For example installing NodeJS can take upto 40mins

So where possible anything that needs to do some C compiling, would recommend:
a) use a different image that has traditional gcc libs (means bigger image size)
b) if installing libs that need compiling, put the compiling bit on to its own layer.
c) stick with it, as your application code requires it and you don't mind waitining for your docker app image.