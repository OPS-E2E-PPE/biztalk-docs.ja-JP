---
title: "WCF サービスの公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF services, publishing
ms.assetid: 70b7851b-77c1-4ab3-a61f-e7165ceb56fb
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5f72f2b300738f2e9a1a643e152048b64cf8f55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="publishing-wcf-services"></a><span data-ttu-id="c61ed-102">WCF サービスの公開</span><span class="sxs-lookup"><span data-stu-id="c61ed-102">Publishing WCF Services</span></span>
<span data-ttu-id="c61ed-103">オーケストレーションでの WCF サービスとして公開できます[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] WCF クライアントによって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="c61ed-103">An orchestration can be published as a WCF service in [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to be called by WCF clients.</span></span>  
  
 <span data-ttu-id="c61ed-104">**分離 WCF アダプターで WCF サービスの公開**</span><span class="sxs-lookup"><span data-stu-id="c61ed-104">**Publishing WCF services with the isolated WCF adapters**</span></span>  
  
 <span data-ttu-id="c61ed-105">WCF-BasicHttp アダプター、WCF-WSHttp アダプター、WCF-CustomIsolated アダプターなどの分離 WCF アダプターに BizTalk WCF サービス公開ウィザードを使用すると、WCF サービスを作成して公開できます。</span><span class="sxs-lookup"><span data-stu-id="c61ed-105">You create and publish WCF services by using the BizTalk WCF Service Publishing Wizard for the isolated WCF adapters such as the WCF-BasicHttp adapter, the WCF-WSHttp adapter, and the WCF-CustomIsolated adapter.</span></span> <span data-ttu-id="c61ed-106">これにより、IIS のプロセス外アプリケーションとして存在する受信場所が作成されます。</span><span class="sxs-lookup"><span data-stu-id="c61ed-106">This creates a receive location which exists as an out of process application in IIS.</span></span>  
  
 <span data-ttu-id="c61ed-107">分離 WCF アダプターを使用して WCF サービスを公開する前に、インターネット インフォメーション サービス (IIS) で WCF サービスをホストする方法について理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="c61ed-107">Before you publish a WCF service with the isolated WCF adapters, you should have an understanding of how to host WCF services in Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="c61ed-108">**WCF 受信場所のサービス メタデータの公開**</span><span class="sxs-lookup"><span data-stu-id="c61ed-108">**Publishing service metadata for the WCF receive locations**</span></span>  
  
 <span data-ttu-id="c61ed-109">BizTalk WCF サービス公開ウィザードを使用して、公開する WCF サービス受信場所のサービス メタデータを作成できます。</span><span class="sxs-lookup"><span data-stu-id="c61ed-109">You create service metadata for published WCF receive locations by using the BizTalk WCF Service Publishing Wizard.</span></span> <span data-ttu-id="c61ed-110">公開されたメタデータ ドキュメントからサービス モデル コードを生成するに含まれている Service Model メタデータ ユーティリティ ツール (SvcUtil.exe) を使用することができます、 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]ソフトウェア開発キット (SDK) の[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]と[!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)]ランタイム コンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="c61ed-110">To generate service model client code from the published metadata documents you can use the Service Model Metadata Utility tool (SvcUtil.exe) included in the [!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] Software Development Kit (SDK) for [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] and [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Runtime Components.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c61ed-111">BizTalk WCF サービス公開ウィザードを実行する前に、WCF サービスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c61ed-111">Before running the BizTalk WCF Service Publishing Wizard, you must enable WCF services.</span></span> <span data-ttu-id="c61ed-112">詳細については、システム用の WCF サービスを有効にすると、次を参照してください。[分離 WCF 受信アダプタの IIS を構成する](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)です。</span><span class="sxs-lookup"><span data-stu-id="c61ed-112">For more information about enabling WCF services for your system, see [Configuring IIS for the Isolated WCF Receive Adapters](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c61ed-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c61ed-113">In This Section</span></span>  
  
-   [<span data-ttu-id="c61ed-114">発行の WCF サービスを分離 WCF 受信アダプター</span><span class="sxs-lookup"><span data-stu-id="c61ed-114">Publishing WCF Services with the Isolated WCF Receive Adapters</span></span>](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="c61ed-115">受信アダプターの wcf サービス メタデータの公開</span><span class="sxs-lookup"><span data-stu-id="c61ed-115">Publishing Service Metadata for the WCF Receive Adapters</span></span>](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="c61ed-116">受信アダプターの WCF での WCF サービスを発行するときの考慮事項</span><span class="sxs-lookup"><span data-stu-id="c61ed-116">Considerations When Publishing WCF Services with the WCF Receive Adapters</span></span>](../core/considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters.md)  
  
-   [<span data-ttu-id="c61ed-117">公開済み WCF サービスでの SOAP ヘッダー</span><span class="sxs-lookup"><span data-stu-id="c61ed-117">SOAP Headers with Published WCF Services</span></span>](../core/soap-headers-with-published-wcf-services.md)  
  
-   [<span data-ttu-id="c61ed-118">WCF サービスとして公開されたオーケストレーションからエラー例外をスローする方法</span><span class="sxs-lookup"><span data-stu-id="c61ed-118">How to Throw Fault Exceptions from Orchestrations Published as WCF Services</span></span>](../core/how-to-throw-fault-exceptions-from-orchestrations-published-as-wcf-services.md)