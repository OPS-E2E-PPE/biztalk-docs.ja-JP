---
title: "ApplicationAdapter |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2f9b876b-cd37-4e24-a476-186adc155ac0
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee9d04f98da5e9b8aa1faba81f32fe5ec37d23b9
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="applicationadapter"></a><span data-ttu-id="5e5ea-102">ApplicationAdapter</span><span class="sxs-lookup"><span data-stu-id="5e5ea-102">ApplicationAdapter</span></span>
<span data-ttu-id="5e5ea-103">ApplicationAdapter サンプルは、メッセージの受信時にパブリック プロセスとプライベート プロセス (応答側または開始側) から通知を送信する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-103">The ApplicationAdapter sample demonstrates how to send notifications from the public and private processes (responder or initiator) when you receive a message.</span></span> <span data-ttu-id="5e5ea-104">このサンプルには、必要に応じて新しい機能を追加できます。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-104">You can customize the sample with whatever additional functionality you want.</span></span>  
  
 <span data-ttu-id="5e5ea-105">ApplicationAdapter サンプルは、`IApplicationAdapter` インターフェイスを `ApplicationAdapter1` クラスに実装する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-105">The ApplicationAdapter sample demonstrates how to implement the `IApplicationAdapter` interface to the `ApplicationAdapter1` class.</span></span> <span data-ttu-id="5e5ea-106">このクラスには、`BeginNotify` と `Notify` という 2 つのメソッドが含まれます。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-106">This class includes two methods, `BeginNotify` and `Notify`.</span></span> <span data-ttu-id="5e5ea-107">各クラスのパラメーターは、メッセージ カテゴリ、送信元パーティ名、送信先パーティ名、PIP (Partner Interface Process) コード、PIP インスタンス ID、および PIP バージョンです。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-107">The parameters for each class are the message category, source party name, destination party name, Partner Interface Process (PIP) code, PIP instance ID, and PIP version.</span></span>  
  
 <span data-ttu-id="5e5ea-108">アセンブリ名とクラス名を入力して、アグリーメントの ApplicationAdapter を設定する、**全般**アグリーメントのタブ、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) 管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-108">You set the ApplicationAdapter for an agreement by entering the assembly name and class name on the **General** tab of the agreement in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] ([!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]) Management Console.</span></span> <span data-ttu-id="5e5ea-109">アプリケーション アダプタの .dll ファイルが BizTalk ホスト サービスと同じ資格情報を使用して実行されます。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-109">The application adapter .dll file runs under the same credentials as the BizTalk host service.</span></span>  
  
 <span data-ttu-id="5e5ea-110">ApplicationAdapter サンプルまたは関連するいずれかの外部環境変数を変更した場合は、[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] のパブリック プロセスをホストする BizTalk ホスト サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-110">If you change the ApplicationAdapter sample or any external environment variable that the ApplicationAdapter sample depends on, restart the BizTalk host service that hosts the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] public process.</span></span>  
  
 <span data-ttu-id="5e5ea-111">ApplicationAdapter サンプル コードにある\<*ドライブ*\>: \Program Files\ BizTalk\<バージョン\>Accelerator RosettaNet\SDK\ApplicationAdapterfor\\.</span><span class="sxs-lookup"><span data-stu-id="5e5ea-111">The ApplicationAdapter sample code is located at \<*drive*\>:\Program Files\ BizTalk \<version\> Accelerator for RosettaNet\SDK\ApplicationAdapter\\.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="5e5ea-112">使用例</span><span class="sxs-lookup"><span data-stu-id="5e5ea-112">Demonstrates</span></span>  
 <span data-ttu-id="5e5ea-113">ApplicationAdapter サンプルは、パブリック プロセスがメッセージを受信したことを応答側プライベート プロセスに通知する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-113">The ApplicationAdapter sample demonstrates how to notify the responder private process that the public process has received a message.</span></span> <span data-ttu-id="5e5ea-114">通知には、メッセージ カテゴリ、送信元パーティ名、送信先パーティ名、PIP コード、PIP バージョン、および PIP インスタンス ID が示されます。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-114">The notification indicates the message category, the source party name, the destination party name, the PIP code, the PIP version, and the PIP instance ID.</span></span> <span data-ttu-id="5e5ea-115">この通知は、アクション メッセージと応答メッセージのいずれに関しても送信できます。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-115">You can send this notification for either an action or a response message.</span></span>  
  
 <span data-ttu-id="5e5ea-116">`BeginNotify` メソッドと `Notify` メソッドは次のように機能します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-116">The `BeginNotify` and `Notify` methods work as follows:</span></span>  
  
1.  <span data-ttu-id="5e5ea-117">応答側パブリック プロセスがメッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-117">The responder public process receives a message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5e5ea-118">次の手順は、パブリック開始側が応答側から応答メッセージを受信する状況にも当てはまります。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-118">The following steps are also applicable for the scenario in which the public initiator receives a response message from the responder.</span></span>  
  
