---
title: インターネットに接続する Web サービスと WCF サービスの発行 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e7553608-f57a-470e-91d4-75504b3fd52b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32a0478e43f87dfbf29f736fde062c67fb4a94cc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009203"
---
# <a name="publishing-internet-facing-web-services-and-wcf-services"></a><span data-ttu-id="a054d-102">インターネットに接続する Web サービスと WCF サービスの発行</span><span class="sxs-lookup"><span data-stu-id="a054d-102">Publishing Internet-facing Web Services and WCF Services</span></span>
<span data-ttu-id="a054d-103">複数のアプローチを使用して、パブリッシング用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービスをインターネット。</span><span class="sxs-lookup"><span data-stu-id="a054d-103">You can use multiple approaches for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services and WCF services to the Internet:</span></span>  
  
- <span data-ttu-id="a054d-104">リバース プロキシ ルールを使用して、境界ネットワーク (DMZ、非武装地帯、およびスクリーン サブネットとも呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="a054d-104">Use reverse proxy rules in a perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>  
  
- <span data-ttu-id="a054d-105">実行しているコンピュータ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワークのドメインに Web サービスまたは WCF サービスを発行します。</span><span class="sxs-lookup"><span data-stu-id="a054d-105">Put the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] that publish the Web services or WCF services into the perimeter network domain.</span></span>  
  
- <span data-ttu-id="a054d-106">Azure AppFabric Service Bus のリレー エンドポイントとして、Web サービスまたは WCF サービスを公開するのに BizTalk Server のクラウドの有効化の機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="a054d-106">Use BizTalk Server cloud enabler functionality to publish the Web services or WCF services as an Azure AppFabric Service Bus relay endpoint.</span></span>  
  
