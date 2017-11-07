---
title: "SDK サンプルの |Microsoft ドキュメント"
description: "アダプター、アプリケーションの展開、BAM、ビジネス ルール、オーケストレーション、パイプライン、および BizTalk Server で使用可能な複数の SDK サンプル"
ms.custom: 
ms.date: 10/17/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53bca653-e604-4452-8805-72632d3397c2
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5181c501543c1dc1518665a55f4429ae12b4cf06
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="samples-in-the-sdk"></a><span data-ttu-id="e8d3e-103">SDK のサンプル</span><span class="sxs-lookup"><span data-stu-id="e8d3e-103">Samples in the SDK</span></span>

## <a name="folder-paths"></a><span data-ttu-id="e8d3e-104">フォルダーのパス</span><span class="sxs-lookup"><span data-stu-id="e8d3e-104">Folder paths</span></span>
<span data-ttu-id="e8d3e-105">このセクションには、Microsoft では含まれている 30 以上のサンプルがについて説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソフトウェア開発キット (SDK)。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-105">This section describes more than 30 samples included in the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK).</span></span> <span data-ttu-id="e8d3e-106">ここでは、サンプルの構築手順、実行方法、および予想される実行結果など、各サンプルについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-106">The section provides detailed information about each sample, including instructions for building the sample, how to run it, and what results to expect.</span></span>  
  
 <span data-ttu-id="e8d3e-107">サンプル ドキュメント パスの省略形を使用して\<*サンプル パス*> をインストールのサンプルへのパスを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-107">The samples documentation uses the path abbreviation \<*Samples Path*> to denote the path to the samples in your installation.</span></span> <span data-ttu-id="e8d3e-108">パスの既定値は、インストール時の判断によって変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-108">The default for the path can vary based on decisions made during installation.</span></span> <span data-ttu-id="e8d3e-109">次の表に、一般的なインストール シナリオの既定のパスを示します。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-109">The following table provides the default path for common installation scenarios.</span></span>  
  
|<span data-ttu-id="e8d3e-110">Description</span><span class="sxs-lookup"><span data-stu-id="e8d3e-110">Description</span></span>|<span data-ttu-id="e8d3e-111">[パス]</span><span class="sxs-lookup"><span data-stu-id="e8d3e-111">Path</span></span>|  
|-----------------|----------|  
|<span data-ttu-id="e8d3e-112">32 ビット プラットフォームでのインストール</span><span class="sxs-lookup"><span data-stu-id="e8d3e-112">Installation on 32-bit platform</span></span>|[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="e8d3e-113">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="e8d3e-113">\SDK\Samples</span></span>|  
|<span data-ttu-id="e8d3e-114">64 ビット プラットフォームでのインストール</span><span class="sxs-lookup"><span data-stu-id="e8d3e-114">Installation on a 64-bit platform.</span></span>|[!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]<span data-ttu-id="e8d3e-115">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="e8d3e-115">\SDK\Samples</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8d3e-116">説明を簡略化するために、この SDK 内のサンプル、およびこのドキュメントでは、単一のコンピューターに、開発者向けに BizTalk Server がインストールされた状態を前提としています。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-116">For the sake of simplicity, the samples in this SDK, and this documentation, assume that you are using a single computer developer installation of BizTalk Server.</span></span> <span data-ttu-id="e8d3e-117">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の完全インストールを実行していない場合は、一部のサンプルが正常に機能しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-117">If you do not perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some samples may not work properly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8d3e-118">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK のすべての項目は、英語で示されており、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の英語版インストールについてのみサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e8d3e-118">All of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK items are provided in English and are supported only for English-language installations of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="available-samples"></a><span data-ttu-id="e8d3e-119">使用可能なサンプル</span><span class="sxs-lookup"><span data-stu-id="e8d3e-119">Available samples</span></span> 
  
-   [<span data-ttu-id="e8d3e-120">アダプタ サンプル - 開発</span><span class="sxs-lookup"><span data-stu-id="e8d3e-120">Adapter Samples - Development</span></span>](../core/adapter-samples-development.md)  
  
-   [<span data-ttu-id="e8d3e-121">アダプタ サンプル – 使用法</span><span class="sxs-lookup"><span data-stu-id="e8d3e-121">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)  
  
-   [<span data-ttu-id="e8d3e-122">Admin (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-122">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-123">アプリケーションの展開 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-123">Application Deployment (BizTalk Server Samples Folder)</span></span>](../core/application-deployment-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-124">ビジネス アクティビティの監視 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-124">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-125">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-125">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-126">EDI および AS2 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-126">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-127">Messaging (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-127">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-128">オーケストレーション (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-128">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-129">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-129">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-130">SSO (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-130">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8d3e-131">XML ツール (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="e8d3e-131">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)