---
title: "キューの管理のサポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d60d06ba-8cf3-46d6-af59-626f12fc572a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faeb3f141e114cf1f86157084f50d0a0d490833a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-queue-management"></a>キュー管理のサポート
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries アダプタを使用して、MQSeries キュー マネージャ上のキューをリモートから作成および削除できます。 この機能がサポートされるのは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、MQSeries キュー マネージャと直接通信するリモートの MQSAgent COM+ オブジェクトが使用されるためです。 通常この MQSAgent は、リモートの MQSeries Server キューにメッセージを読み書きする実行時に使用されます。 このリモート サービスには、複数の BizTalk サーバーをクライアントとすることができます。 MQSAgent ではキューの作成および削除機能も提供され、これはオーケストレーションまたはアダプタ内から直接呼び出すことができます。 このことによって、高度に動的なシナリオを実現できます。このシナリオでは、オーケストレーションまたはアダプタは一時キューを作成でき、そのキューでメッセージを送信し、別のキューで返信を受け取り、最後に一時キューを削除できます。  
  
## <a name="createqueue-and-deletequeue-apis"></a>CreateQueue および DeleteQueue API  
 CreateQueue および DeleteQueue API は次のように定義されています。  
  
### <a name="structure-definition"></a>構造体定義  
  
```  
typedef enum QueueUsage {  
      Normal       = 0,  
      Transmission = 1  
} QueueUsage;  
  
typedef enum ResultCode {  
      QueueAlreadyExists                     = 0, //  no bits set  
      QueueCreated                           = 1, //  QueueCreated  
      QueueCreatedAndRemoteDefinitionUpdated = 5, //  QueueCreated | RemoteDefinitionUpdated  
      QueueAndRemoteDefinitionCreated        = 7, //  QueueCreated | RemoteDefinitionCreated | RemoteDefinitionUpdated  
      QueueDoesNotExist                      = 8, //  QueueDoesNotExist  
      QueueDeleted                           = 16 //  QueueDeleted  
} ResultCode;  
```  
  
### <a name="interface-definition"></a>インターフェイス定義  
  
```  
[  
            object,  
            uuid(E90AC1A6-657B-4680-AF6A-89F11113FB8B),  
            dual,  
            nonextensible,  
            helpstring("IMQSAdmin Interface"),  
            pointer_default(unique)  
]  
interface IMQSAdmin2 : IDispatch{  
  
HRESULT CreateQueue (  
[in]BSTR queueManager,  
[in]BSTR newQueueName,  
[in]QueueUsage usage,  
[in]BSTR remoteDefinition,  
[in]BSTR remoteQName,  
[in]BSTR remoteQMgrName,  
[in]BOOL updateExistingRemoteDefinition,  
[out, retval]ResultCode* resultCode);  
  
HRESULT DeleteQueue (  
[in]BSTR queueManager,  
[in]BSTR newQueueName,  
[out, retval]ResultCode* resultCode);  
};  
  
      [  
            uuid(412AF00D-7CA8-4d2a-AFF6-F61CE2E29A0D),  
            helpstring("MQSAdmin Class")  
      ]  
      coclass MQSAdmin  
      {  
            [default] interface IMQSAdmin2;  
      };  
  
```  
  
## <a name="examples"></a>使用例  
 「例 1」の手順を実行して、MQSeries Server キューの作成や削除に使用できる [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# コンソール アプリケーションを作成します。  
  
### <a name="example-1"></a>例 1  
  
##### <a name="create-a-c-console-application-to-manage-mqseries-server-queues"></a>MQSeries Server キューを管理する C# コンソール アプリケーションの作成  
  
1.  新しい Visual c# コンソール アプリケーションを作成で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]名前を持つ**MQSeriesQueues**です。  
  
2.  以下のコードで生成される Program.cs ファイルで既存のコードを置き換えます。  
  
    ```  
    using System;  
    using System.Collections.Generic;  
    using System.Text;  
    using MQSAgentLib;  
  
    namespace MQSeriesQueues  
    {  
        class ManageQueues  
        {  
            public static void Main(string[] args)  
            {  
                // The first argument should be "c" (without quotes)  
                // to create a queue, anything else to delete a queue.  
                // The 2nd and 3rd arguments should be the name of   
                // the MQSeries Queue Manager and the name of   
                // the queue to be created or deleted for example  
                // the following usage will create the local   
                // queue testq for the Queue Manager QM_Test  
                // MQSeriesQueues c QM_Test testq  
                createordeleteQs(args[0], args[1], args[2]);  
            }  
  
            static void createordeleteQs(string Qswitch, string QMgr, string QName)  
            {   
            if ((Qswitch =="c" & (QMgr != null & QName != null)))  
                {  
                    CreateQueue(QMgr, QName);  
                }  
                else if(QMgr != null & QName != null)  
                {  
                    DeleteQueue(QMgr, QName);  
                }  
             }  
  
            static void CreateQueue(string Qmgr, string Qname)  
            {  
                MQSAdmin admin = new MQSAdmin();    
  
                ResultCode resultCode = admin.CreateQueue(Qmgr, Qname, 0, "", "", "", 0);  
  
                if ((resultCode & ResultCode.QueueCreated) == ResultCode.QueueCreated)  
                {  
                    Console.WriteLine("Queue Created.");  
                }  
                else if ((resultCode & ResultCode.QueueAlreadyExists) == ResultCode.QueueAlreadyExists)  
                {  
                    Console.WriteLine("Queue Already Exists.");  
                }  
            }  
  
            static void DeleteQueue(string Qmgr, string Qname)  
            {  
                MQSAdmin admin = new MQSAdmin();  
  
                ResultCode resultCode = admin.DeleteQueue(Qmgr, Qname);  
  
                if ((resultCode & ResultCode.QueueDeleted) == ResultCode.QueueDeleted)  
                {  
                    Console.WriteLine("Queue successfully deleted.");  
                }  
                if ((resultCode & ResultCode.QueueDoesNotExist) == ResultCode.QueueDoesNotExist)  
                {  
                    Console.WriteLine("Queue did not exist anyway!");  
                }  
            }  
  
        }  
    }  
    ```  
  
3.  このプロジェクトへの参照を追加、 **MQSAgent 1.0 Type Library**です。 **MQSAgent 1.0 Type Library**で使用できるは、 **COM**のタブ、**参照の追加** ダイアログ ボックス。  
  
    > [!NOTE]
    >  このコンソール アプリケーションを実行するコンピュータには、MQSAgent COM+ コンポーネントがインストールされている必要があります。 MQSAgent COM + コンポーネントのインストールの詳細については、次を参照してください。 [MQSAgent COM + 構成ウィザードを使用して](../core/using-the-mqsagent-com-configuration-wizard.md)です。  
  
4.  コンソール アプリケーションをビルドします。  
  
5.  コンパイルしたコンソール アプリケーションと同じディレクトリで、コマンド プロンプトを開きます。  
  
6.  コンパイルしたコンソール アプリケーションの名前を、適切な引数と共に入力し、Enter キーを押します。 例については、キューを削除する**testq**キュー マネージャーの**QM_Test**はコマンド プロンプトで次のテキストを入力して ENTER キーを押します。  
  
    ```  
    MQSeriesQueues d QM_Test testq  
    ```  
  
7.  キューを作成する**testq**キュー マネージャーの**QM_Test**はコマンド プロンプトで次のテキストを入力して ENTER キーを押します。  
  
    ```  
    MQSeriesQueues c QM_Test testq  
    ```