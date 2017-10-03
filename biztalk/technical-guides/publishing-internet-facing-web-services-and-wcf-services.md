---
title: "インターネットに接続された Web サービスと WCF サービスを発行 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38ee916aaa5e158160f2096b0ba9b2678dd6b8d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a><span data-ttu-id="c2d70-102">インターネットに接続された Web サービスと WCF サービスの発行</span><span class="sxs-lookup"><span data-stu-id="c2d70-102">Publishing Internet-facing Web Services and WCF Services</span></span>
<span data-ttu-id="c2d70-103">複数の方法を使用するには発行のため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービスをインターネット。</span><span class="sxs-lookup"><span data-stu-id="c2d70-103">You can use multiple approaches for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services and WCF services to the Internet:</span></span>  
  
-   <span data-ttu-id="c2d70-104">リバース プロキシ ルールを使用して、境界ネットワーク (DMZ、非武装地帯およびスクリーン サブネットとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="c2d70-104">Use reverse proxy rules in a perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>  
  
-   <span data-ttu-id="c2d70-105">実行するコンピューターに配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワークのドメインに、Web サービスまたは WCF サービスを発行します。</span><span class="sxs-lookup"><span data-stu-id="c2d70-105">Put the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that publish the Web services or WCF services into the perimeter network domain.</span></span>  
  
-   <span data-ttu-id="c2d70-106">使用して[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]クラウドの Web サービスまたは WCF サービスを Azure AppFabric Service Bus リレー エンドポイントとして公開する機能を有効化します。</span><span class="sxs-lookup"><span data-stu-id="c2d70-106">Use [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] cloud enabler functionality to publish the Web services or WCF services as an Azure AppFabric Service Bus relay endpoint.</span></span>  
  
## <a name="using-a-reverse-proxy"></a><span data-ttu-id="c2d70-107">リバース プロキシを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2d70-107">Using a Reverse Proxy</span></span>  
 <span data-ttu-id="c2d70-108">発行のための従来のアプローチがされてこの[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービスです。</span><span class="sxs-lookup"><span data-stu-id="c2d70-108">This has been the traditional approach for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services and WCF services.</span></span> <span data-ttu-id="c2d70-109">リバース プロキシ ルールを使用して、境界ネットワーク内と、境界ネットワークにある BizTalk サーバーが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2d70-109">Using reverse proxy rules in the perimeter network obviates the need to have BizTalk servers located in the perimeter network.</span></span> <span data-ttu-id="c2d70-110">リバース プロキシ ルールだけで、HTTP および SOAP に要求を転送、境界ネットワークから実行しているコンピューター[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イントラネット ドメインにします。</span><span class="sxs-lookup"><span data-stu-id="c2d70-110">The reverse proxy rules simply forward the HTTP and SOAP requests from the perimeter network to the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the intranet domain.</span></span>  
  
 <span data-ttu-id="c2d70-111">詳細については、リバース プロキシを使用して、次のトピックを参照してください。[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="c2d70-111">For more information about using a reverse proxy, see the following topics in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help:</span></span>  
  
-   <span data-ttu-id="c2d70-112">["サンプル アーキテクチャ: HTTP アダプタと SOAP アダプタ"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339)。</span><span class="sxs-lookup"><span data-stu-id="c2d70-112">["Sample Architecture: HTTP and SOAP Adapters"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339).</span></span>  
  
-   <span data-ttu-id="c2d70-113">["サンプル TMA: HTTP アダプタと SOAP アダプタ"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340)。</span><span class="sxs-lookup"><span data-stu-id="c2d70-113">["Sample TMA: HTTP and SOAP Adapters"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340).</span></span>  
  
-   <span data-ttu-id="c2d70-114">["Large Distributed Architecture"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341)。</span><span class="sxs-lookup"><span data-stu-id="c2d70-114">["Large Distributed Architecture"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341).</span></span>  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a><span data-ttu-id="c2d70-115">境界ネットワークに BizTalk Server を実行しているコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="c2d70-115">Using Computers Running BizTalk Server in the Perimeter Network</span></span>  
 <span data-ttu-id="c2d70-116">これは発行のため推奨できるアプローチではありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスまたはインターネットへの WCF サービスを実行しているコンピューターが必要とするため[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワーク内に配置します。</span><span class="sxs-lookup"><span data-stu-id="c2d70-116">This is not the preferred approach for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services or WCF services to the Internet because it requires computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be located in the perimeter network.</span></span> <span data-ttu-id="c2d70-117">ただし、リバース プロキシを境界ネットワークで使用できない場合は、この方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2d70-117">However, when a reverse proxy is not available in the perimeter network, you can use this approach.</span></span>  
  
 <span data-ttu-id="c2d70-118">この方法には、イントラネット ドメインと一方向の信頼関係に参加する、境界ネットワークのドメインが必要があります (ただし、イントラネット ドメインは、境界ネットワークのドメインを信頼しません)。</span><span class="sxs-lookup"><span data-stu-id="c2d70-118">This approach requires the perimeter network domain to enlist in a one-way trust with the intranet domain (but the intranet domain does not trust the perimeter network domain).</span></span> <span data-ttu-id="c2d70-119">IIS アプリケーション プールのホストは「BizTalk 分離ホスト ユーザー」のドメイン グループに属するイントラネット ドメイン アカウントでは、Web サービスや境界ネットワークのドメインでの WCF サービスを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2d70-119">The IIS application pools that host the Web services or WCF services in the perimeter network domain must be running under an intranet domain account that is in the "BizTalk Isolated Host Users" domain group.</span></span> <span data-ttu-id="c2d70-120">こうと、アプリケーション プールにメッセージを公開する必要な権限、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="c2d70-120">This gives the application pool the required rights to publish messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database.</span></span>  
  
 <span data-ttu-id="c2d70-121">これに合わせてファイアウォールで特定のポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2d70-121">You must open specific ports in the firewall to accommodate this.</span></span> <span data-ttu-id="c2d70-122">必要なポートの詳細については、次を参照してください。 ["ポート、受信と送信サーバーを"](http://go.microsoft.com/fwlink/?LinkId=153342) (http://go.microsoft.com/fwlink/?LinkId=153342) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="c2d70-122">For more information about the required ports, see ["Ports for the Receive and Send Servers"](http://go.microsoft.com/fwlink/?LinkId=153342) (http://go.microsoft.com/fwlink/?LinkId=153342) in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a><span data-ttu-id="c2d70-123">AppFabric Connect サービスを使用するクラウド上の BizTalk アプリケーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="c2d70-123">Exposing BizTalk Applications on the Cloud using AppFabric Connect for Services</span></span>  
 <span data-ttu-id="c2d70-124">記事を参照して[AppFabric Connect サービスを使用するクラウドに BizTalk アプリケーションを公開する](http://go.microsoft.com/fwlink/?LinkID=204700)(http://go.microsoft.com/fwlink/?LinkID=204700) の詳細については、クラウドでの WCF サービスとしての BizTalk アプリケーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="c2d70-124">See the article [Exposing BizTalk Applications on the Cloud using AppFabric Connect for Services](http://go.microsoft.com/fwlink/?LinkID=204700) (http://go.microsoft.com/fwlink/?LinkID=204700) for more information about expose BizTalk Applications as WCF Services on the cloud.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d70-125">参照</span><span class="sxs-lookup"><span data-stu-id="c2d70-125">See Also</span></span>  
 [<span data-ttu-id="c2d70-126">Web Services1 を公開するための計画</span><span class="sxs-lookup"><span data-stu-id="c2d70-126">Planning for Publishing Web Services1</span></span>](../technical-guides/planning-for-publishing-web-services1.md)