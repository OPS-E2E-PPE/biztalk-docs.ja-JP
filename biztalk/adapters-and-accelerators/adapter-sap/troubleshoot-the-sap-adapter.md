---
title: "SAP アダプターのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: 2c554a7b-18be-4c94-8bf2-f22ac080794c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1994f7c2d6d32dc394783a68edb91532118434aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-sap-adapter"></a><span data-ttu-id="519b5-102">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="519b5-102">Troubleshoot the SAP adapter</span></span>
<span data-ttu-id="519b5-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用してまたはに限らずなど、いくつかの Microsoft テクノロジによって異なります、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、および Microsoft[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]または[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="519b5-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="519b5-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築された、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、順番がありますが、[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]または[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="519b5-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="519b5-105">いずれかを使用してアプリケーションを作成して、アダプターを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="519b5-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="519b5-106">これらのテクノロジと製品に関連する問題については、それぞれのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="519b5-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="519b5-107">このセクションのトラブルシューティングに関する情報を提供する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]など。</span><span class="sxs-lookup"><span data-stu-id="519b5-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="519b5-108">問題を診断するアダプタを使用してトレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="519b5-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="519b5-109">インストールと考えられる原因および解決方法を含む、アダプターを操作するときに発生する可能性がある運用の問題を処理しています。</span><span class="sxs-lookup"><span data-stu-id="519b5-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="519b5-110">パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。</span><span class="sxs-lookup"><span data-stu-id="519b5-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="519b5-111">例外と考えられる原因と解決方法を含む、エラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="519b5-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="519b5-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="519b5-112">In This Section</span></span>  
  
-   [<span data-ttu-id="519b5-113">診断トレースと SAP アダプターのメッセージ ログ</span><span class="sxs-lookup"><span data-stu-id="519b5-113">Diagnostic Tracing and Message Logging for the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)  
  
-   [<span data-ttu-id="519b5-114">SAP アダプターでのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="519b5-114">Troubleshoot Installation Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-installation-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="519b5-115">SAP アダプターでの運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="519b5-115">Troubleshoot Operational Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="519b5-116">SAP アダプターを使用したパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="519b5-116">Troubleshoot Performance Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-performance-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="519b5-117">Data Provider 用 SAP に関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="519b5-117">Troubleshoot Issues with the Data Provider for SAP</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-issues-with-the-data-provider-for-sap.md)  
  
-   [<span data-ttu-id="519b5-118">SAP アダプターのパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="519b5-118">Use Performance Counters with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="519b5-119">例外とエラーは、SAP アダプターの処理</span><span class="sxs-lookup"><span data-stu-id="519b5-119">Exceptions and Error Handling with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)