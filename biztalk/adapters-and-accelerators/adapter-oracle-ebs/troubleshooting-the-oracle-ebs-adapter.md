---
title: Oracle EBS アダプターのトラブルシューティング |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d78d5335-b860-47d9-9f3a-7f74d628d8ff
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7b36316612bda541d9bf608f7da22c399ade045
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216178"
---
# <a name="troubleshooting-the-oracle-ebs-adapter"></a><span data-ttu-id="00e7e-102">Oracle EBS アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="00e7e-102">Troubleshooting the Oracle EBS adapter</span></span>
## <a name="overview"></a><span data-ttu-id="00e7e-103">概要</span><span class="sxs-lookup"><span data-stu-id="00e7e-103">Overview</span></span>
<span data-ttu-id="00e7e-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用してまたはに限らずなど、いくつかの Microsoft テクノロジによって異なります、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、および[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00e7e-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="00e7e-105">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築された、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]を使用しても、[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="00e7e-105">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which also uses the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="00e7e-106">いずれかを使用してアプリケーションを作成して、アダプターを使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="00e7e-106">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> 
  
 <span data-ttu-id="00e7e-107">このセクションを含めのトラブルシューティングに関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="00e7e-107">This section provides information about troubleshooting, including:</span></span>  
  
-   <span data-ttu-id="00e7e-108">問題を診断するアダプタを使用してトレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="00e7e-108">Enabling tracing to diagnose issues with the adapters</span></span>
  
-   <span data-ttu-id="00e7e-109">インストールと考えられる原因および解決方法を含む、アダプターを操作するときに発生する可能性がある運用の問題の処理</span><span class="sxs-lookup"><span data-stu-id="00e7e-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause and a resolution</span></span>
  
-   <span data-ttu-id="00e7e-110">パフォーマンス カウンターを使用して、アダプターのパフォーマンスを確認するには</span><span class="sxs-lookup"><span data-stu-id="00e7e-110">Using performance counters to review adapter performance</span></span>
  
-   <span data-ttu-id="00e7e-111">例外の処理やエラー、考えられる原因および解決方法を含む</span><span class="sxs-lookup"><span data-stu-id="00e7e-111">Handling exceptions and errors, including probable cause, and a resolution</span></span>
  
## <a name="lets-get-started"></a><span data-ttu-id="00e7e-112">開始しましょう</span><span class="sxs-lookup"><span data-stu-id="00e7e-112">Let's get started</span></span>  
  
-   [<span data-ttu-id="00e7e-113">診断トレースと Oracle E-business Suite アダプターでメッセージのログ記録</span><span class="sxs-lookup"><span data-stu-id="00e7e-113">Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md) 
  
-   [<span data-ttu-id="00e7e-114">Oracle E-business Suite アダプターでのインストールに関する問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="00e7e-114">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="00e7e-115">Oracle E-business Suite アダプターでの運用上の問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="00e7e-115">Troubleshoot Operational Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter.md)
  
-   [<span data-ttu-id="00e7e-116">Oracle E-business Suite アダプターのパフォーマンス カウンターの使用します。</span><span class="sxs-lookup"><span data-stu-id="00e7e-116">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-performance-counters-with-the-oracle-e-business-suite-adapter.md)