GNU Make is program that is commonly used to build other programs. When you run make, GNU Make
looks in your current directory for a file named Makefile and executes the commands inside, according
to the makefile language.


Makefile
task_one:
  echo 1
task_two: task_one
  echo 2
  
make task_two
make clean
