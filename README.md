Pseudo-device-driver-named--string--for-FreeBSD-OS
==================================================

The pseudo-device for which the driver has been written is called string. This is a very simple device which, when read (2), returns a string stored inside the device. 
Also it can be written to with the help of write (2) or any other utility. The device accepts maximum 50 bytes worth of data.

It only allows one process to have it open (for either reading or writing) at a time. If another process, even if that process is owned by root, tries to open the device that will be an error.
While writing to the device it is assumed that all the data that has to be written to the device gets written at the same time i.e. only one uio structure.

An IOCTL has been added to the device driver which toggles the mode of the device between normal mode and upper-case-only mode. When in upper-case-only-mode the device will return the contents in upper case when read (2) is executed
