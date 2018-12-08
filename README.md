---------fcfs------------------------
bt=[]     #bt stands for burst time
procees=[]     #prorcess stands for procees no like p1 p2 p3
arrival=[]     #arrival stands for arrival time of process
finish=[]     #finish stands for finsish time of proceesees
start=[]     #start stands for start time for processes
runtime=[]    #runtime stands for runtime of the processes
wt=[]    #wt stands for waiting time
avgwt=0  #average of waiting time
tat=[]    #tat stands for turnaround time
avgtat=0   #average of total turnaround time
print("Enter the number of process:\n ")
n=int(input())
for i in range(0,n):
 procees.insert(i,i+1)
print("Enter the burst time of the processes: \n")
bt=list(map(int, input().split()))
print("Enter the arrival time of the processes: \n")
arrival=list(map(int, input().split()))
for i in range(0,len(bt)-1):  #applying sorting to sort process according to their arrival
 for j in range(i,len(procees),1):
  if(arrival[i]>arrival[j]):
   temp=arrival[j]
   arrival[j]=arrival[i]
   arrival[i]=temp

   temp = bt[j]
   bt[j] = bt[i]
   bt[i] = temp

   temp = procees[j]
   procees[j] = procees[i]
   procees[i] = temp

i=0
runTIme=0
while True:
    if(i>=len(bt)):
        break
    if(arrival[i]<=runTIme):
         start.append(runTIme)
         runTIme=runTIme+bt[i]
         finish.append(runTIme)
         i=i+1
    else:
        runTIme=runTIme+1
for i in range(len(start)):
    tat.append(finish[i]-arrival[i])
    wt.append(start[i]-arrival[i])

for i in range(len(start)):
    avgwt = avgwt + tat[i]
    avgtat = avgtat + wt[i]

avgwt=float(avgwt)/n
avgtat=float(avgtat)/n

print("\n")
print("Process\t  Burst Time\t  Waiting Time\t  Turn Around Time")
for i in range(0,n):
 print(str(procees[i])+"\t\t\t"+str(bt[i])+"\t\t\t\t"+str(wt[i])+"\t\t\t\t"+str(tat[i]))
 print("\n")
print("Average Waiting time is: "+str(avgwt))
print("Average Turn Arount Time is: "+str(avgtat))


---------pirottiy-----------------
bt=[]     #bt stands for burst time
p=[]
procees=[]     #prorcess stands for procees no like p1 p2 p3
arrival=[]     #arrival stands for arrival time of process
finish=[]     #finish stands for finsish time of proceesees
start=[]     #start stands for start time for processes
runtime=[]    #runtime stands for runtime of the processes
wt=[]    #wt stands for waiting time
avgwt=0  #average of waiting time
tat=[]    #tat stands for turnaround time
avgtat=0   #average of total turnaround time
print("Enter the number of process:\n ")
n=int(input())
for i in range(0,n):
 procees.insert(i,i+1)
print("Enter the burst time of the processes: \n")
bt=list(map(int, input().split()))
print("Enter the arrival time of the processes: \n")
arrival=list(map(int, input().split()))
print("Enter the  piority of the processes: \n")
p=list(map(int, input().split()))
for i in range(0,len(bt)-1):  #applying sorting to sort process according to their arrival
 for j in range(i,len(procees),1):
  if(arrival[i]>arrival[j]):
    temp=arrival[j]
    arrival[j]=arrival[i]
    arrival[i]=temp

    temp = bt[j]
    bt[j] = bt[i]
    bt[i] = temp

    temp = procees[j]
    procees[j] = procees[i]
    procees[i] = temp

    temp = p[j]
    p[j] = p[i]
    p[i] = temp


  elif(arrival[i]==arrival[j]):
      if(p[j]>p[i]):
          temp = arrival[j]
          arrival[j] = arrival[i]
          arrival[i] = temp

          temp = bt[j]
          bt[j] = bt[i]
          bt[i] = temp

          temp = procees[j]
          procees[j] = procees[i]
          procees[i] = temp

          temp = p[j]
          p[j] = p[i]
          p[i] = temp
      elif(p[i]==p[j]):
          if(procees[j]<procees[i]):
              temp = arrival[j]
              arrival[j] = arrival[i]
              arrival[i] = temp

              temp = bt[j]
              bt[j] = bt[i]
              bt[i] = temp

              temp = procees[j]
              procees[j] = procees[i]
              procees[i] = temp

              temp = p[j]
              p[j] = p[i]
              p[i] = temp





