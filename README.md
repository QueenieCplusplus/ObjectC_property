# ObjectC_property
帶參屬性存取和讀寫

屬性的意義是讓開發者存取和操作個體變數方式更加直觀與方便的方式。

宣告方式

           @property 類型 執行個體變數名稱;
           //只要經過此符號修飾的成員變數
           //則作用在類別以外的程式需要存取執行個體變數時
           //可以透過屬性來存取

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
           
         
         
         }
