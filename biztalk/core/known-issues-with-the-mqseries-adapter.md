---
title: "MQSeries アダプターに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c36bcabb-e1eb-455c-8384-00d4682464d3
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe3093416a10b6b66867dcb2e3629de8f25e5aca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-the-mqseries-adapter"></a><span data-ttu-id="170ab-102">MQSeries アダプターに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="170ab-102">Known Issues with the MQSeries Adapter</span></span>
<span data-ttu-id="170ab-103">ここでは、エラー回避に役立つ情報を記載します。</span><span class="sxs-lookup"><span data-stu-id="170ab-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="know-issues"></a><span data-ttu-id="170ab-104">既知の問題点</span><span class="sxs-lookup"><span data-stu-id="170ab-104">Know Issues</span></span>  
  
#### <a name="access-denied-errors-occur-when-attempting-to-send-or-receive-messages"></a><span data-ttu-id="170ab-105">メッセージの送信または受信を試行したときにアクセス拒否エラーが発生する</span><span class="sxs-lookup"><span data-stu-id="170ab-105">Access Denied errors occur when attempting to send or receive messages</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="170ab-106">問題</span><span class="sxs-lookup"><span data-stu-id="170ab-106">Problem</span></span>  
 <span data-ttu-id="170ab-107">MQSeries アダプターを使用して MQSeries サーバーとの間でメッセージを送信または受信すると、イベント ビューアーのアプリケーション ログに次のようなメッセージが記録されます。</span><span class="sxs-lookup"><span data-stu-id="170ab-107">When you use the MQSeries adapter to send messages to or receive messages from an MQSeries server, error messages that are similar to the following are logged in the Application log in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