i=0
runTIme=0
while True:
    if(i>=len(bt)):
        break
    if (arrival[i] <= runTIme):
        for j in range(i+1, len(procees), 1):
            if(arrival[j]<=runTIme):
                if(p[j]<p[i]):
                    temp = arrival[j]
                    arrival[j] = arrival[i]
                    arrival[i] = temp

                    temp = bt[j]
                    bt[j] = bt[i]
                    bt[i] = temp

                    temp = procees[j]
                    procees[j] = procees[i]
                    procees[i] = temp

                    temp = p[j]
                    p[j] = p[i]
                    p[i] = temp



        start.append(runTIme)
        runTIme = runTIme + bt[i]
        finish.append(runTIme)
        i = i + 1
    else:
        runTIme = runTIme + 1

for i in range(len(start)):
    tat.append(finish[i]-arrival[i])
    wt.append(start[i]-arrival[i])

for i in range(len(start)):
    avgwt = avgwt + tat[i]
    avgtat = avgtat + wt[i]

avgwt=float(avgwt)/n
avgtat=float(avgtat)/n

print("\n")
print("Process\t  Burst Time\t  Waiting Time\t  Turn Around Time\t  Pirority")
for i in range(0,n):
 print(str(procees[i])+"\t\t\t"+str(bt[i])+"\t\t\t\t"+str(wt[i])+"\t\t\t\t"+str(tat[i])+"\t\t\t\t"+str(p[i]))
 print("\n")
print("Average Waiting time is: "+str(avgwt))
print("Average Turn Arount Time is: "+str(avgtat))
------------------------sjf----------------------------------------
bt=[]     #bt stands for burst time

procees=[]     #prorcess stands for procees no like p1 p2 p3
arrival=[]     #arrival stands for arrival time of process
finish=[]     #finish stands for finsish time of proceesees
start=[]     #start stands for start time for processes
runtime=[]    #runtime stands for runtime of the processes
wt=[]    #wt stands for waiting time
avgwt=0  #average of waiting time
tat=[]    #tat stands for turnaround time
avgtat=0   #average of total turnaround time
print("Enter the number of process:\n ")
n=int(input())
for i in range(0,n):
 procees.insert(i,i+1)
print("Enter the burst time of the processes: \n")
bt=list(map(int, input().split()))
print("Enter the arrival time of the processes: \n")
arrival=list(map(int, input().split()))

for i in range(0,len(bt)-1):  #applying sorting to sort process according to their arrival
 for j in range(i,len(procees),1):
  if(arrival[i]>arrival[j]):
    temp=arrival[j]
    arrival[j]=arrival[i]
    arrival[i]=temp

    temp = bt[j]
    bt[j] = bt[i]
    bt[i] = temp

    temp = procees[j]
    procees[j] = procees[i]
    procees[i] = temp




i=0
runTIme=0
while True:
    if(i>=len(bt)):
        break
    if (arrival[i] <= runTIme):
        for j in range(i+1, len(procees), 1):
            if(arrival[j]<=runTIme):
                if(bt[j]<bt[i]):
                    temp = arrival[j]
                    arrival[j] = arrival[i]
                    arrival[i] = temp

                    temp = bt[j]
                    bt[j] = bt[i]
                    bt[i] = temp

                    temp = procees[j]
                    procees[j] = procees[i]
                    procees[i] = temp



        start.append(runTIme)
        runTIme = runTIme + bt[i]
        finish.append(runTIme)
        i = i + 1
    else:
        runTIme = runTIme + 1

for i in range(len(start)):
    tat.append(finish[i]-arrival[i])
    wt.append(start[i]-arrival[i])

for i in range(len(start)):
    avgwt = avgwt + tat[i]
    avgtat = avgtat + wt[i]

avgwt=float(avgwt)/n
avgtat=float(avgtat)/n

print("\n")
print("Process\t  Burst Time\t  Waiting Time\t  Turn Around Time")
for i in range(0,n):
 print(str(procees[i])+"\t\t\t"+str(bt[i])+"\t\t\t\t"+str(wt[i])+"\t\t\t\t"+str(tat[i]))
 print("\n")
print("Average Waiting time is: "+str(avgwt))
print("Average Turn Arount Time is: "+str(avgtat))
