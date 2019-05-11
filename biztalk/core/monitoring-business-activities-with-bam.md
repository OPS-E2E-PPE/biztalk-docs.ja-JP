---
title: BAM によるビジネス アクティビティの監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], business activities
- business activities, monitoring
- business activities, managing
- monitoring business activities [BAM], about monitoring business activities
- monitoring business activities [BAM]
ms.assetid: 282a07b9-1fb2-4a83-a9b8-7d1df6c15a5b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1232c635cc8a3bbb6c6052e0b8f1b6defb40face
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65527570"
---
# <a name="monitoring-business-activities-with-bam"></a><span data-ttu-id="f7ae6-102">BAM によるビジネス アクティビティの監視</span><span class="sxs-lookup"><span data-stu-id="f7ae6-102">Monitoring Business Activities with BAM</span></span>
<span data-ttu-id="f7ae6-103">ビジネス アナリストは、ビジネス アクティビティ監視 (BAM) を使用して、ビジネス プロセスに関するデータを監視します。</span><span class="sxs-lookup"><span data-stu-id="f7ae6-103">Business Analysts use Business Activity Monitoring (BAM) to monitor data about business processes.</span></span> <span data-ttu-id="f7ae6-104">ビジネス アナリストは、Microsoft Office Excel で BAM ブックを使用して、ビジネス プロセスから収集して、ビジネス ユーザーが、収集したデータを表示する方法を定義するデータを定義します。</span><span class="sxs-lookup"><span data-stu-id="f7ae6-104">Business analysts use the BAM workbook in Microsoft Office Excel to define what data to collect from business processes and to define the way in which business users will view the collected data.</span></span>  
  
 <span data-ttu-id="f7ae6-105">ビジネス アナリストは、BAM を使用して、複数のアプリケーションにまたがるプロセスを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="f7ae6-105">Business analysts can use BAM to monitor processes that span multiple applications.</span></span> <span data-ttu-id="f7ae6-106">たとえば、発注プロセスには、BizTalk Server、データベース アクティビティ、および送信されるメッセージなどのさまざまなアプリケーションを内部の Web サイト、業者の Web サイト、および出荷業者の Web サイトで完了される部分があります。</span><span class="sxs-lookup"><span data-stu-id="f7ae6-106">For example, a purchase order process may have parts that are completed by different applications, including BizTalk Server, database activity, and messages sent from and to an internal Web site, a supplier Web site, and the shipper Web site.</span></span>  
  
 <span data-ttu-id="f7ae6-107">ビジネス ユーザーは、BAM を使用して、ビジネス プロセスに関するリアルタイムとアーカイブ済みの両方の (履歴) データを表示します。</span><span class="sxs-lookup"><span data-stu-id="f7ae6-107">Business users can use BAM to view both real-time and archived (historical) data about business processes.</span></span> <span data-ttu-id="f7ae6-108">たとえば、ビジネス ユーザーはときに複数の $100 (リアルタイム データ) または、注文書の数の注文書が到着する複数の (アーカイブ) 今月届いた $100 を知りたい場合があります。</span><span class="sxs-lookup"><span data-stu-id="f7ae6-108">For example, a business user may want to know when a purchase order arrives for more than $100 (real-time data) or, how many purchase orders for more than $100 arrived this month (archived).</span></span> <span data-ttu-id="f7ae6-109">BAM 集計リアルタイム データとアーカイブされたデータをデータ表示速度を向上させるためにします。</span><span class="sxs-lookup"><span data-stu-id="f7ae6-109">BAM aggregates real-time and archived data to improve the speed at which it presents data.</span></span>  
  
 <span data-ttu-id="f7ae6-110">BAM をインストールするためのソフトウェアとハードウェアの要件についてで BizTalk Server のインストール ガイドを参照してください。 [BizTalk Server の新機能新規、インストール、構成、およびアップグレード](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)します。</span><span class="sxs-lookup"><span data-stu-id="f7ae6-110">For information about software and hardware requirements for installing BAM, see the BizTalk Server Installation Guide, at [BizTalk Server What's New, Installation, Configuration, and Upgrade](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7ae6-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="f7ae6-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f7ae6-112">BAM のユーザー</span><span class="sxs-lookup"><span data-stu-id="f7ae6-112">Who Uses BAM?</span></span>](../core/who-uses-bam.md)  
  
-   [<span data-ttu-id="f7ae6-113">BAM のワークフロー</span><span class="sxs-lookup"><span data-stu-id="f7ae6-113">BAM Workflow</span></span>](../core/bam-workflow.md)  
  
-   [<span data-ttu-id="f7ae6-114">BAM でのデータの定義</span><span class="sxs-lookup"><span data-stu-id="f7ae6-114">Defining Data in BAM</span></span>](../core/defining-data-in-bam.md)  
  
-   [<span data-ttu-id="f7ae6-115">Excel でのビジネス アクティビティとビジネス ビューの定義</span><span class="sxs-lookup"><span data-stu-id="f7ae6-115">Defining Business Activities and Views in Excel</span></span>](../core/defining-business-activities-and-views-in-excel.md)  
  
-   [<span data-ttu-id="f7ae6-116">ライブ BAM データの表示</span><span class="sxs-lookup"><span data-stu-id="f7ae6-116">Viewing Live BAM Data</span></span>](../core/viewing-live-bam-data.md)