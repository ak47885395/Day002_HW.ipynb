# Day002_HW.ipynb
# Comparasion between file I/O and CSV Reader
file I/O  讀出來是一堆用逗號分隔的字串  而  CSV Reader 是好幾個list組成的list
# 1. 取出班次一的每一個時間
import csv
with open("./Data/example.csv",newline="",encoding='utf8') as csvfile:
    text = csv.reader(csvfile)
    for x in text:
          print(x[5])   
# 2. 將班次一的每一個時間用一種資料型態保存  
import csv
with open("./Data/example.csv",newline="",encoding='utf8') as csvfile:
    thislist=[]
    text = csv.reader(csvfile)
    for x in text: 
        thislist.append(x[5])  
first_order_list=list(thislist) 
print(first_order_list)
# 3. 將班次一到五與其所有時間用一種資料型態個別保存
import csv  
with open("./Data/example.csv",newline='',encoding='utf8') as csvfile :
    text=csv.reader(csvfile)
    thislist=list(text)
    #print(len(thislist))  #0 to 76 the first row is equal to thistlist[0]
    #print(thislist[0][0])   #[0][0]  to [76][16]
    for i in range(5 , 10):  
        for j in range(len(thislist)):
            print(thislist[j][i])
