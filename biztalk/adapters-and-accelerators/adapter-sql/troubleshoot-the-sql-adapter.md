---
title: SQL アダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1be376ba-ad4c-4fa7-b94b-82bfbc8f34cc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6992b62630fab4c2f4d8235f493fd45c2bcbb48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367458"
---
# <a name="troubleshoot-the-sql-adapter"></a><span data-ttu-id="f55c6-102">SQL アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="f55c6-102">Troubleshoot the SQL adapter</span></span>
<span data-ttu-id="f55c6-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用して、またはこれらに限定されませんが、いくつかの Microsoft テクノロジに依存、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]、および[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f55c6-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)], and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="f55c6-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、順番がありますが、[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]または[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f55c6-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="f55c6-105">アダプターは、いずれかを使用してアプリケーションを作成して使用できる、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="f55c6-105">The adapters can be consumed either by writing applications using the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="f55c6-106">これらのテクノロジや製品のそれぞれに関連する問題については、それぞれのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f55c6-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="f55c6-107">このセクションのトラブルシューティングについて説明します、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]など。</span><span class="sxs-lookup"><span data-stu-id="f55c6-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="f55c6-108">アダプターに関する問題の診断トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f55c6-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="f55c6-109">インストールと考えられる原因、および解決方法を含め、アダプターを使用する場合に発生する可能性が運用上の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="f55c6-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="f55c6-110">アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f55c6-110">Using performance counters to gauge adapter performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f55c6-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f55c6-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f55c6-112">診断トレースと SQL アダプターでメッセージのログ記録</span><span class="sxs-lookup"><span data-stu-id="f55c6-112">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)  
  
-   [<span data-ttu-id="f55c6-113">SQl アダプターを使用したインストールの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="f55c6-113">Troubleshoot Installation Issues with the SQl adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-installation-issues-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="f55c6-114">SQL アダプターを使用した運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="f55c6-114">Troubleshoot Operational Issues with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="f55c6-115">SQL アダプターを使用したパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="f55c6-115">Use Performance Counters with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)