## <a name="using-a-reverse-proxy"></a><span data-ttu-id="a054d-107">リバース プロキシを使用します。</span><span class="sxs-lookup"><span data-stu-id="a054d-107">Using a Reverse Proxy</span></span>  
 <span data-ttu-id="a054d-108">これは、発行のため、従来のアプローチをされた[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Web サービスと WCF サービス。</span><span class="sxs-lookup"><span data-stu-id="a054d-108">This has been the traditional approach for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services and WCF services.</span></span> <span data-ttu-id="a054d-109">境界ネットワークでリバース プロキシ ルールを使用して、BizTalk サーバーを境界ネットワークにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="a054d-109">Using reverse proxy rules in the perimeter network obviates the need to have BizTalk servers located in the perimeter network.</span></span> <span data-ttu-id="a054d-110">リバース プロキシ ルール単に要求を転送、HTTP および SOAP、境界ネットワークから実行するコンピューターに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イントラネット ドメインにします。</span><span class="sxs-lookup"><span data-stu-id="a054d-110">The reverse proxy rules simply forward the HTTP and SOAP requests from the perimeter network to the computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the intranet domain.</span></span>  
  
 <span data-ttu-id="a054d-111">詳細については、リバース プロキシを使用して、BizTalk Server ヘルプで、次のトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a054d-111">For more information about using a reverse proxy, see the following topics in BizTalk Server Help:</span></span>  
  
-   <span data-ttu-id="a054d-112">["サンプル アーキテクチャ: HTTP アダプターと SOAP アダプター"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339)します。</span><span class="sxs-lookup"><span data-stu-id="a054d-112">["Sample Architecture: HTTP and SOAP Adapters"](http://go.microsoft.com/fwlink/?LinkId=153339) (http://go.microsoft.com/fwlink/?LinkId=153339).</span></span>  
  
-   <span data-ttu-id="a054d-113">["サンプル TMA: HTTP アダプターと SOAP アダプター"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340)します。</span><span class="sxs-lookup"><span data-stu-id="a054d-113">["Sample TMA: HTTP and SOAP Adapters"](http://go.microsoft.com/fwlink/?LinkId=153340) (http://go.microsoft.com/fwlink/?LinkId=153340).</span></span>  
  
-   <span data-ttu-id="a054d-114">["大規模な分散アーキテクチャ"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341)します。</span><span class="sxs-lookup"><span data-stu-id="a054d-114">["Large Distributed Architecture"](http://go.microsoft.com/fwlink/?LinkId=153341) (http://go.microsoft.com/fwlink/?LinkId=153341).</span></span>  
  
## <a name="using-computers-running-biztalk-server-in-the-perimeter-network"></a><span data-ttu-id="a054d-115">境界ネットワーク内の BizTalk Server を実行しているコンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a054d-115">Using Computers Running BizTalk Server in the Perimeter Network</span></span>  
 <span data-ttu-id="a054d-116">これは発行に対して推奨されるアプローチではありません[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]サービスまたはインターネットへの WCF サービスを実行しているコンピューターが必要とするため Web[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]境界ネットワーク内に配置します。</span><span class="sxs-lookup"><span data-stu-id="a054d-116">This is not the preferred approach for publishing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services or WCF services to the Internet because it requires computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be located in the perimeter network.</span></span> <span data-ttu-id="a054d-117">ただし、リバース プロキシが境界ネットワークで利用できない場合は、このアプローチを使用できます。</span><span class="sxs-lookup"><span data-stu-id="a054d-117">However, when a reverse proxy is not available in the perimeter network, you can use this approach.</span></span>  
  
 <span data-ttu-id="a054d-118">このアプローチには、イントラネット ドメインと一方向の信頼関係に参加する、境界ネットワークのドメインが必要があります (ただし、イントラネット ドメインでは、境界ネットワークのドメインを信頼しません)。</span><span class="sxs-lookup"><span data-stu-id="a054d-118">This approach requires the perimeter network domain to enlist in a one-way trust with the intranet domain (but the intranet domain does not trust the perimeter network domain).</span></span> <span data-ttu-id="a054d-119">IIS アプリケーション ホストとなるプール、Web サービスまたは境界ネットワークのドメインでの WCF サービスは、「BizTalk 分離ホスト ユーザー」ドメインのグループ内にあるイントラネット ドメイン アカウントで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a054d-119">The IIS application pools that host the Web services or WCF services in the perimeter network domain must be running under an intranet domain account that is in the "BizTalk Isolated Host Users" domain group.</span></span> <span data-ttu-id="a054d-120">こうと、アプリケーション プールにメッセージを発行する必要な権限、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベースです。</span><span class="sxs-lookup"><span data-stu-id="a054d-120">This gives the application pool the required rights to publish messages to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MessageBox database.</span></span>  
  
 <span data-ttu-id="a054d-121">これに合わせてファイアウォールでは、特定のポートを開く必要があります。</span><span class="sxs-lookup"><span data-stu-id="a054d-121">You must open specific ports in the firewall to accommodate this.</span></span> <span data-ttu-id="a054d-122">必要なポートの詳細については、次を参照してください。 ["ポートを、受信と送信サーバー"](http://go.microsoft.com/fwlink/?LinkId=153342) (<http://go.microsoft.com/fwlink/?LinkId=153342>) で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="a054d-122">For more information about the required ports, see ["Ports for the Receive and Send Servers"](http://go.microsoft.com/fwlink/?LinkId=153342) (<http://go.microsoft.com/fwlink/?LinkId=153342>) in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] documentation.</span></span>  
  
## <a name="exposing-biztalk-applications-on-the-cloud-using-appfabric-connect-for-services"></a><span data-ttu-id="a054d-123">サービスの AppFabric Connect を使用して、クラウド上の BizTalk アプリケーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="a054d-123">Exposing BizTalk Applications on the Cloud using AppFabric Connect for Services</span></span>  
 <span data-ttu-id="a054d-124">記事をご覧ください[サービスの AppFabric Connect を使用して、クラウドでの BizTalk アプリケーションの公開](http://go.microsoft.com/fwlink/?LinkID=204700)(http://go.microsoft.com/fwlink/?LinkID=204700)の詳細については、クラウドでの WCF サービスとしての BizTalk アプリケーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="a054d-124">See the article [Exposing BizTalk Applications on the Cloud using AppFabric Connect for Services](http://go.microsoft.com/fwlink/?LinkID=204700) (http://go.microsoft.com/fwlink/?LinkID=204700) for more information about expose BizTalk Applications as WCF Services on the cloud.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a054d-125">参照</span><span class="sxs-lookup"><span data-stu-id="a054d-125">See Also</span></span>  
 [<span data-ttu-id="a054d-126">Web Services1 を公開するための計画</span><span class="sxs-lookup"><span data-stu-id="a054d-126">Planning for Publishing Web Services1</span></span>](../technical-guides/planning-for-publishing-web-services1.md)