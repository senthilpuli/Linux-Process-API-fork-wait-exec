# Linux-Process-API-fork-wait-exec-
Ex02-Linux Process API-fork(), wait(), exec()
# Ex02-OS-Linux-Process API - fork(), wait(), exec()
Operating systems Lab exercise


# AIM:
To write C Program that uses Linux Process API - fork(), wait(), exec()

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Write the C Program using Linux Process API - fork(), wait(), exec()

### Step 3:

Test the C Program for the desired output. 

# PROGRAM:

## C Program to print process ID and parent Process ID using Linux API system calls
```
#include <stdio.h>
#include <sys/types.h>
#include <unistd.h>
int main(void)
{	//variable to store calling function's process id
	pid_t process_id;
	//variable to store parent function's process id
	pid_t p_process_id;
	//getpid() - will return process id of calling function
	process_id = getpid();
	//getppid() - will return process id of parent function
	p_process_id = getppid();
	//printing the process ids

//printing the process ids
	printf("The process id: %d\n",process_id);
	printf("The process id of parent function: %d\n",p_process_id);
	return 0; }
```
# Output
![Screenshot 2024-03-08 134110](https://github.com/gowriganeshns/Linux-Process-API-fork-wait-exec/assets/121471306/59215fdd-9789-4ff7-acbc-f2390d11b01d)

## C Program to create new process using Linux API system calls fork() and exit()
```
#include <stdlib.h>

#include <sys/wait.h>
#include<stdio.h>
#include<unistd.h>
#include <sys/types.h>
int main()
{ int pid; 
pid=fork(); 
if(pid == 0) 
{ printf("Iam child my pid is %d\n",getpid()); 
printf("My parent pid is:%d\n",getppid()); 
exit(0); } 
else{ 
printf("I am parent, my pid is %d\n",getpid()); 
sleep(100); 
exit(0);} 
}
```
# Output
![Screenshot 2024-03-08 134137](https://github.com/gowriganeshns/Linux-Process-API-fork-wait-exec/assets/121471306/2f76e8f0-815f-48d7-b116-384302532208)

## C Program to execute Linux system commands using Linux API system calls exec() family
```
#include <stdlib.h>

#include <sys/wait.h>
#include<stdio.h>
#include<unistd.h>
#include <sys/types.h>
int main()
{       int status;
        printf("Running ps with execlp\n");
        execl("ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
printf("Running ps with execlp. Now with path specified\n");
        execl("/bin/ps", "ps", "ax", NULL);
        wait(&status);
        if (WIFEXITED(status))
                printf("child exited with status of %d\n", WEXITSTATUS(status));
        else
                puts("child did not exit successfully\n");
        printf("Done.\n");
        exit(0);}
```
# Output
![Screenshot 2024-03-08 134228](https://github.com/gowriganeshns/Linux-Process-API-fork-wait-exec/assets/121471306/b31c63ff-f20e-42b0-aad0-09ddb4b8a8d3)
![Screenshot 2024-03-08 134245](https://github.com/gowriganeshns/Linux-Process-API-fork-wait-exec/assets/121471306/6320f945-a3d0-42ff-9c93-854b3c12987b)
![Screenshot 2024-03-08 134310](https://github.com/gowriganeshns/Linux-Process-API-fork-wait-exec/assets/121471306/c67ef524-7e8e-4334-83e6-0ac3d77f85d3)
![Screenshot 2024-03-08 134328](https://github.com/gowriganeshns/Linux-Process-API-fork-wait-exec/assets/121471306/cd78f710-5b49-46e7-9d03-e6eb8d5325fb)
![Screenshot 2024-03-08 134352](https://github.com/gowriganeshns/Linux-Process-API-fork-wait-exec/assets/121471306/196cf4d7-bac5-43be-8fb2-f6595ace4ac5)



# RESULT:
Thus , the C Program that uses Linux Process API - fork(), wait(), exec() is Written and Successfully Executed .

