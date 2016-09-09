# 1bitsy for Platform.io 


This requires the 3.0 version of Platform.io. If the About page indicates version 2.x.x, then enable the development version of 3.0 with the following settings from the top menu:

> Platform.io
>> Settings
>>> Platform.io IDE
>>>> Use development version

Platform.io will the update to the newest version

#TODO
- [ ] Need to automatically run make on the `libopencm3` before attempting to build the project
- [X] Still has a linker config issue. Have leads, pretty close to figuring this out methinks. 
	- Useful: http://www.scons.org/doc/production/HTML/scons-user.html
	- http://docs.platformio.org/en/stable/platforms/creating_platform.html
	- https://github.com/platformio/platformio/blob/8a379d2db26ff0deb37be83e82d1abe72e5439f8/platformio/builder/tools/platformio.py#L68
- [ ] Upload
	- [ ] JTAG
	- [ ] SWDIO
	- [ ] Uart?
	- [ ] USB without BMP? 

## Basics of the build system

Most of it is in `builder/main.py`. For the most part, everything is just setting up flags, which are appropriately named. 

The "build recipes" start ~L#121 at `BUILDERS=dict(...`. These very closely match the Makefile for the system. 
	
Conspicuously missing is any sort of a .map file at this time. 

Upload stuff is currently left in from the stock STM32 project, pending the build process working right. 