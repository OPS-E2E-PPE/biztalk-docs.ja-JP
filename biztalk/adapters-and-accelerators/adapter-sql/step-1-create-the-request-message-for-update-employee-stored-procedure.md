---
title: 手順 1:UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4dd975d9-4b38-46e0-a926-4b325b0d7b5e
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee815884b029e1efecedfcb3a6aea3b5a256e0a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367901"
---
# <a name="step-1-create-the-request-message-for-updateemployee-stored-procedure"></a>手順 1:UPDATE_EMPLOYEE の要求メッセージを作成するストアド プロシージャ
![手順 2 の 1](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **所要時間:** 10 分  
  
 **目標:** この手順で追加、C#をソリューションにクラス ライブラリ プロジェクト。 このライブラリは、メモリ内の要求メッセージを作成、 **UPDATE_EMPLOYEE**ストアド プロシージャ。 後の手順では、オーケストレーションは、ストアド プロシージャを実行する SQL Server にこのメッセージを送信します。  
  
## <a name="prerequisites"></a>前提条件  
 」の手順を完了する必要があります[レッスン 2。受信して通知をフィルター処理](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)します。  
  
### <a name="to-create-a-request-message-for-updateemployee-stored-procedure"></a>UPDATE_EMPLOYEE の要求メッセージを作成するには、ストアド プロシージャ  
  
1.  ビジュアルの追加C#をソリューションにクラス ライブラリ プロジェクト。 プロジェクトの名前を入力`UpdateEmployeeMessageCreator`します。  
  
2.  名前を変更**Class1.cs**に**UpdateEmployeeMessageCreator.cs**します。  
  
3.  次のコードを .cs ファイルにコピーします。  
  
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
  
     このコード スニペットの要求メッセージが必要ですが、 **UPDATE_EMPLOYEE**ストアド プロシージャを C:\TestLocation\CreateEmployeeMessage に存在します。 コードでは、要求メッセージを使用して、実行時に同様の要求メッセージを作成します。  
  
4.  厳密な名前キー ファイルをプロジェクトに追加します。 参照してください[SQL アダプターを使用して SQL アプリケーションを作成するための必要条件](../../adapters-and-accelerators/adapter-sql/prerequisites-to-create-sql-applications-using-the-sql-adapter.md)します。  
  
    1.  ソリューション エクスプ ローラーで右クリックし、 **UpdateEmployeeMessageCreator**プロジェクトをクリックして**プロパティ**します。  
  
    2.  **プロパティ**ウィンドウで、をクリックして**署名**します。  
  
    3.  **署名**] タブで、[、**アセンブリに署名**チェック ボックスをオンします。  
  
    4.  **厳密な名前キー ファイルを選択して**一覧で、 **\<参照\>** します。  
  
    5.  厳密な名前キー ファイルを作成したフォルダーに移動し、をクリックし、**オープン**します。  
  
    6.  クリックして**保存**標準のメニュー バー。 閉じる、**プロパティ**ウィンドウ。  
  
5.  プロジェクトをビルドする。 プロジェクトを右クリックし、**ビルド**します。  
  
6.  ソリューション内の BizTalk プロジェクトには、このプロジェクトの参照を追加します。  
  
    1.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを展開し、右クリックして**参照**、 をクリックし、**参照の追加**します。  
  
    2.  **参照の追加**ダイアログ ボックスで、をクリックして、**プロジェクト**タブ。  
  
    3.  プロジェクト名のリストから選択**UpdateEmployeeMessageCreator**、 をクリックして**追加**、順にクリックします**OK**します。  
  
7.  プロジェクトをビルドして、プロジェクトの \bin\Debug フォルダーの下に、アセンブリ DLL を作成します。 この DLL は、グローバル アセンブリ キャッシュ (GAC) に追加する必要があります。  
  
    1.  Visual Studio コマンド プロンプトを起動します。  
  
    2.  コマンド プロンプトからの \bin\Debug\ フォルダーに移動、 **UpdateEmployeeMessageCreator**プロジェクト。  
  
    3.  コマンド プロンプトで次のコマンドを実行します。  
  
        ```  
        gacutil /i UpdateEmployeeMessageCreator.dll  
        ```  
  
## <a name="what-did-i-just-do"></a>でしただけ何か。  
 この手順で実行時に要求メッセージを作成する UpdateEmployeeMessageCreator クラス ライブラリ プロジェクトを追加しました。 BizTalk プロジェクトでこのプロジェクトへの参照を追加し、またアセンブリ DLL を GAC に追加します。  
  
## <a name="next-steps"></a>次の手順  
 SQL Server に要求メッセージを送信し、」の説明に従って、応答を受信する[手順 2。SQL Server への要求メッセージの送信し、応答受信](../../adapters-and-accelerators/adapter-sql/step-2-send-the-request-message-to-sql-server-and-receive-response.md)します。  
  
## <a name="see-also"></a>参照  
 [レッスン 3:ストアド プロシージャを実行して、追加された新しい従業員を選択する](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)