LS
===

> we found this [binary](ls) and captured some [traffic](ls.pcap)...

## Write-up

I started off with inspecting the captured traffic which looked like a tcp connection to 188.40.18.94 sending some binary data back and forth. I couldn't really make anything from it.

So off to the binary. Looking at the main function in IDA we immediatly see two branches. 

![2 branches](screenshot1.png)

If the environment variable "HAX" exists the program executes sub_405BD0("188.40.18.94", 1024) which seems like setting up a connection to the ip also found in the pcap.

