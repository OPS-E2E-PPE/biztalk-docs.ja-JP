---
title: "手順 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fde018d8-9d9a-42ea-8ee9-e3632450b9d7
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d27a186cffc86a79f0a40f73cc6a0c1791c3b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-the-request-message-for-insert-operation-on-purchaseorder-table"></a>手順 1: Purchase_Order テーブルに対する挿入操作の要求メッセージを作成します。
![4 のステップ 1](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-1of4.gif "Step_1of4")  
  
 **所要時間:** 10 分  
  
 **目標:** c# クラス ライブラリ プロジェクトをソリューションでは、追加します。 このライブラリに挿入操作のため、メモリ内の要求メッセージを作成する、 **Purchase_Order**テーブル。 以降のステップでは、オーケストレーションは、テーブルにレコードを挿入する SQL Server にこのメッセージを送信します。  
  
## <a name="prerequisites"></a>前提条件  
 内の手順を完了する必要があります[レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行して](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)です。  
  
### <a name="to-create-a-request-message-for-insert-operation"></a>挿入操作の要求メッセージを作成するには  
  
1.  Visual c# クラス ライブラリ プロジェクトをソリューションに追加します。 プロジェクトの名前を入力`UpdatePOMessageCreator`です。  
  
2.  名前を変更**Class1.cs**に**UpdatePOMessageCreator.cs**です。  
  
3.  .Cs ファイルに次のコードをコピーします。  
  
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
  
     このコード スニペットの挿入操作の要求メッセージが必要ですが、 **Purchase_Order** C:\TestLocation\CreatePOMessage に存在するテーブル。 コードでは、要求メッセージを使用して、実行時に、同様の要求メッセージを作成します。  
  
4.  厳密な名前キー ファイルをプロジェクトに追加します。 厳密な名前キー ファイルを作成する方法の詳細については、次を参照してください。 [SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)です。  
  
    1.  ソリューション エクスプ ローラーで右クリックし、 **UpdatePOMessageCreator**プロジェクトし、クリックして**プロパティ**です。  
  
    2.  **プロパティ**ウィンドウで、をクリックして**署名**です。  
  
    3.  **署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンします。  
  
    4.  **厳密な名前キー ファイルを選択して**一覧で、クリックして**\<参照 >**です。  
  
    5.  厳密な名前のキー ファイルを作成したフォルダーに移動し、をクリックして**開く**です。  
  
    6.  をクリックして**保存**上、**標準**メニュー バーです。 閉じる、**プロパティ**ウィンドウです。  
  
5.  プロジェクトをビルドする。 プロジェクトを右クリックし、をクリックして**ビルド**です。  
  
6.  このプロジェクトの参照をソリューション内の BizTalk プロジェクトに追加します。  
  
    1.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを展開しを右クリックして**参照**、クリックして**参照の追加**です。  
  
    2.  **参照の追加**ダイアログ ボックスで、をクリックして、**プロジェクト**タブです。  
  
    3.  、プロジェクト名の一覧から選択**UpdatePOMessageCreator**、 をクリックして**追加**、をクリックし、 **OK**です。  
  
7.  プロジェクトをビルドすると、プロジェクトの \bin\Debug フォルダーの下アセンブリ DLL が作成されます。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。  
  
    1.  Visual Studio コマンド プロンプトを起動します。  
  
    2.  コマンド プロンプトからの \bin\Debug\ フォルダーに移動、 **UpdatePOMessageCreator**プロジェクト。  
  
    3.  コマンド プロンプトで次のコマンドを実行します。  
  
        ```  
        gacutil /i UpdatePOMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、実行時に要求メッセージを作成する UpdatePOMessageCreator クラス ライブラリ プロジェクトを追加しました。 BizTalk プロジェクトでこのプロジェクトへの参照を追加しても、GAC にアセンブリ DLL を追加します。  
  
## <a name="next-steps"></a>次の手順  
 挿入操作の要求メッセージに UPDATE_EMPLOYEE ストアド プロシージャの応答メッセージをマップする**Purchaser_Order**テーブル。  
  
## <a name="see-also"></a>参照  
 [手順 2: マップ操作の要求メッセージを挿入する UPDATE_EMPLOYEE 応答メッセージ](../../adapters-and-accelerators/adapter-sql/step-2-map-update_employee-response-to-insert-operation-request.md)   
 [レッスン 4: Purchase Order テーブルで挿入操作を実行します。](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)