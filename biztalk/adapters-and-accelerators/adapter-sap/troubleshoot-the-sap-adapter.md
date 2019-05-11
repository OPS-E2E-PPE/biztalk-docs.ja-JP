---
title: SAP アダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 2c554a7b-18be-4c94-8bf2-f22ac080794c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d369d76fab9c12f6f06b55187ab683252ff5f90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372311"
---
# <a name="troubleshoot-the-sap-adapter"></a><span data-ttu-id="3c5ab-102">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-102">Troubleshoot the SAP adapter</span></span>
<span data-ttu-id="3c5ab-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用して、またはこれらに限定されませんが、いくつかの Microsoft テクノロジに依存、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、および Microsoft[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]または[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="3c5ab-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、順番がありますが、[!INCLUDE[dotnet45](../../includes/dotnet45-md.md)]または[!INCLUDE[dotnet451](../../includes/dotnet451-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[dotnet45](../../includes/dotnet45-md.md)] or [!INCLUDE[dotnet451](../../includes/dotnet451-md.md)].</span></span> <span data-ttu-id="3c5ab-105">アダプターは、いずれかを使用してアプリケーションを作成して使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="3c5ab-106">これらのテクノロジや製品のそれぞれに関連する問題については、それぞれのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="3c5ab-107">このセクションのトラブルシューティングについて説明します、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]など。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="3c5ab-108">アダプターに関する問題の診断トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="3c5ab-109">インストールと考えられる原因、および解決方法を含め、アダプターを使用する場合に発生する可能性が運用上の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="3c5ab-110">アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="3c5ab-111">例外とエラー、考えられる原因、解決方法などを処理します。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3c5ab-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="3c5ab-112">In This Section</span></span>  
  
-   [<span data-ttu-id="3c5ab-113">診断トレースと SAP アダプターのメッセージ ログ</span><span class="sxs-lookup"><span data-stu-id="3c5ab-113">Diagnostic Tracing and Message Logging for the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)  
  
-   [<span data-ttu-id="3c5ab-114">SAP アダプターを使用したインストールの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-114">Troubleshoot Installation Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-installation-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="3c5ab-115">SAP アダプターを使用した運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-115">Troubleshoot Operational Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-operational-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="3c5ab-116">SAP アダプターを使用したパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-116">Troubleshoot Performance Issues with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-performance-issues-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="3c5ab-117">Data Provider for SAP に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="3c5ab-117">Troubleshoot Issues with the Data Provider for SAP</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-issues-with-the-data-provider-for-sap.md)  
  
-   [<span data-ttu-id="3c5ab-118">SAP アダプターを使用したパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c5ab-118">Use Performance Counters with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/use-performance-counters-with-the-sap-adapter.md)  
  
-   [<span data-ttu-id="3c5ab-119">例外と SAP アダプターを使用したエラーの処理</span><span class="sxs-lookup"><span data-stu-id="3c5ab-119">Exceptions and Error Handling with the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/exceptions-and-error-handling-with-the-sap-adapter.md)