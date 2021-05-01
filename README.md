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








