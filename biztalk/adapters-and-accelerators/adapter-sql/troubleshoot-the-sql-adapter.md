---
title: "SQL アダプターのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1be376ba-ad4c-4fa7-b94b-82bfbc8f34cc
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb8b574a372ed365a22ff9d87d40bf4ab9af8ae4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-sql-adapter"></a><span data-ttu-id="b3172-102">SQL アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="b3172-102">Troubleshoot the SQL adapter</span></span>
<span data-ttu-id="b3172-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用してまたはに限らずなど、いくつかの Microsoft テクノロジによって異なります、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]、および[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b3172-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)], and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="b3172-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築された、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、順番がありますが、[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]または[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="b3172-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="b3172-105">いずれかを使用してアプリケーションを作成して、アダプターを使用できる、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="b3172-105">The adapters can be consumed either by writing applications using the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="b3172-106">これらのテクノロジと製品に関連する問題については、それぞれのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3172-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="b3172-107">このセクションのトラブルシューティングに関する情報を提供する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]など。</span><span class="sxs-lookup"><span data-stu-id="b3172-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="b3172-108">問題を診断するアダプタを使用してトレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b3172-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="b3172-109">インストールと考えられる原因および解決方法を含む、アダプターを操作するときに発生する可能性がある運用の問題を処理しています。</span><span class="sxs-lookup"><span data-stu-id="b3172-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="b3172-110">パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。</span><span class="sxs-lookup"><span data-stu-id="b3172-110">Using performance counters to gauge adapter performance.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b3172-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b3172-111">In This Section</span></span>  
  
-   [<span data-ttu-id="b3172-112">診断トレースと SQL アダプターでメッセージのログ記録</span><span class="sxs-lookup"><span data-stu-id="b3172-112">Diagnostic Tracing and Message Logging in the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/diagnostic-tracing-and-message-logging-in-the-sql-adapter.md)  
  
-   [<span data-ttu-id="b3172-113">SQl アダプタでのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="b3172-113">Troubleshoot Installation Issues with the SQl adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-installation-issues-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="b3172-114">SQL アダプタで運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="b3172-114">Troubleshoot Operational Issues with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-operational-issues-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="b3172-115">SQL アダプターのパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b3172-115">Use Performance Counters with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)