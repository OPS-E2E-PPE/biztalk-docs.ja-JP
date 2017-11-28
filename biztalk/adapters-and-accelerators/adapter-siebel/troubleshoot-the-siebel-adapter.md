---
title: "Siebel アダプターのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: de11ffe3-3622-40df-b9c5-11c96f8460e0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e12b877eaabb629bb9e9e1da81cf5343e1780cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-siebel-adapter"></a><span data-ttu-id="d145c-102">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d145c-102">Troubleshoot the Siebel adapter</span></span>
<span data-ttu-id="d145c-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用してまたはに限らずなど、さまざまな Microsoft テクノロジに依存[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、および Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] /[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d145c-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several different Microsoft technologies including but not limited to [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]/[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="d145c-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築された、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、さらに必要がある[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]と[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="d145c-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] and [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="d145c-105">いずれかを使用してアプリケーションを作成して、アダプターを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="d145c-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="d145c-106">これらのテクノロジと製品に関連する問題については、それぞれのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d145c-106">For issues related to each of these technologies and products, refer to the respective documentation.</span></span>  
  
 <span data-ttu-id="d145c-107">このセクションのトラブルシューティングに関する情報を提供する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]など。</span><span class="sxs-lookup"><span data-stu-id="d145c-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="d145c-108">問題を診断するアダプタを使用してトレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d145c-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="d145c-109">インストールと考えられる原因および解決方法を含む、アダプターを操作するときに発生する可能性がある運用の問題を処理しています。</span><span class="sxs-lookup"><span data-stu-id="d145c-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="d145c-110">パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。</span><span class="sxs-lookup"><span data-stu-id="d145c-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="d145c-111">例外と考えられる原因と解決方法を含む、エラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="d145c-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d145c-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="d145c-112">In This Section</span></span>  
  
-   [<span data-ttu-id="d145c-113">診断トレースと Siebel アダプターのメッセージ ログ</span><span class="sxs-lookup"><span data-stu-id="d145c-113">Diagnostic Tracing and Message Logging for the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="d145c-114">Siebel アダプターのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d145c-114">Troubleshoot Installation Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-installation-issues-with-the-siebel-adapter.md) 
  
-   [<span data-ttu-id="d145c-115">Siebel アダプターでの運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d145c-115">Troubleshoot Operational Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-operational-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="d145c-116">Siebel アダプターのパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d145c-116">Troubleshoot Performance Issues with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-performance-issues-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="d145c-117">Data Provider 用 Siebel に関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d145c-117">Troubleshoot Issues with the Data Provider for Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-issues-with-the-data-provider-for-siebel.md) 
  
-   [<span data-ttu-id="d145c-118">Siebel アダプターのパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="d145c-118">Use Performance Counters with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/use-performance-counters-with-the-siebel-adapter.md)  
  
-   [<span data-ttu-id="d145c-119">例外とエラーの Siebel アダプターの処理</span><span class="sxs-lookup"><span data-stu-id="d145c-119">Exceptions and Error Handling with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/exceptions-and-error-handling-with-the-siebel-adapter.md)