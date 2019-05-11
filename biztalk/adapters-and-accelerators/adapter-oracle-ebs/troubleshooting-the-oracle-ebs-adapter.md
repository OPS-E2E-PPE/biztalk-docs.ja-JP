---
title: Oracle EBS アダプターのトラブルシューティング |Microsoft Docs
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
ms.openlocfilehash: 1d4011252a27d2b7f4c86490ea9d55343d504ad3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374364"
---
# <a name="troubleshooting-the-oracle-ebs-adapter"></a><span data-ttu-id="30cf1-102">Oracle EBS アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="30cf1-102">Troubleshooting the Oracle EBS adapter</span></span>
## <a name="overview"></a><span data-ttu-id="30cf1-103">概要</span><span class="sxs-lookup"><span data-stu-id="30cf1-103">Overview</span></span>
<span data-ttu-id="30cf1-104">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]を使用して、またはこれらに限定されませんが、いくつかの Microsoft テクノロジに依存、 [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]、Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、および[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="30cf1-104">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] uses or depends on several Microsoft technologies, including but not limited to the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)], Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="30cf1-105">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]の上に構築、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]、使用することも、[!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="30cf1-105">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is built on top of the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], which also uses the [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)].</span></span> <span data-ttu-id="30cf1-106">アダプターは、いずれかを使用してアプリケーションを作成して使用できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]または BizTalk アプリケーションを作成しています。</span><span class="sxs-lookup"><span data-stu-id="30cf1-106">The adapters can be consumed either by writing applications using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or by creating BizTalk applications.</span></span> 
  
 <span data-ttu-id="30cf1-107">このセクションなどのトラブルシューティングに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="30cf1-107">This section provides information about troubleshooting, including:</span></span>  
  
-   <span data-ttu-id="30cf1-108">アダプターに関する問題の診断トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="30cf1-108">Enabling tracing to diagnose issues with the adapters</span></span>
  
-   <span data-ttu-id="30cf1-109">インストールと考えられる原因および解決方法を含め、アダプターを使用する場合に発生する可能性が運用上の問題の処理</span><span class="sxs-lookup"><span data-stu-id="30cf1-109">Handling installation and operational issues that you might encounter when working with the adapters, including probable cause and a resolution</span></span>
  
-   <span data-ttu-id="30cf1-110">パフォーマンス カウンターを使用して、アダプターのパフォーマンスを確認するには</span><span class="sxs-lookup"><span data-stu-id="30cf1-110">Using performance counters to review adapter performance</span></span>
  
-   <span data-ttu-id="30cf1-111">例外と考えられる原因、および解決策を含む、エラーの処理</span><span class="sxs-lookup"><span data-stu-id="30cf1-111">Handling exceptions and errors, including probable cause, and a resolution</span></span>
  
## <a name="lets-get-started"></a><span data-ttu-id="30cf1-112">それでは、始めましょう</span><span class="sxs-lookup"><span data-stu-id="30cf1-112">Let's get started</span></span>  
  
-   [<span data-ttu-id="30cf1-113">診断トレースと Oracle E-business Suite アダプターでメッセージのログ記録</span><span class="sxs-lookup"><span data-stu-id="30cf1-113">Diagnostic Tracing and Message Logging in the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/diagnostic-tracing-and-message-logging-in-the-oracle-e-business-suite-adapter.md) 
  
-   [<span data-ttu-id="30cf1-114">Oracle E-business Suite アダプターを使用したインストールの問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="30cf1-114">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter.md)  
  
-   [<span data-ttu-id="30cf1-115">Oracle E-business Suite アダプターを使用した運用上の問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="30cf1-115">Troubleshoot Operational Issues with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshoot-operational-issues-with-the-oracle-e-business-suite-adapter.md)
  
-   [<span data-ttu-id="30cf1-116">Oracle E-business Suite アダプターを使用したパフォーマンス カウンターの使用します。</span><span class="sxs-lookup"><span data-stu-id="30cf1-116">Use Performance Counters with the Oracle E-Business Suite adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/use-performance-counters-with-the-oracle-e-business-suite-adapter.md)