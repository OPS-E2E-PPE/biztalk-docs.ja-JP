---
title: Oracle データベース アダプターのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 2a3da42b-413b-479a-90d2-02f262abff41
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33afecfb511595cec0dc556f479968f073516a31
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375891"
---
# <a name="troubleshoot-the-oracle-database-adapter"></a><span data-ttu-id="ed445-102">Oracle データベース アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="ed445-102">Troubleshoot the Oracle Database adapter</span></span>
<span data-ttu-id="ed445-103">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用して、またはこれらに限定されませんが、いくつかの Microsoft テクノロジに依存、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、および Microsoft[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ed445-103">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and the Microsoft [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="ed445-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、順番がありますが、[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="ed445-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which in turn requires the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="ed445-105">アダプターは、いずれかを使用してアプリケーションを作成して使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="ed445-105">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> <span data-ttu-id="ed445-106">これらのテクノロジや製品のそれぞれに関連する問題については、それぞれのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed445-106">For issues related to each of these technologies and products, see the respective documentation.</span></span>  
  
 <span data-ttu-id="ed445-107">このセクションのトラブルシューティングについて説明します、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]など。</span><span class="sxs-lookup"><span data-stu-id="ed445-107">This section provides information about troubleshooting the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], including:</span></span>  
  
-   <span data-ttu-id="ed445-108">アダプターに関する問題の診断トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="ed445-108">Enabling tracing to diagnose issues with the adapters.</span></span>  
  
-   <span data-ttu-id="ed445-109">インストールと考えられる原因、および解決方法を含め、アダプターを使用する場合に発生する可能性が運用上の問題を処理します。</span><span class="sxs-lookup"><span data-stu-id="ed445-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause, and a resolution.</span></span>  
  
-   <span data-ttu-id="ed445-110">アダプターのパフォーマンスを測定するのにパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ed445-110">Using performance counters to gauge adapter performance.</span></span>  
  
-   <span data-ttu-id="ed445-111">例外とエラー、考えられる原因、解決方法などを処理します。</span><span class="sxs-lookup"><span data-stu-id="ed445-111">Handling exceptions and errors, including probable cause, and a resolution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ed445-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ed445-112">In This Section</span></span>  
  
-   [<span data-ttu-id="ed445-113">診断トレースとメッセージ ログの Oracle Database アダプター</span><span class="sxs-lookup"><span data-stu-id="ed445-113">Diagnostic tracing and message logging for the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="ed445-114">Oracle データベース アダプターのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="ed445-114">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="ed445-115">Oracle データベース アダプターを使用した運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="ed445-115">Troubleshoot operational issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-operational-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="ed445-116">Oracle データベース アダプターのパフォーマンスの問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="ed445-116">Troubleshoot performance issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-performance-issues-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="ed445-117">Oracle データベース アダプターを使用したパフォーマンス カウンターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ed445-117">Use performance counters with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/use-performance-counters-with-the-oracle-database-adapter.md)
  
-   [<span data-ttu-id="ed445-118">例外と、Oracle Database アダプターによるエラー処理</span><span class="sxs-lookup"><span data-stu-id="ed445-118">Exceptions and error handling with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/exceptions-and-error-handling-with-the-oracle-database-adapter.md)