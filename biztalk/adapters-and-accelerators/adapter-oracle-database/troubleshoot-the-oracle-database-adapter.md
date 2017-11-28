---
title: "Oracle データベース アダプターのトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: 2a3da42b-413b-479a-90d2-02f262abff41
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f3cf2e8c5f9a3f0baa743f86eaf6527ed9847019
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-the-oracle-database-adapter"></a><span data-ttu-id="73be0-102">Oracle データベース アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="73be0-102">Troubleshoot the Oracle Database adapter</span></span>
<span data-ttu-id="73be0-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用してまたはに限らずなど、いくつかの Microsoft テクノロジによって異なります、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、および Microsoft[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="73be0-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="73be0-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築された、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、順番がありますが、[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="73be0-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="73be0-105">いずれかを使用してアプリケーションを作成して、アダプターを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="73be0-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="73be0-106">これらのテクノロジと製品に関連する問題については、それぞれのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="73be0-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="73be0-107">このセクションのトラブルシューティングに関する情報を提供する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]など。</span><span class="sxs-lookup"><span data-stu-id="73be0-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="73be0-108">問題を診断するアダプタを使用してトレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="73be0-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="73be0-109">インストールと考えられる原因および解決方法を含む、アダプターを操作するときに発生する可能性がある運用の問題を処理しています。</span><span class="sxs-lookup"><span data-stu-id="73be0-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="73be0-110">パフォーマンス カウンターを使用して、アダプターのパフォーマンスを測定します。</span><span class="sxs-lookup"><span data-stu-id="73be0-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="73be0-111">例外と考えられる原因と解決方法を含む、エラーを処理します。</span><span class="sxs-lookup"><span data-stu-id="73be0-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="73be0-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="73be0-112">In This Section</span></span>  
  
-   [<span data-ttu-id="73be0-113">診断トレースと Oracle データベース アダプターのメッセージ ログ</span><span class="sxs-lookup"><span data-stu-id="73be0-113">Diagnostic tracing and message logging for the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="73be0-114">Oracle データベース アダプターのインストールに関するをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="73be0-114">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="73be0-115">Oracle データベース アダプターの運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="73be0-115">Troubleshoot operational issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="73be0-116">Oracle データベース アダプターのパフォーマンスに関するをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="73be0-116">Troubleshoot performance issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-performance-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="73be0-117">Oracle データベース アダプターのパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="73be0-117">Use performance counters with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/use-performance-counters-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="73be0-118">例外と、Oracle データベース アダプターによるエラー処理</span><span class="sxs-lookup"><span data-stu-id="73be0-118">Exceptions and error handling with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)