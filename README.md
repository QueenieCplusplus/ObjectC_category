# ObjectC_category
分類在物件導向C的功能是在已有類別上，對類別進行擴充。

宣告分類

             @interface classname (cetegory name)
             
                // 聲明方法
                // 不允許新增變數
               
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



