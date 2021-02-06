# Question.py
#A version of the number guessing game. Program guesses user's number. 
def Search(low, high):
  num_guess = 0     
  while low <= high:  
    m = (low+high)//2
    
    print("Is your number Less than, Greater than, or Equal to", str(m)+ "?")

    x = input("Type 'L', 'G' or 'E': ")
    print()
    
    #while loop checks if input matches L G E  
    while x not in ["L", "l" , "G", "g", "E", "e"]: 
    #better than writing: 
    #        x!= 'L' and x != 'l' and x != 'G' and 'x' != 'g' and x != 'E' and x != 'e':
      x = input("Please type 'L', 'G' or 'E': ")
      print()
    #end while
    
    if x in ["L", "l", "G", "g", "E", "e"]:
      num_guess += 1
    
    #if-if-else-elif  
    if x == 'E' or x == 'e':
      if num_guess == 1:
        print("I found your number in 1 guess.\n")
        print() 
      else: 
        print("I found your number in "+str(num_guess),"guesses.\n")
        print()        
      break 
    elif x == 'G' or x== 'g':
      low = m + 1
    elif x == 'L' or x=='l':
      high = m -1
    #end if-if-else-elif 
    
    #if 
    if low == high: 
      if num_guess == 1:
        print("Your number is", str(high)+". I found it in 1 guess.\n")
        print()
      else:
        print("Your number is", str(high)+". I found it in", str(num_guess)+" guesses.\n")
        print()
     # print(low, high)
      break
    #end if 
  #end while 
  #if inconsistent
  if high < low:
    print("Your answers have not been consistent.\n")
    print()
  #end if 
  


    
#-------------------main program------------------------------------------------
print("\n")

print("Enter two numbers, low then high.")

low = int(input("low = ")) 
high = int(input("high = ")) 

print()

#while
while high < low: 
  print("Please enter the smaller followed by the larger number.")
  low = int(input("low = "))
  high = int(input("high = "))
  print()
  
#end while


print("Think of a number in the range", str(low), "to",str(high)+".")
print()

#if 
if low == high: 
  print("Your number is", str(high)+". I found it in 0 guesses.\n")
  print()
else:
  Search(low, high) 
#end  if-else  
 
