# Set up instructions

This set up file includes set up instructions for applying the oh-my-posh theme on the following terminals:
- [PowerShell](https://github.com/Exator921/Dark-My-Posh/blob/main/SETUP.md#powershell)
- [Command Prompt](https://github.com/Exator921/Dark-My-Posh/blob/main/SETUP.md#command-prompt)
- [Bash](https://github.com/Exator921/Dark-My-Posh/blob/main/SETUP.md#bash)

Ensure you have oh-my-posh installed and download the theme [file](https://github.com/Exator921/Dark-My-Posh/blob/main/.dark-My-Posh.omp.json).
>[!TIP]
> It is recommended to have the theme file in your home directory for easy access of the file, but you can place it where ever you may need/want.

For instructions on other terminals please go to the [oh-my-posh instructions page](https://ohmyposh.dev/docs/installation/prompt).

## PowerShell
Open a text editor from your terminal to make and/or edit your $PROFILE file, an easy thing to do would be use notepad but you can use whatever will allow you to parse the $PROFILE file into.
```shell
notepade $PROFILE
```

With the theme installed and in a location you know the directory to, paste the following line:
```
oh-my-posh init pwsh --config [DIRECTORY].dark-My-Posh.omp.json | Invoke-Expression 
```
Of course replacing [DIRECTORY] with the actual files location. It is recommended to be places within your home directory.


Once the $PROFILE has been saved with the line provided, return to your terminal and reload your terminals source. This can be done by using the following command:
```shell
. $PROFILE
```

If done properly your user prompt section will change and show the new theme.

## Command Prompt
Command prompt (or otherwise called CMD) does not have a native way to use oh-my-posh so you must add a thirty-party software to use it, easily enough you can just use [Clink](https://chrisant996.github.io/clink/) for this process. Intall Clink following their installation instrunctions then return here, make sure you set up auto-start so you don't need to load it manually every time you open CMD.

With Clink now installed and set up on your CMD terminal you will need to create a `oh-my-posh.lua` file in your Clink Scripts directory, you can find that directory easily using the following command:
```shell
clink info
```
<sub>It is likely you'll find it `C:\Program Files (x86)\clink\scripts`</sub>

Once you've found the directory and made the `oh-my-posh.lua` file inside it, use a text editor to edit the file and paste the following line:
```lua
load(io.popen('oh-my-posh init cmd --config [DIRECTORY].dark-My-Posh.omp.json'):read("*a"))()
```
Of course replacing [DIRECTORY] with the actual files location. It is recommended to be places within your home directory.
> [!TIP]
> You can use notepad again for this however it is recommended you us an actual IDE text editor such as VScode.
> 
> To do this in notepade you can simply do the following
> ```cmd
> notepad oh-my-posh.lua
> ```
> and for VScode use
> ```cmd
> code oh-my-posh.lua
> ```

Once the file is edited and saved you must restart your CMD terminal to see it take effect.

## Bash
Bash is the easiest one to set up (*cause y'know, Linux. Why wouldn't it be*). All you have for setting the theme up in a bash terminal are three easy steps:

Open your source file, depending on your distribution/environment this can be done many ways:
```bash
sudo nano ~/.bashrc
sudo nano ~/.profile
sudo nano ~/.bash_profile
```
You'll know when you find your source when one of the files already has code in it.

Next, paste this line (DO NOT REPLACE WHAT IS ALREADY IN THERE):
```profile
eval "$(oh-my-posh init bash --config [DIRECTORY].dark-My-Posh.omp.json)"
```
Of course replacing [DIRECTORY] with the actual files location. It is recommended to be places within your home directory.

Once the line is added save the file and reload your source:
```bash
exec bash
```
Or
```bash
. ~/.profile
```
If done right, your use prompt sections will change applying the theme.
