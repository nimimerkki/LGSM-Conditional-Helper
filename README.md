# LGSM "Companion App 1"
Mini Helper to incorporate **Conditionals** into LGSM related operations

Ever wanted to update your LGSM-operated server **only if there was an update available?**

Only wanted to do restart **if server was empty?**

*Well now you can!*


##
## !!! WARNING !!!
> **This is still in DEBUG-MODE, meaning that it will NOT work as you think it would!**
*(unless you edit the code)*



##
## Features (current and planned)
- [ ] Has a builtin `--help` & `--examples` to help you!
- [x] Can ask LGSM if the gameserver has an update available
- [x] Can ask LGSM if the gameserver is empty (requires gamedig)
- [x] Can also handle updating the `gameserver` for you (optional)
- [x] Can also handle updating mods for the `gameserver` for you (optional)
- [ ] Can `--updateself` to keep itself up-to-date


##
## Dependencies & Installation
### Dependencies
* [LGSM](https://github.com/GameServerManagers/LinuxGSM) Of course!
   * `--ifempty` requires `gamedig` to be installed ([how-to](https://docs.linuxgsm.com/requirements/gamedig))
* Bash but you probably already got that if you got LGSM :P

### Installation
**Basic installation:**
> copy/paste: `wget -O checkif LINKHERE && chmod +x checkif` 

**Advanced installation:**
> You can rename the script to make it *auto-assume* one or the other fuction:
> * `--isempty  ` = copy/paste: `wget -O isempty LINKHERE && chmod +x isempty` 
> * `--canupdate` = copy/paste: `wget -O canupdate LINKHERE && chmod +x canupdate` 


## 
## Usage & examples
### Usage:
If nothing causes a `fail` (such as server not empty, or no update available, or an error occurring at some point), the *Companion App 1* will terminate with `exitcode 0`, which means `success` and continues the processing of `&&`-chained commands. If all conditions were not met (not empty, and/or no update available), another `exitcode` will instead be used, meaning `fail` and **preventing** the processing of any `&&`-chained commands that may following.

Typical usage-cases are cronjobs, but works *"manually"* from commandline just as well.

Depending on your installation (see above), you use either `./checkif`, `./isempty` or `./canupdate`, followed by any `<options>` you'd like, and one or more LGSM gameserver-files. The following commandline parameters & options are available:
| Parameter   | short | Description |
| ------------ | --- | :------------ |
| --isempty    | -ie | Fails if server is not empty (Offline, or 0/xx players) |
| --canupdate  | -cu | Fails if the server has no update available (LGSM's `-check-update`) |
| --examples   |     | Prints out usage-examples (some are below as well) |
| --help       |     | Prints out the *"in-app help"* :upside_down_face: |
| --noerrors   | -ne | Supresses printing errors (Default = print errors.) |
| --verbose    | -v  | Prints status & progress on screen (Default = no.) |
| --updateself |     | *( Not done yet )* |
| --updategame | -ug | Updates *the gameserver* |
| --updatemods | -um | Also does a `mods-update` before (re)starting the gameserver (also requires `--updategame` to work) |

### Other examples:
TODO: Add Cronjob examples here?
Add Commandline examples also?


##
## Credits

* [LGSM](https://github.com/GameServerManagers/LinuxGSM) & the author of it, [DanGibbs](https://github.com/dgibbs64)
* Stanley (and other folk) @ [LGSM's Discord](https://linuxgsm.com/discord)
* My family for leaving the house for a day and giving me a *Computer Day* :sunglasses:


##
## Goals & personal review of the project
Goals of the project were:
1. Learning GitHub
   - [ ] My first GitHub project, branch, pull request etc... = I'd say about 50%-70% done :sweat_smile:
1. Learning to code in Bash
   - [x] Do-did-done
1. Making the occasionally sought-after, but missing, functionality of LGSM a reality:
   - [x] Do it without adding any further depencies (such as perl) = achieved 100%!
   - [x] `"if update available"` = works! (100%)
   - [x] `"if empty"           ` = works! (100%)

Overall I'm satisfied.
And if people use it, *"it has a purpose",* even better! :innocent:
