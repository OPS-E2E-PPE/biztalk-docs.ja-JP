---
title: "WCF サービスを公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 00136b64d5feaf552f77b92b3ad4442da4e447cc
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/28/2018
---
# <a name="publish-wcf-services"></a><span data-ttu-id="06d90-102">WCF サービスを公開します。</span><span class="sxs-lookup"><span data-stu-id="06d90-102">Publish WCF Services</span></span>
<span data-ttu-id="06d90-103">オーケストレーションは、WCF クライアントが呼び出すための BizTalk Server で WCF サービスとして公開できます。</span><span class="sxs-lookup"><span data-stu-id="06d90-103">An orchestration can be published as a WCF service in BizTalk Server to be called by WCF clients.</span></span>  
  
## <a name="publish-wcf-services-with-the-isolated-wcf-adapters"></a><span data-ttu-id="06d90-104">分離 WCF アダプターで WCF サービスを公開します。</span><span class="sxs-lookup"><span data-stu-id="06d90-104">Publish WCF services with the isolated WCF adapters</span></span> 
  
 <span data-ttu-id="06d90-105">WCF-BasicHttp アダプター、WCF-WSHttp アダプター、WCF-CustomIsolated アダプターなどの分離 WCF アダプターに BizTalk WCF サービス公開ウィザードを使用すると、WCF サービスを作成して公開できます。</span><span class="sxs-lookup"><span data-stu-id="06d90-105">You create and publish WCF services by using the BizTalk WCF Service Publishing Wizard for the isolated WCF adapters such as the WCF-BasicHttp adapter, the WCF-WSHttp adapter, and the WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="06d90-106">これにより、IIS のプロセス外アプリケーションとして存在する受信場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="06d90-106">This creates a receive location which exists as an out of process application in IIS.</span></span>  
  
 <span data-ttu-id="06d90-107">分離 WCF アダプターを使用して WCF サービスを公開する前に、インターネット インフォメーション サービス (IIS) で WCF サービスをホストする方法について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="06d90-107">Before you publish a WCF service with the isolated WCF adapters, you should have an understanding of how to host WCF services in Internet Information Services (IIS).</span></span>  
  
## <a name="publish-service-metadata-for-the-wcf-receive-locations"></a><span data-ttu-id="06d90-108">WCF 受信場所のサービス メタデータを公開します。</span><span class="sxs-lookup"><span data-stu-id="06d90-108">Publish service metadata for the WCF receive locations</span></span>
  
 <span data-ttu-id="06d90-109">BizTalk WCF サービス公開ウィザードを使用して、公開する WCF サービス受信場所のサービス メタデータを作成できます。</span><span class="sxs-lookup"><span data-stu-id="06d90-109">You create service metadata for published WCF receive locations by using the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="06d90-110">公開されたメタデータ ドキュメントからサービス モデル コードを生成するには、Windows ソフトウェア開発キット (SDK) および .NET Framework ランタイム コンポーネントに含まれている Service Model メタデータ ユーティリティ ツール (SvcUtil.exe) を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="06d90-110">To generate service model client code from the published metadata documents you can use the Service Model Metadata Utility tool (SvcUtil.exe) included in the Windows Software Development Kit (SDK) and .NET Framework Runtime Components.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="06d90-111">BizTalk WCF サービス公開ウィザードを実行する前に、WCF サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="06d90-111">Before running the BizTalk WCF Service Publishing Wizard, you must enable WCF services.</span></span> <span data-ttu-id="06d90-112">詳細については、システム用の WCF サービスを有効にすると、次を参照してください。[分離 WCF 受信アダプタの IIS を構成する](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="06d90-112">For more information about enabling WCF services for your system, see [Configuring IIS for the Isolated WCF Receive Adapters](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="06d90-113">次の手順</span><span class="sxs-lookup"><span data-stu-id="06d90-113">Next steps</span></span>
  
-   [<span data-ttu-id="06d90-114">分離 WCF 受信アダプターでの WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="06d90-114">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="06d90-115">WCF 受信アダプタへのサービス メタデータの公開</span><span class="sxs-lookup"><span data-stu-id="06d90-115">Publishing Service Metadata for the WCF Receive Adapters</span></span>](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="06d90-116">WCF 受信アダプターで WCF サービスを公開する場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="06d90-116">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="06d90-117">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="06d90-117">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)  
  
-   [<span data-ttu-id="06d90-118">WCF サービスとして公開されたオーケストレーションからエラー例外をスローする</span><span class="sxs-lookup"><span data-stu-id="06d90-118">Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)