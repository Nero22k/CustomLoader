# Noname shellcode loader (Decent)

### AV Results (ESET BITCH :P) :
![image](https://antiscan.me/images/result/hbOqC5hKgASP.png)

# Demo:
(https://www.youtube.com/watch?v=YwRyDRSezJg)

# HOW DOES IT WORK:
 * shellcode is encrypted with AES algorithm 
 * The binary first runs checks to see if its inside a VM, attach to debugger or monitored by sysmon
 * Then it sleeps for 1 minute after running checks it will sleep for another 1 min 20 sec before decrypting and looks for target process (SearchHostProtocol.exe)
 * Then it will inject shellcode into the target process. If the target process does not exist it will try to inject into (smartscreen.exe). If that does not exist it will exit and remove it self.
 * The binary resolves API functions dynamicly which effectively hides them from showing up in import table
 * The functions are also encrypted and decrypted on run time to get rid of strings 
 * Then the binary will delete it self from disk living no trace (KAPPA!)
