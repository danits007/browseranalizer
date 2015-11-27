# browseranalizer

import time


#lista=[]

#line=fd.readline()



#while (True):

fd=open('/var/log/apache2/access.log', 'ro')
lines = fd.read().splitlines()
moz = 0
chro = 0
op = 0
saf = 0
cur = 0
total = 0
percmoz = 0
percgc = 0
percop = 0
percsaf = 0
perccur = 0

for l in lines:
    if "Mozilla" in l:
        moz += 1
        total += 1
    elif "Chrome" in l:
        chro += 1
        total += 1
    elif "Opera" in l:
        op += 1
        total += 1
    elif "Safari" in l:
        saf += 1
        total += 1
    elif "curl" in l:
        cur += 1
        total += 1
    print l
    percmoz = (100.0*moz)/total
    percgc = (100.0*chro)/total
    percop = (100.0*op)/total
    percsaf = (100.0*saf)/total
    perccur = (100.0*cur)/total
    print

    #time.sleep()
print "Acessos pelo navegador Mozilla: " + str(moz) + "(" + str(percmoz) + "%" + ")"
print "Acessos pelo navegador Chrome: " + str(chro) + "(" + str(percgc) + "%" + ")"
print "Acessos pelo navegador Opera: " + str(op) + "(" + str(percop) + "%" + ")"
print "Acessos pelo navegador Safari: " + str(saf) + "(" + str(percsaf) + "%" + ")"
print "Acessos pelo navegador culr: " + str(cur) + "(" + str(perccur) + "%" + ")"
