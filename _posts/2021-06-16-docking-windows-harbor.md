This is my third attempt at migrating the dev environment from Mac to Windows. I used to develop apps on Mac for 5 years. With all my muscle memory on keymaps, productivity tools, and the general UX is stick to Mac, I can't think of moving to another OS, until the quarantine day. I got locked down at home for a month, and my 2017 Mac started to slow since I start C# development with Rider. And I have my gaming PC stay here just for Doto2. Whew, I think it's time.

- The first attempt a year ago is about native app prebuild for Windows like nvim-qt, vscode, Windows terminal... I quit after a few days cause I miss my keymap.

- After a few months, the second attempt is about WSL, this time I dig deeper into the real command-line tools like curl, git, grep, gcloud, kubectl, autojump... And I'm too lazy for learning the powershell way to do it, then I went with WSL. And you know what, WSL sucks, with a ton of troubles while install and using it through Windows terminal.

- And this time is the third.

I have to accept that I can't make the experience on Windows exactly like Mac. Since I know to live with compromise, I know how to deal with this situation. Besides, I don't want to be a sheeple that sticks to every generation of Mac even when it sucks. So, the first thing that comes to mind is to learn to compromise.

# The editor

The most frustrating thing with Windows is I can't config Vim - my main editor exactly like what I have in Mac. For example, I have Karabiner Elements to map jk to ESC, it's super productive while the escape is right at your finger, but I don't have it here. Fzf is experimenting on Windows, it's buggy and doesn't work at all in my case, Windows terminal not very good with vim running inside...

> I have to config Rider and Vscode as much as I can, compromised with something missing.

# The command-line tools

Git is the second most important tool. I have several alias functions for git, which combine several commands in one function which helps save time on repetitive tasks. It works on whatever shells except for Powershell... So I have to learn PowerShell way and transform those command one by one, like this:
It is quite similar to bash shell syntax but it still needs some research and transforms all of them. I have like 10 frequently use commands like that, e.g., tagging, rebasing, showing log, pull with rebase... for example, git merge to master

```bash
function gmerge() {
  $CURRENT_BRANCH = & invoke-Expression gcurrent 2>&1
  $TO_BRANCH="master"

  "> Merging $CURRENT_BRANCH -> $TO_BRANCH"

  "> git checkout $TO_BRANCH"
  git checkout $TO_BRANCH

  "> git merge --no-ff $CURRENT_BRANCH"
  git merge --no-ff $CURRENT_BRANCH

  "> git commit -m 'Merge branch $CURRENT_BRANCH'"
  git commit -m "Merge branch $CURRENT_BRANCH"

  "> git push origin $TO_BRANCH"
  git push origin $TO_BRANCH

  "> Delete $CURRENT_BRANCH branch from local"
  git branch -D $CURRENT_BRANCH
}
```

For the other command, Windows has `scoop`, it will install the prebuild CLI program which works similar to the program on Linux or Mac. If scoop doesn't have that, MSYS2 comes to the rescue. Most frequently used is curl, gcloud, autojump, grep, cat, tail, pwd... So far the command line is quite the same.

# The terminal

Windows doesn't have much choice on the terminal app, cause most of them is ugly af. Windows terminal so far is the best, with true color, tab and pannel support, able to open all kinds of shells.

![image](images/window-terminal.png)

It still need a lot to improve but at least it good enough for now.

# Productivity tools

## Window management

I introduce you to PowerToys, a series of productive tools for Windows. There is a tool name FancyZones which helps to split the windows by the predefined layouts. But I found it's kind of complex to use, hundred times harder to use than my favorite tool on Mac name Spectacles. So the basic default Win + up/down/left/right is enough for me.

If you want to press the Space key to preview a file, there is a tool name QuickLook on Windows Store can helps.

## Spotlight search

PowerToys also have tool PowerToys Run, it does search for file, application, calculator, run a shell command, open url, run a window command.

## Key remapping

PowerToys Keyboard Manager can help to remap the simple keystrokes. I don't want to relearn the memory muscle so that I map all the familiar keystrokes like alt+c, alt+v to ctrl+c, ctrl+v, and so on. 

![](images/window-keys-remapping.png)
I also use the F keys to quick launch the app, which is super productive for me. For example, I usually switch between Chrome, Terminal, Vim, Postman for the development, mapping it directly to F1, F2, F3, F8... check out my AutoHotkey dot file

```autohotkey
#NoEnv  ; Recommended for performance and compatibility with future AutoHotkey releases.
F1::
if WinExist("ahk_exe chrome.exe",,"Picture-in-Picture")
    WinActivate
return

F2::
if WinExist("ahk_exe code.exe")
    WinActivate
return

F3::
if WinExist("ahk_exe WindowsTerminal.exe")
    WinActivate
return

F4::
if WinExist("ahk_exe rider64.exe")
    WinActivate
return

F5::
if WinExist("ahk_exe firefox.exe",,"Picture-in-Picture")
    WinActivate
return

F6::
if WinExist("ahk_exe discord.exe")
    WinActivate
return

F7::
if WinExist("ahk_exe Slack.exe")
    WinActivate
return

F8::
if WinExist("ahk_exe Postman.exe")
    WinActivate
return

F9::
if WinExist("ahk_exe pritunl.exe")
    WinActivate
return
```

# Conclusion

It is not the end of the road yet, I just switch to Windows for a few weeks, and the post will be updated.

There are something still makes me uncomfortable, my favorite editor is NeoVim but it is not fully working on Windows yet, my favorite fzf.vim still unstable and buggy which prevents me from using it as a daily driver. There are no Apple Photos, iMessage, Notes, and other productivity apps that belong to the Apple ecosystem available here. I have to compromise because the computer power is huge compare to my Macbook pro.
I think a big Mac Pro with 28 cores and 64Gb of Ram will resolve all the trouble above.
