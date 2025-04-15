# Dark-My-Posh Advanced
A simple theme for Oh-My-Posh! to make your terminal simple and informative.

![image](https://github.com/user-attachments/assets/5744b167-fb98-4766-bac1-41de8eed3b40)
*The background of the terminals does not come with the theme*

Dark-My-Posh is compatible with PowerShell (1.0 or more), CMD, and Bash (Linux and WSL) terminals and can further be edited to read for other terminals on your system.

The following symbol shows if your terminal is in administrator [ ⛯ ]. [This has not changed from the base version]

The diamond shows the status of your last commands exit code (*Successful or failure, see images belown*):
![image](https://github.com/user-attachments/assets/1f1ed2c3-e179-4916-bf5a-b9e3ecd5ac98)
![image](https://github.com/user-attachments/assets/dbf687eb-c310-4f46-bd6b-06315d5264d0)
If the command failed the diamond will go red, if successful it will stay magenta. [This has not changed from the base version]

Dark-My-Posh also supports command run time, shows how long a command took to run. [This has not changed from the base version]
![image](https://github.com/user-attachments/assets/22d4d427-230e-4736-93e2-d8b16e919640)

It also gives simple Git info if your CWD is a repository:
- `main⇡` if you are ahead of your branch.
- `⇣main` if you are behind your branch.
- `*main` if you have unstagged changes.
- `main*` if you have stagged changes.
- `┎main` if you are detached from your branch.
- `main` if nothing is detected between repo and CWD.
[This has not changed from the base version]

## Advanced specific featers
- It now looks for the shell version of the running terminal
- It checks for if your on CMD to not print it's version (CMD does not get updates so it's on a static version)
- And finally checks if your terminal is a Windows Subsystem for Linux (WSL) terminal and prints it as well as showing the Shell level (If it is in admin level or not)


It is recommended you use the `SauceCodePro Nerd Font` however any nerdfont should work fine with this theme.

For set up instructions please visit the [Oh-My-Posh instructions page](https://ohmyposh.dev/docs/installation/prompt) or refer to the [SETUP.md](https://github.com/Exator921/Dark-My-Posh/blob/main/SETUP.md) file within this repository. Please ensure you download the theme and schema for this version and have them within the same directory.

<sub>Creator rights go to Exator911. Copyright belongs to the public domain, you may not claim copyright over the code and attempt to sue the creator as you don't own the rights to the code. This code is public use for a reason.</sub>
