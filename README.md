```
import random
a=[]
while len(a)<7:
    random.seed()
    x=random.randint(1,48)
    for i in a:
        if i==x:
            break
    a+=[x]
print("這一期的樂透彩開獎號碼為以下:",a)
p=0
for m in range(len(a)):
     for n in range(m):
          if a[m]==a[n]:
                p=1  
                break
          if p==1:
                break
while p==0:
    b=list(map(int,input("請輸入對獎號碼並以空格區隔開:").split(' ')))
    if len(b)!=len(a):
        print("對獎號碼個數應與開獎號碼個數相同")
        break
    p=0
    for m in range(len(b)):
        for n in range(m):
            if b[n]==b[m]:
                print("請勿輸入重複號碼")
                p=1
                break
        if p==1:
            break
    if p==1:
        break
    star=0
    for m in range(len(a)):
        if b[m] in a:
            star+=1
    if star==len(a):
        print("恭喜您號碼全中!!!")
    else:
        print("您中了",star,"個號碼")
```
