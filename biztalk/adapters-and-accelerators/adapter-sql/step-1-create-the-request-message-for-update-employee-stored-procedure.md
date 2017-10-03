---
title: "手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4dd975d9-4b38-46e0-a926-4b325b0d7b5e
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be63a18df71a91bebffeb1fccfe46395fdb36b0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-1-create-the-request-message-for-updateemployee-stored-procedure"></a>手順 1: UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ
![2 の手順 1.](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **所要時間:** 10 分  
  
 **目標:** c# クラス ライブラリ プロジェクトをソリューションでは、追加します。 このライブラリのメモリ内の要求メッセージを作成する、 **UPDATE_EMPLOYEE**ストアド プロシージャです。 以降のステップでは、オーケストレーションは、ストアド プロシージャを実行する SQL Server にこのメッセージを送信します。  
  
## <a name="prerequisites"></a>前提条件  
 内の手順を完了する必要があります[レッスン 2: 受信とフィルター通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)です。  
  
### <a name="to-create-a-request-message-for-updateemployee-stored-procedure"></a>UPDATE_EMPLOYEE の要求メッセージを作成するには、ストアド プロシージャ  
  
1.  Visual c# クラス ライブラリ プロジェクトをソリューションに追加します。 プロジェクトの名前を入力`UpdateEmployeeMessageCreator`です。  
  
2.  名前を変更**Class1.cs**に**UpdateEmployeeMessageCreator.cs**です。  
  
3.  .Cs ファイルに次のコードをコピーします。  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using System.Xml;  
    using System.IO;  
  
    namespace UpdateEmployeeMessageCreator  
    {  
        public class UpdateEmployeeMessageCreator  
        {  
            private static XmlDocument Message;  
            private static string XmlFileLocation;  
            private static string ResponseDoc;  
  
            public static XmlDocument XMLMessageCreator()  
            {  
                XmlFileLocation = "C:\\TestLocation\\CreateEmployeeMessage";  
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
  
     このコード スニペットの要求メッセージが必要ですが、 **UPDATE_EMPLOYEE**ストアド プロシージャを C:\TestLocation\CreateEmployeeMessage に存在します。 コードでは、要求メッセージを使用して、実行時に、同様の要求メッセージを作成します。  
  
4.  厳密な名前キー ファイルをプロジェクトに追加します。 参照してください[SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)です。  
  
    1.  ソリューション エクスプ ローラーで右クリックし、 **UpdateEmployeeMessageCreator**プロジェクトをクリックして**プロパティ**です。  
  
    2.  **プロパティ**ウィンドウで、をクリックして**署名**です。  
  
    3.  **署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンします。  
  
    4.  **厳密な名前キー ファイルを選択して**一覧で、クリックして**\<参照 >**です。  
  
    5.  厳密な名前のキー ファイルを作成したフォルダーに移動し、をクリックして**開く**です。  
  
    6.  をクリックして**保存**標準メニュー バーでします。 閉じる、**プロパティ**ウィンドウです。  
  
5.  プロジェクトをビルドする。 プロジェクトを右クリックし、をクリックして**ビルド**です。  
  
6.  このプロジェクトの参照をソリューション内の BizTalk プロジェクトに追加します。  
  
    1.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを展開しを右クリックして**参照**、クリックして**参照の追加**です。  
  
    2.  **参照の追加**ダイアログ ボックスで、をクリックして、**プロジェクト**タブです。  
  
    3.  、プロジェクト名の一覧から選択**UpdateEmployeeMessageCreator**、 をクリックして**追加**、をクリックし、 **OK**です。  
  
7.  プロジェクトをビルドすると、プロジェクトの \bin\Debug フォルダーの下アセンブリ DLL が作成されます。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。  
  
    1.  Visual Studio コマンド プロンプトを起動します。  
  
    2.  コマンド プロンプトからの \bin\Debug\ フォルダーに移動、 **UpdateEmployeeMessageCreator**プロジェクト。  
  
    3.  コマンド プロンプトで次のコマンドを実行します。  
  
        ```  
        gacutil /i UpdateEmployeeMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a>でしただけは何ですか。  
 このステップでは、実行時に要求メッセージを作成する UpdateEmployeeMessageCreator クラス ライブラリ プロジェクトを追加しました。 BizTalk プロジェクトでこのプロジェクトへの参照を追加しても、GAC にアセンブリ DLL を追加します。  
  
## <a name="next-steps"></a>次の手順  
 SQL Server に要求メッセージを送信し、」の説明に従って、応答を受信する[手順 2: SQL Server と応答の受信要求メッセージを送信](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)です。  
  
## <a name="see-also"></a>参照  
 [レッスン 3: 追加された新しい従業員を選択するストアド プロシージャを実行します。](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)