# Set up instructions

This set up file includes set up instructions for applying the oh-my-posh theme on the following terminals:
- [PowerShell](https://github.com/Exator921/Dark-My-Posh/blob/advanced/SETUP.md#powershell)
- [Command Prompt](https://github.com/Exator921/Dark-My-Posh/blob/advanced/SETUP.md#command-prompt)
- [Bash](https://github.com/Exator921/Dark-My-Posh/blob/advanced/SETUP.md#bash)
- [Bash {Root}](https://github.com/Exator921/Dark-My-Posh/blob/advanced/SETUP.md#bash-root)

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
Of course replacing [DIRECTORY] with the actual files location. It is recommended to be placed within your home directory.


Once the $PROFILE has been saved with the line provided, return to your terminal and reload your terminals source. This can be done by using the following command:
```shell
. $PROFILE
```

If done properly your user prompt section will change and show the new theme.

## Command Prompt
Command prompt (or otherwise called CMD) does not have a native way to use oh-my-posh so you must add a third-party software to use it, easily enough you can just use [Clink](https://chrisant996.github.io/clink/) for this process. Intall Clink following their installation instrunctions then return here, make sure you set up auto-start so you don't need to load it manually every time you open CMD.

With Clink now installed and set up on your CMD terminal you will need to create a `oh-my-posh.lua` file in your Clink Scripts directory, you can find that directory easily using the following command:
```shell
clink info
```
<sub>It is likely you'll find it in `C:\Program Files (x86)\clink\scripts`</sub>

Once you've found the directory and made the `oh-my-posh.lua` file inside it, use a text editor to edit the file and paste the following line:
```lua
load(io.popen('oh-my-posh init cmd --config [DIRECTORY].dark-My-Posh.omp.json'):read("*a"))()
```
Of course replacing [DIRECTORY] with the actual files location. It is recommended to be placed within your home directory.
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
Of course replacing [DIRECTORY] with the actual files location. It is recommended to be placed within your home directory.

Once the line is added save the file and reload your source:
```bash
exec bash
```
Or
```bash
. ~/.profile #If applicable change "profile" to what your source file is.
```
If done right, your user prompt sections will change applying the theme.

## Bash {Root}
> [!NOTE]
> For applying to root user you will need to have it on your main user first, follow the steps above if you haven't already.

Ensure Oh-My-Posh is installed on the system, if it is not you can install it for the root user by following the installation guide. If it is already installed from the main user make it available to all users using the following command:
```bash
sudo cp "$(which oh-my-posh)" /usr/local/bin/
```

Next, you need to edit the source of the root user. You can do this from main or root but it will be easier (in my opinion) to use the main user to edit this. Use the following command to open the root users source:
```bash
sudo nano /root/.bashrc
```

Next at the bottom of the file, paste this line (DO NOT REPLACE WHAT IS ALREADY IN THERE):
```profile
eval "$(oh-my-posh init bash --config [DIRECTORY].dark-My-Posh.omp.json)"
```
Of course replacing [DIRECTORY] with the actual files location. It is recommended to be placed within your home directory.

From there exit the root user and sign back into it to see the theme applied.
