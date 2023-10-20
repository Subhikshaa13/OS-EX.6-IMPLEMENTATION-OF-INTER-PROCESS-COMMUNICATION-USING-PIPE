# OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE

AIM: To implement interprocess communication using pipe command.

ALGORITHM:

Create a child process using fork().
Create a simple pipe with C, we make use of the pipe() system call.
Create two file descriptor fd[0] is set up for reading, fd[1] is set up for writing
Close the read end of parent process using close() and perform write operation
Close the write end of child process and perform reading
Display the text.

PROGRAM:

#include <stdio.h> 

int main() {


int fd[2],child;

char a[10]; 

printf("\nEnter the string : ");

scanf("%s",a);

pipe(fd);

child=fork(); 

if(!child)
  { close(fd[0]); write(fd[1],a,5); wait(0); }

else

{ close(fd[1]); read(fd[0],a,5); printf("The string received from pipe is : %s",a); 


OUTPUT:

![image](https://github.com/Subhikshaa13/OS-EX.6-IMPLEMENTATION-OF-INTER-PROCESS-COMMUNICATION-USING-PIPE/assets/118787344/de3790f4-9ae9-4c9c-9619-737a6e5b3c0d)



RESULT:

Thus the implementation of interprocess communication using pipe command is successfully executed.
