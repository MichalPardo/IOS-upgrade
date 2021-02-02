					### This is a process to follow while upgrading the IOS on switches ###

The process could be applied for switches that are standalone or are working in the cluster\stack.

1. Download requiered version of IOS from Cisco.com
2. Upload the image to a flash storage of Cisco switch.
   - If there is only one switch, upload the file to flash module
   - If there is a stack, upload the image to each flash, etc. flash1, flash2...

To copy initial file use TFTP server. Once this is done copy the image from one flash to other if required.
3. Verify MD5 of uploaded file:
   verify /md5 PATH_TO_A_FILE
4. Change boot image:
   - For standalone switch:
     boot system PATH_TO_A_FILE
   - For switches in the stack:
     boot system switch all PATH_TO_A_FILE
5. Verify the boot options
   show boot
6. Save the configuration
   wr mem
7. Reload the switch
   reload   
8. Verify the current IOS version
   show version
   show boot