2.  <span data-ttu-id="5e5ea-119">受信パイプラインとパブリック プロセス、および場合によって検証アダプターによる検証が正しく行われると、応答側パブリック プロセスは、`BeginNotify` クラスの `ApplicationAdapter` メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-119">If validation by the receive pipeline and public process, and validation adapter, if applicable, was successful, the responder public process calls the `BeginNotify` method in the `ApplicationAdapter` class.</span></span> <span data-ttu-id="5e5ea-120">このメソッドは、パブリック プロセスが新しいメッセージを受信し、そのメッセージを MessageBox データベースに保存したことを、応答側プライベート プロセスに通知します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-120">This method notifies the responder private process that the public process has received the new message and saved the message in the MessageBox database.</span></span>  
  
3.  <span data-ttu-id="5e5ea-121">応答側パブリック プロセスがシグナル メッセージを開始側に戻します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-121">The responder public process sends a signal message back to the initiator.</span></span>  
  
4.  <span data-ttu-id="5e5ea-122">応答側パブリック プロセスがメッセージの Service Content を応答側プライベート プロセスに送信します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-122">The responder public process sends the message service content to the responder private process.</span></span>  
  
5.  <span data-ttu-id="5e5ea-123">応答側プライベート プロセスが BTARNDATA データベースの MessagesToLOB テーブルにメッセージを格納します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-123">The responder private process puts the message in the MessagesToLOB table of the BTARNDATA database.</span></span>  
  
6.  <span data-ttu-id="5e5ea-124">応答側プライベート プロセスが `Notify` クラスの `ApplicationAdapter` メソッドを呼び出して、End Notify メッセージを応答側パブリック プロセスに戻します。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-124">The responder private process calls the `Notify` method in the `ApplicationAdapter` class to send the End Notify message back to the responder public process.</span></span> <span data-ttu-id="5e5ea-125">応答側パブリック プロセスが正しく実行されるには、End Notify メッセージを受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-125">The responder public process must receive the End Notify message for the process to be successfully completed.</span></span> <span data-ttu-id="5e5ea-126">受信しなかった場合、メッセージは保留されます。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-126">Otherwise, the message is suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e5ea-127">`Notify` メッセージを使用すると、MessagesToLOB テーブルでメッセージが待機しているというシグナルを基幹業務 (LOB) アプリケーションに送ることができます。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-127">You can use the `Notify` message to signal the line-of-business (LOB) application that the message is waiting in the MessagesToLOB table.</span></span> <span data-ttu-id="5e5ea-128">LOB アプリケーションは、システムから警告を受けるとすぐにテーブルからメッセージを取得できます。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-128">As soon the system alerts the LOB application, the LOB application can retrieve the message from that table.</span></span>  
  
## <a name="to-implement-this-sample"></a><span data-ttu-id="5e5ea-129">サンプルの実装</span><span class="sxs-lookup"><span data-stu-id="5e5ea-129">To Implement this Sample</span></span>  
 <span data-ttu-id="5e5ea-130">ApplicationAdapter サンプルを実装するには、アプリケーション アダプタをアグリーメントに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-130">To implement the ApplicationAdapter sample, you must add the application adapter to the agreement.</span></span>  
  
#### <a name="to-add-the-application-adapter-to-an-agreement"></a><span data-ttu-id="5e5ea-131">アプリケーション アダプターをアグリーメントに追加するには</span><span class="sxs-lookup"><span data-stu-id="5e5ea-131">To add the application adapter to an agreement</span></span>  
  
1.  <span data-ttu-id="5e5ea-132">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] **BizTalk\<バージョン\>Accelerator for RosettaNet**、し、をクリックして[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理コンソール**です。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-132">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] **BizTalk \<version\> Accelerator for RosettaNet**, and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2.  <span data-ttu-id="5e5ea-133">[!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)]管理コンソールで、展開[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]、 をクリック**契約**です。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-133">In the [!INCLUDE[btaBTARNNoVersion](../../includes/btabtarnnoversion-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and click **Agreements**.</span></span>  
  
3.  <span data-ttu-id="5e5ea-134">アプリケーション アダプターを追加するアグリーメントをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-134">Double-click the agreement to which you want to add the application adapter.</span></span>  
  
4.  <span data-ttu-id="5e5ea-135">**アプリケーション アダプター**ボックスで、省略記号ボタンをクリックして (**.**) の右側にあるボタン**アセンブリ名**、アプリケーション アダプタ アセンブリが含まれている場所に移動して、適切な .dll ファイルを選択および順にクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-135">In the **Application Adapter** box, click the ellipsis button (**...**) button to the right of **Assembly name**, move to the location that contains the application adapter assembly, select the appropriate .dll file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="5e5ea-136">下矢印をクリックして**クラス名**アプリケーション アダプター クラスを選択し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="5e5ea-136">Click the down arrow for **Class Name**, select the application adapter class, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e5ea-137">参照</span><span class="sxs-lookup"><span data-stu-id="5e5ea-137">See Also</span></span>  
 [<span data-ttu-id="5e5ea-138">アダプター サンプル</span><span class="sxs-lookup"><span data-stu-id="5e5ea-138">Adapter Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)