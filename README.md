# thread-safe-counter
Compiled in Linux






#result of mutex
#@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

#main: begin [counter = 0]
#A: begin
#B: begin
#A: done
#B: done
#main: done [counter: 2000000] [should be: 2000000]

#real	0m0.129s
#user	0m0.195s
#sys	0m0.056s

#@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@


#result of semaphore
#@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@

#main: begin [counter = 0]
#A: begin
#B: begin
#B: done
#A: done
#main: done [counter: 2000000] [should be: 2000000]

#real	0m5.326s
#user	0m2.230s
#sys	0m5.774s

#@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@


#Mutex is more faster than Semaphore.
#Mutex allows only process or thread to access critical section.
#So,Mutex just locks and unlocks while access to critical section.
#But Semaphore allows multiple access depend on semid value.
#So, when they access to critical section they should check semid value and change semid value by using function. #It makes more code lines.
#This is why Semaphore takes more time than Mutex.
