# Set up instructions

This set up file includes set up instructions for applying the oh-my-posh theme on the following terminals:
- PowerShell
- Command Prompt
- Bash

For instructions on other terminals please go to the [oh-my-posh instructions page](https://ohmyposh.dev/docs/installation/prompt)

## PowerShell
Open a text editor from your terminal to make and/or edit your $PROFILE file, an easy thing to do would be use notepad but you can use whatever will allow you to parse the $PROFILE file into.
```shell
notepade $PROFILE
```

With the theme installed and in a location you know the directory to, paste the following line:
```
oh-my-posh init pwsh --config [DIRECTORY].dark-My-Posh.omp.json | Invoke-Expression 
```
Of course replacing [DIRECTORY] with the actual file locations. It is recommended to be places within your home directory.


Once the $PROFILE has been saved with the line provided, return to your terminal and reload your terminals source. This can be done by using the following command:
```shell
. $PROFILE
```

If done properly your user prompt section will change and show the new theme.

## Command Prompt
Command prompt (or otherwise called CMD) does not have a native way to use oh-my-posh so you must add a thirty-party software to use it, easily enough you can just use [Clink](https://chrisant996.github.io/clink/) for this process. Intall Clink following their installation instrunctions then return here, make sure you set up auto-start so you don't need to load it manually every time you open CMD.

With Clink now installed and set up on your CMD terminal you will need to create a `oh-my-posh.lua` file in your Clink Scripts directory, you can find that directory easily using the following command
```shell
clink info
```
Once you've found the directory and made the `oh-my-posh.lua` file inside it, use a text editor to edit the file and paste the following line:
```
load(io.popen('oh-my-posh init cmd --config [DIRECTORY].dark-My-Posh.omp.json'):read("*a"))()
```
> [!TIP]
> You can use notepad again for this however it is recommended you us an actual IDE text editor such as VScode.
> to do this in notepade you can simply do the following
> ```shell
> notepad oh-my-posh.lua
> ```
> and for VScode use
> ```shell
> code oh-my-posh.lua
> ```

Once the file is edited and saved you must restart your CMD termianl to see it take effect.

## Bash
