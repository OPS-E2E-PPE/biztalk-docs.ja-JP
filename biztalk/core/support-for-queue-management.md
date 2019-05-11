---
title: キュー管理のサポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d60d06ba-8cf3-46d6-af59-626f12fc572a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c434b1c026eb3d1a0c6235dc885f10e62d3ec5dc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398927"
---
# <a name="support-for-queue-management"></a><span data-ttu-id="e00a9-102">キュー管理のサポート</span><span class="sxs-lookup"><span data-stu-id="e00a9-102">Support for Queue Management</span></span>
<span data-ttu-id="e00a9-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries アダプタを使用して、MQSeries キュー マネージャ上のキューをリモートから作成および削除できます。</span><span class="sxs-lookup"><span data-stu-id="e00a9-103">With the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries adapter you can now create and delete queues remotely on the MQSeries Queue Manager.</span></span> <span data-ttu-id="e00a9-104">この機能がサポートされるのは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で、MQSeries キュー マネージャと直接通信するリモートの MQSAgent COM+ オブジェクトが使用されるためです。</span><span class="sxs-lookup"><span data-stu-id="e00a9-104">This is supported because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] uses a remote MQSAgent COM+ object that communicates directly with the MQSeries Queue Manager.</span></span> <span data-ttu-id="e00a9-105">通常この MQSAgent は、リモートの MQSeries Server キューにメッセージを読み書きする実行時に使用されます。</span><span class="sxs-lookup"><span data-stu-id="e00a9-105">Typically this MQSAgent is used at run time to read and write messages to the remote MQSeries Server queues.</span></span> <span data-ttu-id="e00a9-106">このリモート サービスには、複数の BizTalk サーバーをクライアントとすることができます。</span><span class="sxs-lookup"><span data-stu-id="e00a9-106">More than one BizTalk server can be a client of this remote service.</span></span> <span data-ttu-id="e00a9-107">MQSAgent ではキューの作成および削除機能も提供され、これはオーケストレーションまたはアダプタ内から直接呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="e00a9-107">Additionally, queue creation and deletion functions are provided by this MQSAgent and can be called directly from within an orchestration or adapter.</span></span> <span data-ttu-id="e00a9-108">このことによって、高度に動的なシナリオを実現できます。このシナリオでは、オーケストレーションまたはアダプタは一時キューを作成でき、そのキューでメッセージを送信し、別のキューで返信を受け取り、最後に一時キューを削除できます。</span><span class="sxs-lookup"><span data-stu-id="e00a9-108">This allows for highly dynamic scenarios whereby the orchestration or adapter can create a temporary queue and then send a message on it, receive a reply on another queue, and finally delete the temporary queue.</span></span>  
  
## <a name="createqueue-and-deletequeue-apis"></a><span data-ttu-id="e00a9-109">CreateQueue および DeleteQueue API</span><span class="sxs-lookup"><span data-stu-id="e00a9-109">CreateQueue and DeleteQueue APIs</span></span>  
 <span data-ttu-id="e00a9-110">CreateQueue および DeleteQueue API は次のように定義されています。</span><span class="sxs-lookup"><span data-stu-id="e00a9-110">The CreateQueue and DeleteQueue APIs are defined as follows.</span></span>  
  
### <a name="structure-definition"></a><span data-ttu-id="e00a9-111">構造体定義</span><span class="sxs-lookup"><span data-stu-id="e00a9-111">Structure Definition</span></span>  
  
```  
typedef enum QueueUsage {  
      Normal       = 0,  
      Transmission = 1  
} QueueUsage;  
  
typedef enum ResultCode {  
      QueueAlreadyExists                     = 0, //  no bits set  
      QueueCreated                           = 1, //  QueueCreated  
      QueueCreatedAndRemoteDefinitionUpdated = 5, //  QueueCreated | RemoteDefinitionUpdated  
      QueueAndRemoteDefinitionCreated        = 7, //  QueueCreated | RemoteDefinitionCreated | RemoteDefinitionUpdated  
      QueueDoesNotExist                      = 8, //  QueueDoesNotExist  
      QueueDeleted                           = 16 //  QueueDeleted  
} ResultCode;  
```  
  
### <a name="interface-definition"></a><span data-ttu-id="e00a9-112">インターフェイス定義</span><span class="sxs-lookup"><span data-stu-id="e00a9-112">Interface Definition</span></span>  
  
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
  
