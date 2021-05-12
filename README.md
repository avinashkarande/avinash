# avinash

def otp_generator(email):
    length=len(email)
    otp=0
    if length>12:
        otp=otp+10
    if email.endswith((".org",".in")):
        otp=otp+11
    if email[5] in (".", "_"):
        otp=otp+12
    if email[0:2].lower()==email[length-2:length].lower():
        otp=otp+13
    for index in range(0,length):
        if email[index].isdigit():
            otp=otp+index
    if otp==0:
        otp=-1
    return otp
    
email="USgana@a.us"
otp=otp_generator(email)
print(otp)






def otp(email):
     if len(email)>12:
          res=10
          res2 = 10
          if ('.org' in email) or ('.in' in email):
               res += 11
               if (email[5]==',') or (email[5]=='_'):
                    res += 12
                    if email[0:2]==email[len(email)-2:]:
                         res += 13
                         summ = 0
                         for i in email:
                              if i>='0' and i<='9':
                                   summ+=email.index(i)
                         if summ==0:
                              return res2
                         else:
                              res += summ
                              return res
                    else:
                         return res2
               else:
                    return res2
          else:     
               return res2
     elif ('.org' in email)or('.in' in email):
          res = 11
     elif (email[5]==',') or (email[5]=='_'):
          res = 12
     elif email[0:2]==email[len(email)-2:]:
          res = 13
     elif True:
          summ = 0
          for i in email:
               if i>='0' and i<='9':
                    summ+=email.index(i)
          if summ==0:
               res = -1
          else:
               res = summ
     return res

print(otp('robinsingh@abc.com'))
print(otp('tommy@abc.in'))
print(otp('smith_a@a.co'))
print(otp('w123@ty.com'))
print(otp('inest_s23@abc.in'))
print(otp('xy@xyz.co'))

print()




#write a python that accepts input_list1 and input_list2 as parameters 
#and returns a list of numbers as output_list 
#based on the logic below
#[17,23,11,38,12]   [31,13,24,121,17]   [17,23,11,38]
#[25,18,12,11]      [35,625,25,10]      [25]



def num_check(input_list1,input_list2):
    output_list=[]
    
    for i in range(0,len(input_list1)):
        
        #First
        if input_list1[i] in input_list2:
            output_list.append(input_list1[i])
            
        #second
        elif input_list1[i]**2 in input_list2:
            output_list.append(input_list1[i])
            
        #Third
        elif str(input_list1[i])[-1] == str(input_list2[i])[-1]:
            output_list.append(input_list1[i])
            
        #Fourth
        else:
            num=str(input_list1[i])
            
            prod=1
            for n in num:
                prod=prod* int(n)
            if prod in input_list2:
                output_list.append(input_list1[i])
    return output_list
print(num_check([26,17,25,35,39,63],[26,671,11,21,14,28]))






#Eat sleep rave repeat





def fun(N):
    count=0
    count1=0
    count2=0
    v="aeiou"
    
    for i in N:
        if(i.sspace()):
            count1=count1+1
    for i in N:
        if not(i.isalnum() or i.sspace()):
            count=count+1
    for i in v:
        if(i in N):
            count2=count2+1
            
    if not (N[0].isalnum() or N[-1].isalnum()):
        return "A"
    
    elif (N[3].isdigit()):
        return "B"
    
    elif (count==3):
        return"C"
    
    elif(count1==3):
        return "D"
    elif (count2==5):
        return "E"
    else:
        return "X"
print(fun(a))









#password @#&*?
#strength





password="Itz_Me_h1ere@"
strength=10
v="aeiou"
alp="QWERTYUIOPLKJHGFDSAZXCVVBNM"
count=0
count1=0
count2=0
count3=0
for i in password:
    for j in v:
        if(i==j):
            count+=1
for i in password:
    for j in v:
        if(i==j):
            count1=1
            
            
    for i in password:
        if(i in "@#&*?"):
            count1+=1
for i in password:
    for j in alp:
        if(i==j):
            count2+=1
for i in password:
    if(i.isdigit()):
        count3+=1
        
if(count3>=1):
    strength+=3
if(count>=1):
    strength+=2
    
if(count1>=1):
    strength+=2
    
if(count2>=1):
    strength+=3
    
if(len(password)>6):
    strength+=2
else:
    strength-=1
if(strength==10):
    strength="not a good password"
print(strength)








#Given a string  str="I lov3e myself"





str="I lov3e myself"
output=""

def fun (str):
    count=0
    count1=0
    count2=0
    
    a=str.split()
    b=a[1]
    
    for i in str:
        if not (i.isalnum() or i.isspace()):
            count+=1
    for i in b:
        if (i.isdigit()):
            count1+=1
    for i in str:
        if (i in ","):
            count2+=1
    if (count==3):
        return "A"
    elif (count1>=1):
        return "B"
    elif (len(str)>50):
        return "C"
    elif(count2>0):
        return "D"
    elif(str[0].islower()):
        return "E"
    else:
        return "-1"
print(fun(str))
    
    
    
    
    
    
    
    
    
    
    
        
        
        
        







