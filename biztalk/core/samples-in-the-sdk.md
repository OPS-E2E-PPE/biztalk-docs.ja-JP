---
title: SDK のサンプル |Microsoft Docs
description: アダプター、アプリケーションの展開、BAM、ビジネス ルール、オーケストレーション、パイプライン、および BizTalk Server で使用できる他の SDK サンプル
ms.custom: ''
ms.date: 10/17/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53bca653-e604-4452-8805-72632d3397c2
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f33d291893fe46cae5a083adf96a52da8e848b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395579"
---
# <a name="samples-in-the-sdk"></a><span data-ttu-id="2d462-103">SDK 内のサンプル</span><span class="sxs-lookup"><span data-stu-id="2d462-103">Samples in the SDK</span></span>

## <a name="folder-paths"></a><span data-ttu-id="2d462-104">フォルダーのパス</span><span class="sxs-lookup"><span data-stu-id="2d462-104">Folder paths</span></span>
<span data-ttu-id="2d462-105">このセクションでは、Microsoft では含まれている 30 以上のサンプルをについて説明します[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ソフトウェア開発キット (SDK)。</span><span class="sxs-lookup"><span data-stu-id="2d462-105">This section describes more than 30 samples included in the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Software Development Kit (SDK).</span></span> <span data-ttu-id="2d462-106">サンプル、これを実行する方法、および期待する結果を構築するための手順を含む、各サンプルについて詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="2d462-106">The section provides detailed information about each sample, including instructions for building the sample, how to run it, and what results to expect.</span></span>  

 <span data-ttu-id="2d462-107">サンプル ドキュメント パスの省略形を使用して\<*サンプル パス*\>をサンプルのインストールへのパスを示すためにします。</span><span class="sxs-lookup"><span data-stu-id="2d462-107">The samples documentation uses the path abbreviation \<*Samples Path*\> to denote the path to the samples in your installation.</span></span> <span data-ttu-id="2d462-108">パスの既定値は、インストール中に行われた決定によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2d462-108">The default for the path can vary based on decisions made during installation.</span></span> <span data-ttu-id="2d462-109">次の表は、一般的なインストール シナリオの既定のパスを提供します。</span><span class="sxs-lookup"><span data-stu-id="2d462-109">The following table provides the default path for common installation scenarios.</span></span>  


|            <span data-ttu-id="2d462-110">説明</span><span class="sxs-lookup"><span data-stu-id="2d462-110">Description</span></span>             |                                            <span data-ttu-id="2d462-111">パス</span><span class="sxs-lookup"><span data-stu-id="2d462-111">Path</span></span>                                            |
|------------------------------------|--------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2d462-112">32 ビット プラットフォームでのインストール</span><span class="sxs-lookup"><span data-stu-id="2d462-112">Installation on 32-bit platform</span></span>   |    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="2d462-113">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="2d462-113">\SDK\Samples</span></span>    |
| <span data-ttu-id="2d462-114">64 ビット プラットフォームでインストールします。</span><span class="sxs-lookup"><span data-stu-id="2d462-114">Installation on a 64-bit platform.</span></span> | [!INCLUDE[btsBizTalkServerPathx64](../includes/btsbiztalkserverpathx64-md.md)]<span data-ttu-id="2d462-115">\SDK\Samples</span><span class="sxs-lookup"><span data-stu-id="2d462-115">\SDK\Samples</span></span> |

> [!IMPORTANT]
>  <span data-ttu-id="2d462-116">わかりやすく、サンプルでは、この SDK では、およびこのドキュメントでは、1 台のコンピューター開発者向けに BizTalk Server のインストールを使用していることを想定しています。</span><span class="sxs-lookup"><span data-stu-id="2d462-116">For the sake of simplicity, the samples in this SDK, and this documentation, assume that you are using a single computer developer installation of BizTalk Server.</span></span> <span data-ttu-id="2d462-117">完全なインストールを実行していない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、一部のサンプルが正常に動作しない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2d462-117">If you do not perform a complete installation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], some samples may not work properly.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="2d462-118">すべての[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]SDK 項目は、英語で提供され、英語版のインストールについてのみサポートされます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2d462-118">All of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK items are provided in English and are supported only for English-language installations of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  

## <a name="available-samples"></a><span data-ttu-id="2d462-119">使用可能なサンプル</span><span class="sxs-lookup"><span data-stu-id="2d462-119">Available samples</span></span> 

-   [<span data-ttu-id="2d462-120">アダプタ サンプル - 開発</span><span class="sxs-lookup"><span data-stu-id="2d462-120">Adapter Samples - Development</span></span>](../core/adapter-samples-development.md)  

-   [<span data-ttu-id="2d462-121">アダプタ サンプル – 使用法</span><span class="sxs-lookup"><span data-stu-id="2d462-121">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)  

-   [<span data-ttu-id="2d462-122">Admin (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-122">Admin (BizTalk Server Samples Folder)</span></span>](../core/admin-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-123">アプリケーションの展開 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-123">Application Deployment (BizTalk Server Samples Folder)</span></span>](../core/application-deployment-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-124">ビジネス アクティビティの監視 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-124">Business Activity Monitoring (BizTalk Server Samples Folder)</span></span>](../core/business-activity-monitoring-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-125">ビジネス ルール (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-125">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-126">EDI および AS2 (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-126">EDI and AS2 (BizTalk Server Samples Folder)</span></span>](../core/edi-and-as2-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-127">Messaging (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-127">Messaging (BizTalk Server Samples Folder)</span></span>](../core/messaging-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-128">オーケストレーション (BizTalk Server サンプル フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-128">Orchestrations (BizTalk Server Samples Folder)</span></span>](../core/orchestrations-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-129">パイプライン (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-129">Pipelines (BizTalk Server Samples Folder)</span></span>](../core/pipelines-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-130">SSO (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-130">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)  

-   [<span data-ttu-id="2d462-131">XML ツール (BizTalk Server Samples フォルダー)</span><span class="sxs-lookup"><span data-stu-id="2d462-131">XML Tools (BizTalk Server Samples Folder)</span></span>](../core/xml-tools-biztalk-server-samples-folder.md)