---
title: サンプル シナリオの脅威モデル分析 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TMA, security
- security examples [TMA]
- TMA, examples
- examples, TMA
ms.assetid: e35d1d7f-a71a-42f5-b1f4-fe3234ba7686
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afc1e375945ec7b40c56274adc5e18cb1ee67f97
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269114"
---
# <a name="sample-scenarios-for-threat-model-analysis"></a><span data-ttu-id="9e648-102">脅威モデル分析のサンプル シナリオ</span><span class="sxs-lookup"><span data-stu-id="9e648-102">Sample Scenarios for Threat Model Analysis</span></span>
<span data-ttu-id="9e648-103">このセクションで識別される、サンプル アーキテクチャの各使用シナリオの手順を実行し、脅威モデル分析 (TMA) の結果を示します[小さな & Medium-Sized 企業向けのサンプル アーキテクチャ](../core/sample-architectures-for-small-medium-sized-companies.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e648-103">This section provides the steps and results of a threat model analysis (TMA) for each usage scenario for the sample architecture identified in [Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md).</span></span> <span data-ttu-id="9e648-104">このセクションの目的は、TMA の手順を示すことです。</span><span class="sxs-lookup"><span data-stu-id="9e648-104">The purpose of this section is to show you the steps of a TMA.</span></span> <span data-ttu-id="9e648-105">TMA の動作を理解するのに役立ち、サンプル アプリケーションで特定された潜在的な脅威、およびその脅威の影響を軽減するための推奨方法についての説明もあります。</span><span class="sxs-lookup"><span data-stu-id="9e648-105">This helps you understand how a TMA works, and describes for you the potential threats we identified for the sample architecture and how we recommend that you reduce their effect.</span></span>  
  
 <span data-ttu-id="9e648-106">使用シナリオは Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用できるさまざまなアダプタと、エンタープライズ シングル サインオンの使用に基づいて分類してあります。</span><span class="sxs-lookup"><span data-stu-id="9e648-106">We categorize the usage scenarios based on the different adapters you can use with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and the use of Enterprise Single-Sign On.</span></span>  
  
 <span data-ttu-id="9e648-107">各シナリオでは、次の手順に従って脅威モデル分析を行いました。</span><span class="sxs-lookup"><span data-stu-id="9e648-107">For each scenario, we followed these steps to complete the Threat Model Analysis:</span></span>  
  
-   <span data-ttu-id="9e648-108">背景情報の収集</span><span class="sxs-lookup"><span data-stu-id="9e648-108">Collect background information</span></span>  
  
-   <span data-ttu-id="9e648-109">脅威モデルの作成と分析</span><span class="sxs-lookup"><span data-stu-id="9e648-109">Create and analyze the threat model</span></span>  
  
-   <span data-ttu-id="9e648-110">脅威の確認</span><span class="sxs-lookup"><span data-stu-id="9e648-110">Review threats</span></span>  
  
-   <span data-ttu-id="9e648-111">緩和方法とテクノロジの特定</span><span class="sxs-lookup"><span data-stu-id="9e648-111">Identify mitigation techniques and technologies</span></span>  
  
 <span data-ttu-id="9e648-112">脅威モデル分析の詳細を参照してください。[脅威モデル分析](../core/threat-model-analysis.md)です。</span><span class="sxs-lookup"><span data-stu-id="9e648-112">For more information Threat Model Analysis, see [Threat Model Analysis](../core/threat-model-analysis.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e648-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="9e648-113">In This Section</span></span>  
  
-   [<span data-ttu-id="9e648-114">サンプル シナリオの背景情報</span><span class="sxs-lookup"><span data-stu-id="9e648-114">Background Information for Sample Scenarios</span></span>](../core/background-information-for-sample-scenarios.md)  
  
-   [<span data-ttu-id="9e648-115">サンプル TMA: HTTP アダプタと SOAP アダプタ</span><span class="sxs-lookup"><span data-stu-id="9e648-115">Sample TMA: HTTP and SOAP Adapters</span></span>](../core/sample-tma-http-and-soap-adapters.md)  
  
-   [<span data-ttu-id="9e648-116">サンプル TMA: BizTalk メッセージ キュー アダプタ</span><span class="sxs-lookup"><span data-stu-id="9e648-116">Sample TMA: BizTalk Message Queuing Adapter</span></span>](../core/sample-tma-biztalk-message-queuing-adapter.md)  
  
-   [<span data-ttu-id="9e648-117">サンプル TMA: ファイル アダプタ</span><span class="sxs-lookup"><span data-stu-id="9e648-117">Sample TMA: File Adapter</span></span>](../core/sample-tma-file-adapter.md)  
  
-   [<span data-ttu-id="9e648-118">サンプル TMA: FTP アダプター</span><span class="sxs-lookup"><span data-stu-id="9e648-118">Sample TMA: FTP Adapter</span></span>](../core/sample-tma-ftp-adapter.md)  
  
-   [<span data-ttu-id="9e648-119">サンプル TMA: エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9e648-119">Sample TMA: Enterprise Single Sign-On</span></span>](../core/sample-tma-enterprise-single-sign-on.md)