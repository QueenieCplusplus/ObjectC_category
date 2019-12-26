# ObjectC_category
分類在物件導向C的功能是在已有類別上，對類別進行擴充。

宣告分類

             @interface classname (cetegory name)
             
                // 聲明方法
                // 不允許新增變數
                // 新增的方法名稱不能與類別本身存在的方法名稱一樣
                // 否則會被覆寫
               
             @end
             
定義分類

             @implementation classname (category name)
             
               // 新增定義類別的方法
               // 這些方法可以存取類別的執行個體
             
             @end
             
呼叫類別的實體物件（非分類的）即物件及其方法
//物件是類別的產生實體物件

              [物件名稱 新增方法名稱]
              
              
分類檔案示意圖

                 Category QPK on NSObject
                 QPK 本身不能被具現化
                 必須透過類別名稱如 NSObject
                         |
                         |
               ---------------------
               |                   |
               |                   |
         NSObject+QPK.h       NSObject+QPK.m
         

NSObject+QPK.h

             #import<Foundation/Foundation.h>
             
             @interface NSObject(QPK)
             
             @ end

NSObject+QPK.m

             #import"NSObject+QPK.h"
             
             @implementation NSObject(QPK)
             
             @end

實作範例如下：
以下需要先透過檔包含引入
否則會出現錯誤資訊

QQQ.h
一標頭檔

                #import<Foundation/Foundation.h>
                
                @interface QQQ: NSObject
                {
                
                   int p;
                
                }
                -(void)setP;
                -(void)printP;
                
                @end

QQQ+PPP.h
檔包含標頭檔
宣告分類

                #import<Foundation/Foundation.h>
                #import"QQQ.h"
                
                @interface QQQ(PPP)
                
                -(void)setP;
                
                @end

QQQ+PPP.m
檔包含分類檔
定義分類
                #import"PPP.h"
                
                @implementation QQQ(PPP)
                
                -(void)setP
                {
                
                   p=99;
                
                }
                         
                @end

main.h
生命週期中引入物件

               #import<Foundation/Foundation.h>
               #import"QQQ.h"
               #import"QQQ+PPP.h"
               
               int main()
               {
               
                 QQQ *q=[[QQQ alloc]init];
                 
                 [q setP]; // 以分類方法為優先，原始方法已經被覆寫。
                 
                 [q printP];
                   
               
                 return 0;
               }







