# ObjectC_property
帶參屬性存取和讀寫

屬性的意義是讓開發者存取和操作個體變數方式更加直觀與方便的方式。

宣告方式

           @property 類型 執行個體變數名稱;
           //只要經過此符號修飾的成員變數
           //則作用在類別以外的程式需要存取執行個體變數時
           //可以透過屬性來存取
         
有屬性等於間接完成設定值的方法如下

           -(type) p;
           -(void) setP: (type) 資料來源

實現方式

           @synthesize 執行個體變數名稱;
           // 合成的意思
           
    
實作範例

QQQ.h

           #import <Foundation/Foundation.h>
           
           @interface QQQ: NSObject
           {
           
               int p;
           
           }
           
           @property int p;
           
           -(void)printP;

QQQ.m
具體化標頭檔的介面
實現其屬性
實作其方法

          #import <QQQ.h>
          @implementation
          
          @synthesize p;
          
          -(void)printP
          {
             NSlog(@"%i",p);
          }
          
          @end

main.m
注入標頭檔
此標頭檔已經被具體化了

         #import <Foundation/Foundation.h>
         #import "QQQ.h"
         
         int main(int argc, const * argv[])
         {
           
           QQQ *p=[[QQQ alloc]init];
           [p setP: 1]; //setter 
           [p printP];
                      
              return 0;     
         
         }

# 帶參屬性

getter 為存取器; setter 為設定器，在別的語言這稱為存取子，也稱為『記憶體函數』，實際上就是提供外界了取得執行個體變數和設定執行個體變數的方法，所有等級的執行個體變數都能被存取到。

聲明方式

         -(void) setVarName: paramType paramConstName;
         // 傳回值為 void ，這和 js 的表現方式相反

