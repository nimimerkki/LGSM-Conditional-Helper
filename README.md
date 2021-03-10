# LGSM "Companion App 1"
Mini Helper to incorporate **Conditionals** into LGSM related operations

Ever fancied to update your LGSM-operated server **only if there was an update available?**

Ever pondered if it was possible to update your plugins **only if the game was updated too?**

Would you like to **reduce unwanted/unnecessary restarts** and/or updates?

For an example, only wanted to do a restart **if server was empty?**


*Well now you can!*


##
## Features (current and planned)
- [ ] Has a builtin `--help` & `--examples` to help you!
- [x] Can ask LGSM if the gameserver has an update available
- [x] Can ask LGSM if the gameserver is empty (requires gamedig)
- [x] Can also handle updating or restarting the `gameserver` for you (optional)
- [x] Can also handle updating mods for the `gameserver` for you (optional)
- [x] Can `--updateself` to keep itself up-to-date


##
## Dependencies & Installation
### Dependencies
* [LGSM](https://github.com/GameServerManagers/LinuxGSM) Of course!
   * If you want to use `--ifempty` then (otherwise optional) `gamedig` is required ([how-to](https://docs.linuxgsm.com/requirements/gamedig))
* Bash but you probably already got that if you got LGSM :P

### Installation & updating
**Basic installation:**
> While *anywhere* basically works, the *simplest installation location* is the same folder with your LGSM gameserver.
> * Copy/paste: `wget -O checkif https://git.io/LGSMhelper1 && chmod +x checkif` 

**Advanced installation:**
> You can rename the script to make it *auto-assume* one or the other fuction:
> * `--isempty` = Copy/paste: `wget -O isempty https://git.io/LGSMhelper1 && chmod +x isempty` 
> * `--canupdate` = Copy/paste: `wget -O canupdate https://git.io/LGSMhelper1 && chmod +x canupdate` 

**Updating:**
> A simple *reinstallation* does work as a method of updating, but you can also use:
> * `./checkif --updateself` = will replace itself with the latest copy from GitHub
>   * ~~Checks if newer version is available & only updates if needed~~ *(Coming soon!*)

## 
## Usage & examples
### Usage:
If nothing causes a `fail` (such as server not empty, or no update available, or an error occurring at some point), the *Companion App 1* will terminate with `exitcode 0`, which means `success` and continues the processing of `&&`-chained commands. If all conditions were not met (not empty, and/or no update available), another `exitcode` will instead be used, meaning `fail` and **preventing** the processing of any `&&`-chained commands that may following.

Typical usage-cases are cronjobs, but works *"manually"* from commandline just as well.

Depending on your installation (see above), you use either `./checkif`, `./isempty` or `./canupdate`, followed by any `<options>` you'd like, and one or more LGSM gameserver-files. <br> The following commandline parameters & options are available:
| Short | Long parameter & Description  |
| ----- | :---------------------------- |
| `-ie` | `--isempty`     <br> = Fails if server is not empty (Offline, or 0/xx players) |
| `-cu` | `--canupdate`   <br> = Fails if the server has no update available (LGSM's `-check-update`) |
|       | `--examples`    <br> = ~~Prints out usage-examples (some are below as well)~~ |
|       | `--help`        <br> = Prints out the *"in-app help"* :upside_down_face: |
| `-ne` | `--noerrors`    <br> = Supresses printing errors (Default = print errors.) |
| `-v`  | `--verbose`     <br> = Prints status & progress on screen (Default = no.) |
|       | `--updateself`  <br> = Updates self, `exitcode 0` if not needed, `non-0` otherwise |
| `-rg` | `--restartgame` <br> = Restarts *the gameserver* |
| `-ug` | `--updategame`  <br> = Updates *the gameserver* |
| `-um` | `--updatemods`  <br> = Also does a `mods-update` before (re)starting the gameserver (also requires `-ug` or `-rg` to work) |

### Other examples:
TODO: Add Cronjob examples here?
Add Commandline examples also?


##
## Credits

* [LGSM](https://github.com/GameServerManagers/LinuxGSM) & the author of it, [DanGibbs](https://github.com/dgibbs64) 
   * LGSM's sourcecode + Google = *Excellent Bash programming guide!* 
* Stanley (and other folk) @ [LGSM's Discord](https://linuxgsm.com/discord) (Orig.idea *(see `Goal #3`)*, BetaTesting & feedback.)
* My family for leaving the house for a day and giving me a *Computer Day* :sunglasses:


##
## Goals & personal review of the project
**Goals** of the project were:
1. Learning GitHub
   - [ ] My first GitHub project, branch, pull request etc... = I'd say about 50%-70% done :sweat_smile:
1. Learning to code in Bash
   - [x] Do-did-done 😎
1. Making the occasionally sought-after, but missing, functionality of LGSM a reality:
   - [x] Do it without adding any further depencies (such as perl) = achieved 100%!
   - [x] `"if update available"` = Works! (100%)
   - [x] `"if empty"` = Works! (100%)
   - [x] `exitcodes` used to natively determine wether to continue with `&&`-chained commands or not

**AfterThoughts:** 
> Overall I'm satisfied.

> And if people use it = *"It has a purpose"* = **Even better!** :innocent:
