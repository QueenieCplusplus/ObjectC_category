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
             
呼叫分類的實體物件即物件及其方法
//物件是類別的產生實體物件

              [物件名稱 新增方法名稱]
              
              
示意圖


  
