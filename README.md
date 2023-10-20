import xml.etree.ElementTree as ET #該如何讀取xml檔案#匯入程式庫

def comound_intrest(x,s,y):
    total = 0 #計算複利
    for i in range(y):
        totla = (total + x)
        totla = total*(1+s/100)
    return total

tree = ET.parse("setting,xml")#讀取setting.xml的檔案
root = tree.getroot()#建立樹結構

data_dict = {}
for element in root:
    key = element.tag#讀取tg:x,s,y
    value = element.text#讀取裡面的文字:10000、10、20(被tag薄夾的文字)
    data_dict[key] = value#把資料存到python裡的字典處理

#打印字典
print(data_dict)
x = int(data_dict['x'])#讀取值
s = int(data_dict['s'])
y = int(data_dict['y'])

print(comound_intrest(x,s,y)) #輸出結果
#將結果存於記事本

#打開記事本檔案
file = open("result.txt","w", encoding = "utf-8")
#"result.txt" == 檔案名稱
#"w" == WRITE寫入
#emcoding == 文字編碼 繁體用"utf-8" 簡體"big-5"
file.write("本金:"+str(x)+"\n")
file.write("年利率:"+str(s)"\n")
file.write("投資年分:"+str(y)"\n")
file.write("-------以下是你可以得到的總金額-------\n")
file.write(str(int(comound_intrest(x,s,y)))+"元")
file.close()

