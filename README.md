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

function open_fav() {
    # Remind user what the function is doing
    echo 'Opening your favorite web page'

    # Open page in default browser
    open 'https://github.com/BrockNicholas'
    
}

function open_safari() {
    # Remind user what the function is doing
    echo 'Opening your favorite web page in Safari'

    # Open page in Safari specifically
    open -a Safari 'https://github.com/BrockNicholas'
}






