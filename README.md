# CustomShellFunction
Create custom shell functions (BASH or Zsh) (Mac)

## Setup
Create a new .sh file at /usr/local/bin/custom-function.sh

You can use any IDE of course, but if you need help: \
e.g., `vi /usr/local/bin/custom-file.sh`

If using vi (not recommended), type `i` to enter insert mode. 
Save your changes by hitting the Esc key, type `:x` and hit Enter

Include this compiler directive at the top of custom-function.sh \
`#!/bin/bash`

If you only want to create one function, you can type it directly into the file \
e.g.,

>#!/bin/bash \
> \
> echo 'Hello, World!'

Here is an example with multiple functions. I use them for opening some predefined websites I use regularly
#!/bin/bash

>function open_fav() { \
>    &nbsp;&nbsp;\# Remind user what the function is doing \
>    &nbsp;&nbsp;echo 'Opening your favorite web page' 
> 
>
>    &nbsp;&nbsp;\# Open page in default browser \
>    &nbsp;&nbsp;open 'https://github.com/BrockNicholas' 
>    
>}
>
>function open_safari() { \
>    &nbsp;&nbsp;\# Remind user what the function is doing \
>    &nbsp;&nbsp;echo 'Opening your favorite web page in Safari' 
> 
>
>    &nbsp;&nbsp;\# Open page in Safari specifically \
>    &nbsp;&nbsp;open -a Safari 'https://github.com/BrockNicholas' \
>}

To tell your shell about your functions, add the following to your .bashrc file:
`source /usr/local/bin/custom-function.sh`

Then reload the .bashrc file
`source ~/.bashrc`

Now you should be able to run the functions in your shell

e.g., 
#### No defined functions
`. /usr/local/bin/custom-function.sh`

#### Call a function
Just type it's name
`open_fav`

## Send parameters
In your function, use "$1", "$2", etc. to refer to your parameters
e.g.,

>function say-hello-world() {
>&nbsp;&nbsp;echo "$1" World!
>}

When you call your function:

`say-hello-world Hello`

## Remove custom functions
Erase `source /usr/local/bin/custom-function.sh` from .bashrc file

To remove an individual function: \
`unset -f function_name`

To remove all of the functions in a shell file: \
`exec bash` \
This will reset the shell to it's startup version and, since you deleted the source to your custom function, it'll be gone

## Zsh
To use Zsh instead of Bash, replace all of the references to "bash" in these directions with "zsh"
