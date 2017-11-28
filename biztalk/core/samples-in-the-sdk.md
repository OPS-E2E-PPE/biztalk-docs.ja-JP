---
title: "SDK のサンプル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, SDK
- SDK examples
- examples
ms.assetid: 53bca653-e604-4452-8805-72632d3397c2
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42429ed2aa9b6a074a62e472ca804caad676f84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="samples-in-the-sdk"></a><span data-ttu-id="8cfa0-102">SDK のサンプル</span><span class="sxs-lookup"><span data-stu-id="8cfa0-102">Samples in the SDK</span></span>
## <a name="folder-paths"></a><span data-ttu-id="8cfa0-103">フォルダーのパス</span><span class="sxs-lookup"><span data-stu-id="8cfa0-103">Folder paths</span></span>
<span data-ttu-id="8cfa0-104">このセクションには、Microsoft では含まれている 30 以上のサンプルがについて説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソフトウェア開発キット (SDK)。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-104">This section describes more than 30 samples included in the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK).</span></span> <span data-ttu-id="8cfa0-105">ここでは、サンプルの構築手順、実行方法、および予想される実行結果など、各サンプルについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-105">The section provides detailed information about each sample, including instructions for building the sample, how to run it, and what results to expect.</span></span>  
  
 <span data-ttu-id="8cfa0-106">サンプル ドキュメント パスの省略形を使用して\<*サンプル パス*> をインストールのサンプルへのパスを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-106">The samples documentation uses the path abbreviation \<*Samples Path*> to denote the path to the samples in your installation.</span></span> <span data-ttu-id="8cfa0-107">パスの既定値は、インストール時の判断によって変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-107">The default for the path can vary based on decisions made during installation.</span></span> <span data-ttu-id="8cfa0-108">次の表に、一般的なインストール シナリオの既定のパスを示します。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-108">The following table provides the default path for common installation scenarios.</span></span>  
  
|<span data-ttu-id="8cfa0-109">Description</span><span class="sxs-lookup"><span data-stu-id="8cfa0-109">Description</span></span>|<span data-ttu-id="8cfa0-110">[パス]</span><span class="sxs-lookup"><span data-stu-id="8cfa0-110">Path</span></span>|  
|-----------------|----------|  
|<span data-ttu-id="8cfa0-111">32 ビット プラットフォームでのインストール</span><span class="sxs-lookup"><span data-stu-id="8cfa0-111">Installation on 32-bit platform</span></span>|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="8cfa0-112">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="8cfa0-112">\SDK\Samples</span></span>|  
|<span data-ttu-id="8cfa0-113">64 ビット プラットフォームでのインストール</span><span class="sxs-lookup"><span data-stu-id="8cfa0-113">Installation on a 64-bit platform.</span></span>|[!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]<span data-ttu-id="8cfa0-114">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="8cfa0-114">\SDK\Samples</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="8cfa0-115">説明を簡略化するために、この SDK 内のサンプル、およびこのドキュメントでは、単一のコンピューターに、開発者向けに BizTalk Server がインストールされた状態を前提としています。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-115">For the sake of simplicity, the samples in this SDK, and this documentation, assume that you are using a single computer developer installation of BizTalk Server.</span></span> <span data-ttu-id="8cfa0-116">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の完全インストールを実行していない場合は、一部のサンプルが正常に機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-116">If you do not perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some samples may not work properly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8cfa0-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK のすべての項目は、英語で示されており、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の英語版インストールについてのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-117">All of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK items are provided in English and are supported only for English-language installations of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="available-samples"></a><span data-ttu-id="8cfa0-118">使用可能なサンプル</span><span class="sxs-lookup"><span data-stu-id="8cfa0-118">Available samples</span></span> 
  
-   [<span data-ttu-id="8cfa0-119">多数のサンプルします。</span><span class="sxs-lookup"><span data-stu-id="8cfa0-119">Get More Samples</span></span>](../core/get-more-samples.md)  
  
-   [<span data-ttu-id="8cfa0-120">アダプタ サンプル - 開発</span><span class="sxs-lookup"><span data-stu-id="8cfa0-120">Adapter Samples - Development</span></span>](../core/adapter-samples-development.md)  
  
-   [<span data-ttu-id="8cfa0-121">アダプタ サンプル – 使用状況</span><span class="sxs-lookup"><span data-stu-id="8cfa0-121">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)  
  
-   [<span data-ttu-id="8cfa0-122">管理者 (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-122">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-123">アプリケーションの展開 (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-123">Application Deployment (BizTalk Server Samples Folder)</span></span>](../core/application-deployment-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-124">ビジネス アクティビティ監視 (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-124">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-125">ビジネス ルール (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-125">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-126">EDI および AS2 (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-126">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-127">メッセージングの (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-127">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-128">オーケストレーション (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-128">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-129">パイプライン (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-129">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-130">SSO (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-130">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="8cfa0-131">XML ツール (BizTalk Server Samples フォルダ)</span><span class="sxs-lookup"><span data-stu-id="8cfa0-131">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)