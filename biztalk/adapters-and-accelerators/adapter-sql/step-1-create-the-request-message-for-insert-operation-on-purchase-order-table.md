---
title: 手順 1:Purchase_Order テーブルに対する挿入操作の要求メッセージを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fde018d8-9d9a-42ea-8ee9-e3632450b9d7
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ef474e20b44d319ca4ac1d764dfa46b3062231
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367808"
---
# <a name="step-1-create-the-request-message-for-insert-operation-on-purchaseorder-table"></a>手順 1:Purchase_Order テーブルに対する挿入操作の要求メッセージを作成します。
![手順 4 の 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順で追加、C#をソリューションにクラス ライブラリ プロジェクト。 このライブラリで挿入操作のメモリ内の要求メッセージを作成する、 **Purchase_Order**テーブル。 後の手順では、オーケストレーションは、このメッセージをテーブルにレコードを挿入する SQL Server に送信します。  
  
## <a name="prerequisites"></a>前提条件  
 」の手順を完了する必要があります[レッスン 3。追加された新しい従業員を選択するストアド プロシージャの実行](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)します。  
  
### <a name="to-create-a-request-message-for-insert-operation"></a>挿入操作の要求メッセージを作成するには  
  
1.  ビジュアルの追加C#をソリューションにクラス ライブラリ プロジェクト。 プロジェクトの名前を入力`UpdatePOMessageCreator`します。  
  
2.  名前を変更**Class1.cs**に**UpdatePOMessageCreator.cs**します。  
  
3.  次のコードを .cs ファイルにコピーします。  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdatePOMessageCreator  
    {  
        public class UpdatePOMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreatePOMessage";  
                try  
                {  
                    ResponseDoc = (Directory.GetFiles(XmlFileLocation, "*.xml", SearchOption.TopDirectoryOnly))[0];  
                }  
                catch (Exception ex)  
                {  
                    Console.WriteLine("Trying to get XML from: " + XmlFileLocation);  
                    Console.WriteLine("EXCEPTION: " + ex.ToString());  
                    throw ex;  
                }  
  
                //Create Message From XML  
                Message = new XmlDocument();  
  
                Message.PreserveWhitespace = true;  
  
                Message.Load(ResponseDoc);  
  
                return Message;  
            }  
        }  
    }  
  
    ```  
  
     このコード スニペットには、挿入操作の要求メッセージでが必要ですが、 **Purchase_Order** C:\TestLocation\CreatePOMessage に存在するテーブル。 コードでは、要求メッセージを使用して、実行時に同様の要求メッセージを作成します。  
  
4.  厳密な名前キー ファイルをプロジェクトに追加します。 厳密な名前キー ファイルを作成する手順については、次を参照してください。 [SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)します。  
  
    1.  ソリューション エクスプ ローラーで右クリックし、 **UpdatePOMessageCreator**プロジェクトし、クリックして**プロパティ**します。  
  
    2.  **プロパティ**ウィンドウで、をクリックして**署名**します。  
  
    3.  **署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンします。  
  
    4.  **厳密な名前キー ファイルを選択して**一覧で、 **\<参照\>** します。  
  
    5.  厳密な名前キー ファイルを作成したフォルダーに移動し、をクリックし、**オープン**します。  
  
    6.  クリックして**保存**上、**標準**メニュー バー。 閉じる、**プロパティ**ウィンドウ。  
  
5.  プロジェクトをビルドする。 プロジェクトを右クリックし、をクリックして**ビルド**します。  
  
6.  ソリューション内の BizTalk プロジェクトには、このプロジェクトの参照を追加します。  
  
    1.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを展開し、右クリックして**参照**、 をクリックし、**参照の追加**します。  
  
    2.  **参照の追加**ダイアログ ボックスで、をクリックして、**プロジェクト**タブ。  
  
    3.  プロジェクト名のリストから選択**UpdatePOMessageCreator**、 をクリックして**追加**、順にクリックします**OK**します。  
  
7.  プロジェクトをビルドして、プロジェクトの \bin\Debug フォルダーの下に、アセンブリ DLL を作成します。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。  
  
    1.  Visual Studio コマンド プロンプトを起動します。  
  
    2.  コマンド プロンプトからの \bin\Debug\ フォルダーに移動、 **UpdatePOMessageCreator**プロジェクト。  
  
    3.  コマンド プロンプトで次のコマンドを実行します。  
  
        ```  
        gacutil /i UpdatePOMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順で実行時に要求メッセージを作成する UpdatePOMessageCreator クラス ライブラリ プロジェクトを追加しました。 BizTalk プロジェクトでこのプロジェクトへの参照を追加し、またアセンブリ DLL を GAC に追加します。  
  
## <a name="next-steps"></a>次の手順  
 上の応答メッセージの挿入操作の要求メッセージに UPDATE_EMPLOYEE ストアド プロシージャをマップする**Purchaser_Order**テーブル。  
  
## <a name="see-also"></a>参照  
 [手順 2:操作要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージをマップします。](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [レッスン 4:注文テーブルに対して挿入操作を実行する](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)