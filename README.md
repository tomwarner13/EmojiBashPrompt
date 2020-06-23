# EmojiBashPrompt
A cool Bash prompt that uses emojis and colors to provide useful status info

To create this prompt, add the following line to your ~/.bashrc file, then run `source ~/.bashrc` to tell Bash to pick up on the changes.

`export PS1="🏠\[\033[38;5;214m\]\u\[$(tput sgr0)\]@\[\033[38;5;39m\]\h\[$(tput sgr0)\][\[\033[38;5;11m\]\W\[$(tput sgr0)\]]|\[\033[38;5;213m\]\t\[$(tput sgr0)\]🏠\$ "`

The output looks like this:

![prompt](https://raw.githubusercontent.com/tomwarner13/EmojiBashPrompt/master/prompt.png)

So that's `🏠<<USER,ORANGE>>@<<MACHINE NAME,BLUE>>[<<CURRENT DIRECTORY NAME,YELLOW>>]|<<CURRENT TIME,PURPLE>>🏠$ `

You can edit your prompt by messing around with the gibberish in between the double-quotes, that's bash-specific codes to change colors and include custom variables.

I use the house emojis because this prompt is for my local machine. My main virtual development box that I connect to uses cloud emojis--it's a quick way to tell which one I'm typing on.

The parts that look like `\[\033[38;5;214m\]` are color codes; they tell the terminal to change the text color. You can look them up to change them to different ones.

The `[$(tput sgr0)\]` tells the terminal to stop changing the text color, so it goes back to your default color until instructed otherwise.

`\u` is "currently logged in user", useful for obvious reasons. I colored it orange.

`\h` is the machine name, again obviously useful. I colored it blue.

`\W` is the short name of the current working directory, not the full path. I colored it yellow. Again, obviously useful.

`\t` is the current local time in 24-hour format. There are other codes for time formats you can look up but this one is the one I like best. Having the time in a prompt is actually suprisingly crucial because you can tell when you ran a command and when it finished just by looking at your prompt.

Then there's another house emoji and a space at the end. If I start developing on more machines I'll pick a unique emoji for each so I can have instant visual confirmation of where my SSH session is connected to. Also, emojis are fun and cool 😄😎
