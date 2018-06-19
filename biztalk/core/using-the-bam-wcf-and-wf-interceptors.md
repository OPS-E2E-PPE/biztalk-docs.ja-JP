---
title: BAM WCF インターセプタと WF インターセプタを使用して |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8a87a643-8e15-47d1-8d2a-3d899a1494ff
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ea631ed3a9058128a71373b6e6c7eb55ebad6c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287938"
---
# <a name="using-the-bam-wcf-and-wf-interceptors"></a><span data-ttu-id="809e5-102">BAM WCF インターセプタと WF インターセプタの使用</span><span class="sxs-lookup"><span data-stu-id="809e5-102">Using the BAM WCF and WF Interceptors</span></span>
<span data-ttu-id="809e5-103">BAM インターセプターでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM インターセプター機能が Windows Workflow Foundation (WF)、Windows Communication Framework (WCF) などのランタイム環境に拡張されます。</span><span class="sxs-lookup"><span data-stu-id="809e5-103">BAM interceptors extend the BAM interceptor functionality for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] into Windows Workflow Foundation (WF), Windows Communication Framework (WCF), and other runtime environments.</span></span> <span data-ttu-id="809e5-104">BAM インターセプタを使用すると、WF または WCF のソリューションを再コンパイルせずにビジネス プロセスを追跡できます。統合は、アプリケーション イベントを BAM アクティビティにマップし、データ、関連付け ID、継続トークンなどの必須アイテムと省略可能アイテムを定義する一連の要素と XML を使用して、構成ファイル経由で行われます。</span><span class="sxs-lookup"><span data-stu-id="809e5-104">By using a BAM interceptor, you can track your business processes without recompiling your WF or WCF solution — integration is done through a configuration file using XML and a series of elements that map application events to BAM activities and define the data, correlation ID, continuation token and other required and optional artifacts.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="809e5-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="809e5-105">In This Section</span></span>  
  
-   [<span data-ttu-id="809e5-106">BAM WCF インターセプタと WF インターセプタとは</span><span class="sxs-lookup"><span data-stu-id="809e5-106">What Are the BAM WCF and WF Interceptors?</span></span>](../core/what-are-the-bam-wcf-and-wf-interceptors.md)  
  
-   [<span data-ttu-id="809e5-107">BAM WCF インターセプタと WF インターセプタに関する既知の問題</span><span class="sxs-lookup"><span data-stu-id="809e5-107">Known Issues with the BAM WCF and WF Interceptors</span></span>](../core/known-issues-with-the-bam-wcf-and-wf-interceptors.md)  
  
-   [<span data-ttu-id="809e5-108">高可用性環境における BAM インターセプタ</span><span class="sxs-lookup"><span data-stu-id="809e5-108">BAM Interceptors in a High Availability Environment</span></span>](../core/bam-interceptors-in-a-high-availability-environment.md)  
  
-   [<span data-ttu-id="809e5-109">BAM インターセプター パフォーマンス カウンター</span><span class="sxs-lookup"><span data-stu-id="809e5-109">BAM Interceptor Performance Counters</span></span>](../core/bam-interceptor-performance-counters.md)  
  
-   [<span data-ttu-id="809e5-110">BAM API を使用して BAM インターセプタの読み込み</span><span class="sxs-lookup"><span data-stu-id="809e5-110">Loading BAM Interceptors Using the BAM API</span></span>](../core/loading-bam-interceptors-using-the-bam-api.md)  
  
-   [<span data-ttu-id="809e5-111">BAM インターセプタのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="809e5-111">Troubleshooting BAM Interceptors</span></span>](../core/troubleshooting-bam-interceptors.md)  
  
-   [<span data-ttu-id="809e5-112">BAM インターセプタのセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="809e5-112">Security Considerations for BAM Interceptors</span></span>](../core/security-considerations-for-bam-interceptors.md)  
  
-   [<span data-ttu-id="809e5-113">インターセプター構成ファイル</span><span class="sxs-lookup"><span data-stu-id="809e5-113">Interceptor Configuration File</span></span>](../core/interceptor-configuration-file.md)  
  
-   [<span data-ttu-id="809e5-114">BAM WF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="809e5-114">BAM WF Interceptor</span></span>](../core/bam-wf-interceptor.md)  
  
-   [<span data-ttu-id="809e5-115">BAM データを受信する WCF アダプタの構成</span><span class="sxs-lookup"><span data-stu-id="809e5-115">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)  
  
-   [<span data-ttu-id="809e5-116">BAM WCF インターセプタ</span><span class="sxs-lookup"><span data-stu-id="809e5-116">BAM WCF Interceptor</span></span>](../core/bam-wcf-interceptor.md)