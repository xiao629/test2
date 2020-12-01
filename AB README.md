import random
ans_num=random.sample('1234567890',4)                   #隨機取數
print(ans_num)
while True: 
    enterNum = input("輸入4個不同數字:")
    z = list(enterNum)                                  #將輸入的數字列表
    a=0
    if len(enterNum)!=len(ans_num):                     #若不是輸入4位數字重新輸入
        print("請輸入4位數字")
        continue
    p=0
    for i in range(len(enterNum)):                      #檢測是否輸入重複的號碼
        for j in range(i):
            if enterNum[j]==enterNum[i]:
                print("數字不得重複")
                p=1
                break
        if p==1:
            break
    else:
        for i in range(4):
            if ans_num[i] is z[i] :                     #答案與輸入的數字做比對
                a=a+1                                   #若位置、數字相同則a+1
        b = 4-len(set(ans_num)-set(z))-a                #(答案-輸入)集合，取長度再得出B值
        print(a,"A", b, "B")
        if a == 4:
            print("恭喜您答對了")
            break
