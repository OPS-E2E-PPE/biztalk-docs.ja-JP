---
title: MQSeries アダプターに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c36bcabb-e1eb-455c-8384-00d4682464d3
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6185519c3669b61a805fb403b38ead9ad6316184
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380899"
---
# <a name="known-issues-with-the-mqseries-adapter"></a><span data-ttu-id="d1bab-102">MQSeries アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="d1bab-102">Known Issues with the MQSeries Adapter</span></span>
<span data-ttu-id="d1bab-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="know-issues"></a><span data-ttu-id="d1bab-104">既知の問題</span><span class="sxs-lookup"><span data-stu-id="d1bab-104">Know Issues</span></span>  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a><span data-ttu-id="d1bab-105">送信または受信メッセージにアクセス拒否エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-105">Access Denied errors occur when attempting to send or receive messages</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="d1bab-106">問題</span><span class="sxs-lookup"><span data-stu-id="d1bab-106">Problem</span></span>  
 <span data-ttu-id="d1bab-107">MQSeries アダプターを使用してメッセージを送信または MQSeries サーバーからメッセージを受信するときに、次のようなエラー メッセージがイベント ビューアーのアプリケーション ログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="d1bab-107">When you use the MQSeries adapter to send messages to or receive messages from an MQSeries server, error messages that are similar to the following are logged in the Application log in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  <span data-ttu-id="d1bab-108">このエラー メッセージで*servername* 、サーバーの名前を指定し、 *queuename*キューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-108">In this error message, *servername* is the name of the server and *queuename* is the name of the queue.</span></span>  
  
 <span data-ttu-id="d1bab-109">さらに、受信場所または MQSeries の BizTalk アダプターを使用するように構成する送信ポートを作成するときに、イベント ビューアーで、次の警告メッセージを受け取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d1bab-109">Additionally, when you try to create the receive location or the send port that is configured to use the BizTalk Adapter for MQSeries, you may receive the following warning message in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a><span data-ttu-id="d1bab-110">原因</span><span class="sxs-lookup"><span data-stu-id="d1bab-110">Cause</span></span>  
 <span data-ttu-id="d1bab-111">この問題は、1 つの場合に発生する可能性があります。 または true は、次の条件の詳細。</span><span class="sxs-lookup"><span data-stu-id="d1bab-111">This issue may occur if one or more of the following conditions are true:</span></span>  
  
- <span data-ttu-id="d1bab-112">MQSeries アダプターのホスト アカウントには、MQSeries サーバー上の MQSAgent COM + アプリケーションの必要なアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="d1bab-112">The host account for the MQSeries adapter does not have the required permissions for the MQSAgent COM+ application on the MQSeries server.</span></span>  
  
- <span data-ttu-id="d1bab-113">[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-ベースのサーバー ホスト アカウント、MQSeries アダプターが、MQSeries サーバーの Distributed COM Users グループのメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="d1bab-113">On a [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, the host account for the MQSeries adapter is not a member of the Distributed COM Users group on the MQSeries server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="d1bab-114">解決策</span><span class="sxs-lookup"><span data-stu-id="d1bab-114">Resolution</span></span>  
 <span data-ttu-id="d1bab-115">この問題を解決するには、次のメソッドを使用します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-115">To resolve this issue, use the following methods.</span></span> <span data-ttu-id="d1bab-116">メソッドで問題が解決しない場合は、次の方法をお試しください。</span><span class="sxs-lookup"><span data-stu-id="d1bab-116">If a method does not resolve the issue, try the next method.</span></span>  
  
 <span data-ttu-id="d1bab-117">**方法 1:Microsoft ネットワーク COM + アクセスを有効にする[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-ベースのコンピューター**</span><span class="sxs-lookup"><span data-stu-id="d1bab-117">**Method 1: Enable network COM+ access on the Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer**</span></span>  
  
 <span data-ttu-id="d1bab-118">Microsoft でネットワーク COM + アクセスを有効にする[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-ベースのコンピューターに記載の手順に従って[Windows Server 2003 でネットワーク COM + アクセスを有効にする方法](http://go.microsoft.com/fwlink/?LinkId=67076)します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-118">Enable network COM+ access on a Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer by following the steps documented in [How to enable network COM+ access in Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=67076).</span></span>  
  
 <span data-ttu-id="d1bab-119">**方法 2:MSDTC 設定を構成します。**</span><span class="sxs-lookup"><span data-stu-id="d1bab-119">**Method 2: Configure MSDTC settings**</span></span>  
  
 <span data-ttu-id="d1bab-120">手順に従って、**適切な MSDTC セキュリティ構成オプションの設定[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** のセクション[MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)MSDTC 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-120">Follow the steps in the **Set the appropriate MSDTC Security Configuration options on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** section of [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md) to configure MSDTC settings.</span></span>  
  
 <span data-ttu-id="d1bab-121">**方法 3:ホスト アカウントが MQSAgent COM + アプリケーション ロールに追加することを確認します。**</span><span class="sxs-lookup"><span data-stu-id="d1bab-121">**Method 3: Verify that the host account is added to the role in the MQSAgent COM+ application**</span></span>  
  
 <span data-ttu-id="d1bab-122">MQSeries server 上の MQSAgent COM + アプリケーションで作成されたロールに、MQSeries アダプターのホスト アカウントが追加されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-122">Verify that the host account for the MQSeries adapter is added to the role that was created in the MQSAgent COM+ application on the MQSeries server.</span></span> <span data-ttu-id="d1bab-123">これは、コンポーネント サービス管理コンソール インターフェイスで確認できます。</span><span class="sxs-lookup"><span data-stu-id="d1bab-123">You can verify this in the Component Services management console interface.</span></span>  
  
 <span data-ttu-id="d1bab-124">**方法 4:MQSeries アダプターのホスト アカウントが Distributed COM Users グループのメンバーであることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="d1bab-124">**Method 4: Verify that the host account for the MQSeries adapter is a member of the Distributed COM Users group**</span></span>  
  
 <span data-ttu-id="d1bab-125">Windows で[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-ベースのサーバーで、MQSeries アダプターのホスト アカウントのグループ メンバーシップを確認します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-125">On a Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, examine the group memberships of the host account for the MQSeries adapter.</span></span> <span data-ttu-id="d1bab-126">アカウントがのメンバーであることを確認、 **Distributed COM Users** MQSAgent COM + アプリケーションがインストールされている MQSeries サーバーでグループ化します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-126">Make sure that the account is a member of the **Distributed COM Users** group on the MQSeries server where the MQSAgent COM+ application is installed.</span></span>  
  
 <span data-ttu-id="d1bab-127">Microsoft の DCOM セキュリティ強化の詳細については[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]を参照してください[DCOM のセキュリティが強化された](http://go.microsoft.com/fwlink/?LinkId=67077)します。</span><span class="sxs-lookup"><span data-stu-id="d1bab-127">For more information about DCOM security enhancements in Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], see [DCOM Security Enhancements](http://go.microsoft.com/fwlink/?LinkId=67077).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1bab-128">参照</span><span class="sxs-lookup"><span data-stu-id="d1bab-128">See Also</span></span>  
 [<span data-ttu-id="d1bab-129">MQSeries アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d1bab-129">Troubleshooting the MQSeries Adapter</span></span>](../core/troubleshooting-the-mqseries-adapter.md)