## <a name="examples"></a><span data-ttu-id="e00a9-113">使用例</span><span class="sxs-lookup"><span data-stu-id="e00a9-113">Examples</span></span>  
 <span data-ttu-id="e00a9-114">「例 1」の手順を実行して、MQSeries Server キューの作成や削除に使用できる [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# コンソール アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e00a9-114">Complete the steps in Example 1 to create a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] C# console application which can be used to create or delete MQSeries Server queues.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="e00a9-115">例 1</span><span class="sxs-lookup"><span data-stu-id="e00a9-115">Example 1</span></span>  
  
##### <a name="create-a-c-console-application-to-manage-mqseries-server-queues"></a><span data-ttu-id="e00a9-116">MQSeries Server キューを管理する C# コンソール アプリケーションの作成</span><span class="sxs-lookup"><span data-stu-id="e00a9-116">Create a C# console application to manage MQSeries Server queues</span></span>  
  
1. <span data-ttu-id="e00a9-117">新しい Visual c# コンソール アプリケーションを作成で[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]名前**MQSeriesQueues**します。</span><span class="sxs-lookup"><span data-stu-id="e00a9-117">Create a new Visual C# Console Application in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] with the name **MQSeriesQueues**.</span></span>  
  
2. <span data-ttu-id="e00a9-118">以下のコードで生成される Program.cs ファイルで既存のコードを置き換えます。</span><span class="sxs-lookup"><span data-stu-id="e00a9-118">Replace any existing code in the Program.cs file that is generated with the code below:</span></span>  
  
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
  
3. <span data-ttu-id="e00a9-119">このプロジェクトへの参照を追加、 **MQSAgent 1.0 Type Library**します。</span><span class="sxs-lookup"><span data-stu-id="e00a9-119">Add a reference to this project to the **MQSAgent 1.0 Type Library**.</span></span> <span data-ttu-id="e00a9-120">**MQSAgent 1.0 Type Library**で使用できますが、 **COM**のタブ、**参照の追加** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="e00a9-120">The **MQSAgent 1.0 Type Library** is available on the **COM** tab of the **Add reference** dialog box.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="e00a9-121">このコンソール アプリケーションを実行するコンピュータには、MQSAgent COM+ コンポーネントがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e00a9-121">The MQSAgent COM+ component must be installed on the computer that you are running this console application from.</span></span> <span data-ttu-id="e00a9-122">MQSAgent COM + コンポーネントのインストールの詳細については、次を参照してください。 [MQSAgent COM + 構成ウィザードを使用して](../core/using-the-mqsagent-com-configuration-wizard.md)します。</span><span class="sxs-lookup"><span data-stu-id="e00a9-122">For more information about installing the MQSAgent COM+ component see [Using the MQSAgent COM+ Configuration Wizard](../core/using-the-mqsagent-com-configuration-wizard.md).</span></span>  
  
4. <span data-ttu-id="e00a9-123">コンソール アプリケーションをビルドします。</span><span class="sxs-lookup"><span data-stu-id="e00a9-123">Build the console application.</span></span>  
  
5. <span data-ttu-id="e00a9-124">コンパイルしたコンソール アプリケーションと同じディレクトリで、コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="e00a9-124">Open a command prompt in the same directory as the compiled console application.</span></span>  
  
6. <span data-ttu-id="e00a9-125">コンパイルしたコンソール アプリケーションの名前を、適切な引数と共に入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e00a9-125">Type the name of the compiled console application with the appropriate arguments and press ENTER.</span></span> <span data-ttu-id="e00a9-126">たとえば、キューを削除する**testq**キュー マネージャーの**QM_Test**をコマンド プロンプトで、次のテキストを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e00a9-126">For example, to delete the queue **testq** for the Queue Manager **QM_Test** you would type the following text at the command prompt and press ENTER:</span></span>  
  
   ```  
   MQSeriesQueues d QM_Test testq  
   ```  
  
7. <span data-ttu-id="e00a9-127">キューを作成する**testq**キュー マネージャーの**QM_Test**をコマンド プロンプトで、次のテキストを入力し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e00a9-127">To create the queue **testq** for the Queue Manager **QM_Test** you would type the following text at the command prompt and press ENTER:</span></span>  
  
   ```  
   MQSeriesQueues c QM_Test testq  
   ```