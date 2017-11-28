---
title: "BAM によるビジネス アクティビティの監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], business activities
- business activities, monitoring
- business activities, managing
- monitoring business activities [BAM], about monitoring business activities
- monitoring business activities [BAM]
ms.assetid: 282a07b9-1fb2-4a83-a9b8-7d1df6c15a5b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 742dff7f75caf5e8910eb1f133b0d24a42945f95
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-business-activities-with-bam"></a><span data-ttu-id="99e58-102">BAM によるビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="99e58-102">Monitoring Business Activities with BAM</span></span>
<span data-ttu-id="99e58-103">ビジネス アクティビティ監視 (BAM) を使用すると、ビジネス アナリストはビジネス プロセスに関するデータを監視できます。</span><span class="sxs-lookup"><span data-stu-id="99e58-103">Business Analysts use Business Activity Monitoring (BAM) to monitor data about business processes.</span></span> <span data-ttu-id="99e58-104">ビジネス アナリストは、Microsoft Office Excel の BAM ブックを使用して、ビジネス プロセスから収集するデータの種類と、収集したデータをビジネス ユーザーが表示する方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="99e58-104">Business analysts use the BAM workbook in Microsoft Office Excel to define what data to collect from business processes and to define the way in which business users will view the collected data.</span></span>  
  
 <span data-ttu-id="99e58-105">BAM では、複数のアプリケーションにまたがるプロセスを監視できます。</span><span class="sxs-lookup"><span data-stu-id="99e58-105">Business analysts can use BAM to monitor processes that span multiple applications.</span></span> <span data-ttu-id="99e58-106">たとえば、発注プロセスには、BizTalk Server などの多様なアプリケーションによって完了される部分や、データベース アクティビティ、さらには内部 Web サイト、業者 Web サイト、および出荷業者 Web サイトの間で送受信されるメッセージが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="99e58-106">For example, a purchase order process may have parts that are completed by different applications, including BizTalk Server, database activity, and messages sent from and to an internal Web site, a supplier Web site, and the shipper Web site.</span></span>  
  
 <span data-ttu-id="99e58-107">ビジネス ユーザーは BAM を使用して、ビジネス プロセスに関するリアルタイム データおよびアーカイブ済みの (履歴) データの両方を参照できます。</span><span class="sxs-lookup"><span data-stu-id="99e58-107">Business users can use BAM to view both real-time and archived (historical) data about business processes.</span></span> <span data-ttu-id="99e58-108">たとえば、100 ドル以上の注文書の受信 (リアルタイム データ) や、今月届いた 100 ドル以上の注文書の数 (アーカイブ済みのデータ) を確認できます。</span><span class="sxs-lookup"><span data-stu-id="99e58-108">For example, a business user may want to know when a purchase order arrives for more than $100 (real-time data) or, how many purchase orders for more than $100 arrived this month (archived).</span></span> <span data-ttu-id="99e58-109">BAM では、データの表示速度を向上させるためにリアルタイム データおよびアーカイブ済みデータが集計されます。</span><span class="sxs-lookup"><span data-stu-id="99e58-109">BAM aggregates real-time and archived data to improve the speed at which it presents data.</span></span>  
  
 <span data-ttu-id="99e58-110">BAM をインストールするためのソフトウェアとハードウェアの要件についてで BizTalk Server のインストール ガイドを参照してください。 [BizTalk Server の新機能新規、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)です。</span><span class="sxs-lookup"><span data-stu-id="99e58-110">For information about software and hardware requirements for installing BAM, see the BizTalk Server Installation Guide, at [BizTalk Server What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="99e58-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="99e58-111">In This Section</span></span>  
  
-   [<span data-ttu-id="99e58-112">BAM を使用するユーザーですか。</span><span class="sxs-lookup"><span data-stu-id="99e58-112">Who Uses BAM?</span></span>](../core/who-uses-bam.md)  
  
-   [<span data-ttu-id="99e58-113">BAM のワークフロー</span><span class="sxs-lookup"><span data-stu-id="99e58-113">BAM Workflow</span></span>](../core/bam-workflow.md)  
  
-   [<span data-ttu-id="99e58-114">BAM でデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="99e58-114">Defining Data in BAM</span></span>](../core/defining-data-in-bam.md)  
  
-   [<span data-ttu-id="99e58-115">Excel でビジネス アクティビティとビューを定義します。</span><span class="sxs-lookup"><span data-stu-id="99e58-115">Defining Business Activities and Views in Excel</span></span>](../core/defining-business-activities-and-views-in-excel.md)  
  
-   [<span data-ttu-id="99e58-116">ライブ BAM データの表示</span><span class="sxs-lookup"><span data-stu-id="99e58-116">Viewing Live BAM Data</span></span>](../core/viewing-live-bam-data.md)