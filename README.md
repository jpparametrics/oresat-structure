# oresat-structure
Mechanical structure for [OreSat](http://www.oresat.org)

This repo contains the top-level assembly of OreSat and the trivial subassemblies. If you'd like to contribute, drop in on the [Google hangout][hangout] (Fridays at 2 pm), [read the issues][issues], and/or read the [contributions guide.][contrib] 

The top-level assembly requires the [reaction wheels] repo be cloned into the same directory, e.g.:  

    OreSat/
     |-- reaction-wheels/
     |-- oresat-structure/

## Ultra-pro-tip: 
* Tools -> Component Selection -> Advanced Select...
* Either:
  * Filter for document names which contain `COTS`. Name this selection and save it.
  * Import `selectCOTS.xml`
* Apply the selection.
* Edit -> Hide -> Current Display State  
This hides any components which come from the `COTS/` directory (really anything with "COTS" in the name), which reduces lag significantly.  
If you want to show them again, use the same filter process, but show the current display state. 
If you want to show everything, you can just ctrl+a in the feature tree. If you're showing lots of COTS parts, please hide them before committing, since it can cause the model to load very slowly.

## TODO:  
- [X] Get the UO team to choose a camera!
- [x] Fix the assembles/tech drawings to match Nanorack's convention of XYZ. (Helical goes on +Z. Backplane goes on -X) (@paperman5)
- [x] Create keepout volumes (parts in the assembly) that correspond to the CubeSat and Nanoracks specifications. (@jalouke)
- [ ] (Re)design the helical antenna. (@paperman5)
	- [X] Model the strings that will keep the helical rigid.
	- Actually, it looks like this is going to become a capstone.
- [ ] (Re)design the turnstile antenna. 
    - [ ] Build a working mockup of the deployment.
    - This is going to be part of the same capstone that does the helical antenna.
- [X] Fix/check connector alignment on the backplane. (@joedang)
- [X] Modify space foam to not interfere with the screws that hold the frame together. (@RocketmanYG)
- [X] Gather info on and/or bug ECEs about the kill switches and RBF (Remove Before Flight) tag. (@hmarie2)
- [X] Consolidate all COTS parts into the COTS folder. 
- [ ] Update BoM with quantities. (Preferrably as a CSV, so it's not treated as a binary.)
- [ ] Design a board that can act as an adapter for a PC 104 board? (This will either require chopping some corners off of the PC 104 or adding cutouts to the frame.)
- [ ] Complete the inhibit switch assembly, using the measurements from the switches we ordered. (@joedang)
	- [ ] Modify the inhibit switch plunger to only have one sloping side.
	- [ ] Change to a "slide to open" rather than a "push to open" scheme, with the switch sitting vertically, to take up less board space. 

## Repo Structure
- OreSat.SLDASM  
_The complete assembly of OreSat_
- Backplane  
_The hub which provides power and data to all the boards_
- CardModules  
_Parts/subassemblies for the cameras. (due for renaming)_
- COTS  
_Any Commercial-Off-The-Shelf parts -- screws, connectors, et cetera._
- doc  
_Some of the seldom-changing references. (Refer to the Google drive instead when possible.)_
- Generic  
_Parts/subassemblies for the generic card._
- Hardware  
_(deprecated) still holds some COTS parts which need to be moved and relinked_
- head-tail  
_Cards that pass power and data to the endcap boads on the +/-Z faces._
- Inhibit  
_The card that turns off the satellite while in the peapod. (likely to become the battery card)_
- Keepout  
_Solids for quickly checking if we conform to the CDS, by checking for interferences._
- Rack  
_The required CDS rails and the 'rack mount' panels -- the actual structure, per se_
- Solar  
_Solar panel boards
- Zneg  
_The feet of the unicorn: the turnstile antenna and its board._
- Zpos  
_The horn of the unicorn: the helical antenna and its board._

## Drawings
- [generic board](/Generic/Generic_board.pdf): reference drawings of a genericised board. **ECEs should use this as a reference when designing their boards.**
- [backplane board](/Backplane/Backplane_board.PDF): reference drawings of the backplane which connects the boards.

## Terminology
These are just some terms that are relevant to the structure, non-obvious to an MME, or non-standard.  
- The X and Z axes are aligned to the features described below, and the Y axis is oriented to obey the right hand rule. The axes of the top-level assembly follow this convention. This convention matches that of our launch provider.
- A _board_ is any PCB.
- A _card_ a board that slides into the rack structure of the satellite.
- An _endcap_ is a board that is screwed onto one of the +/-Z faces.
- _Rack_ and _structure_ both refer to the assembly of aluminum frames to which all the boards mount.
- The _sides_ are the +/-Y components of the rack. They have the slots that the cards slide into.
- The _turnstile_ antenna is the four-pronged antenna on the -Z face of the satellite. It provides an omnidirectional, low-data-rate signal to the ground.
- The _helical_ or _high gain_ antenna is the curly, single-pronged antenna on the +Z face of the satellite. It's the narrow-beam, high-data-rate antenna the satellite uses for transmitting video.
- The _backplane_ is the long board that sits on the -X face of the satellite. It transfers power, data, and RF between the boards.


[reaction wheels]: https://github.com/oresat/reaction-wheels
[hangout]: http://www.psas.pdx.edu/hangout
[issues]: https://github.com/oresat/oresat-structure/issues
[contrib]: https://github.com/oresat/oresat-structure/blob/master/.github/CONTRIBUTING.md
[]: 
[]: 
[]: 
