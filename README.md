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



