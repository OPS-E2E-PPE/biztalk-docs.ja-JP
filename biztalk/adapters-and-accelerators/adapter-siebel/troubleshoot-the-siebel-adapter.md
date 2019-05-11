---
title: Siebel アダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: de11ffe3-3622-40df-b9c5-11c96f8460e0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7474b75319dabe1f04a51df24ffe952b723fa624
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370390"
---
# <a name="troubleshoot-the-siebel-adapter"></a><span data-ttu-id="3b58b-102">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3b58b-102">Troubleshoot the Siebel adapter</span></span>
<span data-ttu-id="3b58b-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用して、これらに限定されませんが、さまざまな Microsoft テクノロジに依存または[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、および Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] /[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3b58b-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several different Microsoft technologies including but not limited to [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]/[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="3b58b-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、さらに必要がある[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]と[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3b58b-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="3b58b-105">アダプターは、いずれかを使用してアプリケーションを作成して使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="3b58b-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="3b58b-106">これらのテクノロジや製品のそれぞれに関連する問題については、それぞれのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b58b-106">For issues related to each of these technologies and products, refer to the respective documentation.</span></span>  
  
 <span data-ttu-id="3b58b-107">このセクションのトラブルシューティングについて説明します、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]など。</span><span class="sxs-lookup"><span data-stu-id="3b58b-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="3b58b-108">アダプターに関する問題の診断トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3b58b-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="3b58b-109">インストールと考えられる原因、および解決方法を含め、アダプターを使用する場合に発生する可能性が運用上の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="3b58b-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="3b58b-110">アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b58b-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="3b58b-111">例外とエラー、考えられる原因、解決方法などを処理します。</span><span class="sxs-lookup"><span data-stu-id="3b58b-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b58b-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3b58b-112">In This Section</span></span>  
  
-   [<span data-ttu-id="3b58b-113">診断トレースとメッセージ ログの Siebel アダプターの</span><span class="sxs-lookup"><span data-stu-id="3b58b-113">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="3b58b-114">Siebel アダプターのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3b58b-114">Troubleshoot Installation Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-installation-issues-with-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="3b58b-115">Siebel アダプターを使用した運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3b58b-115">Troubleshoot Operational Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="3b58b-116">Siebel アダプターを使用したパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3b58b-116">Troubleshoot Performance Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-performance-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="3b58b-117">Data Provider for Siebel での問題に対するトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3b58b-117">Troubleshoot Issues with the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-issues-with-the-data-provider-for-siebel.md) 
  
-   [<span data-ttu-id="3b58b-118">Siebel アダプターを使用したパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3b58b-118">Use Performance Counters with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="3b58b-119">例外とエラーの Siebel アダプターの処理</span><span class="sxs-lookup"><span data-stu-id="3b58b-119">Exceptions and Error Handling with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)