```  
The adapter failed to transmit message going to send port "MQS://servername/queuename". It will be retransmitted after the retry interval specified for this Send Port. Details: "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
> [!NOTE]
>  <span data-ttu-id="170ab-108">このエラー メッセージに*servername* 、サーバーの名前を指定し、 *queuename*キューの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="170ab-108">In this error message, *servername* is the name of the server and *queuename* is the name of the queue.</span></span>  
  
 <span data-ttu-id="170ab-109">さらに、BizTalk Adapter for MQSeries を使用する構成で受信場所または送信ポートを作成しようとすると、イベント ビューアーに次の警告メッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="170ab-109">Additionally, when you try to create the receive location or the send port that is configured to use the BizTalk Adapter for MQSeries, you may receive the following warning message in Event Viewer:</span></span>  
  
```  
The adapter "MQSeries" raised an error message. Details "The adapter has encountered an 'Access Denied' error while attempting to contact the COM+ object on the MQSeries server. Ensure the BizTalk account is added to the Role on the MQSAgent COM+ application."  
```  
  
##### <a name="cause"></a><span data-ttu-id="170ab-110">原因</span><span class="sxs-lookup"><span data-stu-id="170ab-110">Cause</span></span>  
 <span data-ttu-id="170ab-111">この問題は、1 つの場合に発生する可能性があります。 または以上の次の条件に該当します。</span><span class="sxs-lookup"><span data-stu-id="170ab-111">This issue may occur if one or more of the following conditions are true:</span></span>  
  
-   <span data-ttu-id="170ab-112">MQSeries アダプターのホスト アカウントに、MQSeries サーバー上の MQSAgent COM+ アプリケーションに必要なアクセス許可がない。</span><span class="sxs-lookup"><span data-stu-id="170ab-112">The host account for the MQSeries adapter does not have the required permissions for the MQSAgent COM+ application on the MQSeries server.</span></span>  
  
-   <span data-ttu-id="170ab-113">[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] ベースのサーバー上で、MQSeries アダプターのホスト アカウントが、MQSeries サーバーの分散 COM ユーザー グループのメンバーになっていない。</span><span class="sxs-lookup"><span data-stu-id="170ab-113">On a [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, the host account for the MQSeries adapter is not a member of the Distributed COM Users group on the MQSeries server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="170ab-114">解決策</span><span class="sxs-lookup"><span data-stu-id="170ab-114">Resolution</span></span>  
 <span data-ttu-id="170ab-115">この問題を解決するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="170ab-115">To resolve this issue, use the following methods.</span></span> <span data-ttu-id="170ab-116">最初の方法から試し、問題を解決できなかった場合は次の方法を試してください。</span><span class="sxs-lookup"><span data-stu-id="170ab-116">If a method does not resolve the issue, try the next method.</span></span>  
  
 <span data-ttu-id="170ab-117">**方法 1: Microsoft でネットワーク COM + アクセスを有効にする[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-ベースのコンピューター**</span><span class="sxs-lookup"><span data-stu-id="170ab-117">**Method 1: Enable network COM+ access on the Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer**</span></span>  
  
 <span data-ttu-id="170ab-118">Microsoft でネットワーク COM + アクセスを有効にする[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-ベースのコンピューターに次に記載されている手順に従って、 [Windows Server 2003 でネットワーク COM + アクセスを有効にする方法](http://go.microsoft.com/fwlink/?LinkId=67076)です。</span><span class="sxs-lookup"><span data-stu-id="170ab-118">Enable network COM+ access on a Microsoft [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based computer by following the steps documented in [How to enable network COM+ access in Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=67076).</span></span>  
  
 <span data-ttu-id="170ab-119">**方法 2: MSDTC 設定を構成します。**</span><span class="sxs-lookup"><span data-stu-id="170ab-119">**Method 2: Configure MSDTC settings**</span></span>  
  
 <span data-ttu-id="170ab-120">手順に従います、**で適切な MSDTC セキュリティ構成オプションを設定[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]**のセクション[MSDTC の問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)MSDTC 設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="170ab-120">Follow the steps in the **Set the appropriate MSDTC Security Configuration options on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]** section of [Troubleshooting Problems with MSDTC](../core/troubleshooting-problems-with-msdtc.md) to configure MSDTC settings.</span></span>  
  
 <span data-ttu-id="170ab-121">**方法 3: ホスト アカウントが MQSAgent COM + アプリケーションのロールに追加されたことを確認してください。**</span><span class="sxs-lookup"><span data-stu-id="170ab-121">**Method 3: Verify that the host account is added to the role in the MQSAgent COM+ application**</span></span>  
  
 <span data-ttu-id="170ab-122">MQSeries アダプターのホスト アカウントが、MQSeries サーバー上の MQSAgent COM+ アプリケーションに作成されたロールに追加されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="170ab-122">Verify that the host account for the MQSeries adapter is added to the role that was created in the MQSAgent COM+ application on the MQSeries server.</span></span> <span data-ttu-id="170ab-123">これは [コンポーネント サービス] 管理コンソール インターフェイスで確認できます。</span><span class="sxs-lookup"><span data-stu-id="170ab-123">You can verify this in the Component Services management console interface.</span></span>  
  
 <span data-ttu-id="170ab-124">**方法 4: の場合、MQSeries アダプターのホスト アカウントが Distributed COM Users グループのメンバーであることを確認します。**</span><span class="sxs-lookup"><span data-stu-id="170ab-124">**Method 4: Verify that the host account for the MQSeries adapter is a member of the Distributed COM Users group**</span></span>  
  
 <span data-ttu-id="170ab-125">Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] ベースのサーバーで、MQSeries アダプターのホスト アカウントのグループ メンバーシップを確認します。</span><span class="sxs-lookup"><span data-stu-id="170ab-125">On a Windows [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]-based server, examine the group memberships of the host account for the MQSeries adapter.</span></span> <span data-ttu-id="170ab-126">アカウントがのメンバーであるかどうかを確認、 **Distributed COM Users** MQSAgent COM + アプリケーションがインストールされている MQSeries サーバーでグループ化します。</span><span class="sxs-lookup"><span data-stu-id="170ab-126">Make sure that the account is a member of the **Distributed COM Users** group on the MQSeries server where the MQSAgent COM+ application is installed.</span></span>  
  
 <span data-ttu-id="170ab-127">Microsoft の DCOM セキュリティ強化の詳細については[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]を参照してください[DCOM セキュリティ強化](http://go.microsoft.com/fwlink/?LinkId=67077)です。</span><span class="sxs-lookup"><span data-stu-id="170ab-127">For more information about DCOM security enhancements in Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], see [DCOM Security Enhancements](http://go.microsoft.com/fwlink/?LinkId=67077).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="170ab-128">参照</span><span class="sxs-lookup"><span data-stu-id="170ab-128">See Also</span></span>  
 [<span data-ttu-id="170ab-129">MQSeries アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="170ab-129">Troubleshooting the MQSeries Adapter</span></span>](../core/troubleshooting-the-mqseries-adapter.md)