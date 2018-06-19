---
title: BAM 動的インフラストラクチャ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- infrastructure, BAM
- BAM, infrastructure
ms.assetid: 88f39438-3213-4f0d-8b8d-e6426c266138
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3660eeb6f85fb21ff78b7b833b21adbb3af87385
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230450"
---
# <a name="bam-dynamic-infrastructure"></a><span data-ttu-id="5be62-102">BAM 動的インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="5be62-102">BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="5be62-103">SQL Server のテーブル、BAM ビュー、ストアド プロシージャ、および構成され、増分使用して管理される BAM データベース (プライマリ インポート、アーカイブ、スター スキーマ、および分析) でデータ変換サービス (DTS) パッケージの BAM インフラストラクチャの構成します。BAM 定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="5be62-103">The BAM infrastructure consists of SQL Server tables, BAM views, stored procedures, and Data Transformation Services (DTS) packages in the BAM databases (Primary Import, Archive, Star Schema, and Analysis) as configured and managed through incremental deployments of BAM definitions.</span></span> <span data-ttu-id="5be62-104">インフラストラクチャは、ここで、実行時に、イベントは、相関、集計、および、ユーザーによるクエリの利用できるようです。</span><span class="sxs-lookup"><span data-stu-id="5be62-104">The infrastructure is where, at run time, events are correlated, aggregated, and then made available for querying by users.</span></span>  
  
 <span data-ttu-id="5be62-105">このセクションでは、このインフラストラクチャ プロセスの一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="5be62-105">This section describes some of these infrastructure processes.</span></span> <span data-ttu-id="5be62-106">たとえば、アプリケーションから目的のデータ (BAM 定義) を抽出すると、そのデータを保存して、クエリに使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5be62-106">For example, once you extract the data of interest from your applications (the BAM definition), you can store it so that it is available for queries.</span></span> <span data-ttu-id="5be62-107">また、集計クエリの処理速度を上げるために、事前作成済みの特定のデータ集計を保持できます。</span><span class="sxs-lookup"><span data-stu-id="5be62-107">Additionally, you can maintain certain pre-created aggregations of the data for faster aggregated queries.</span></span>  
  
 <span data-ttu-id="5be62-108">通常、データ ウェアハウスを実装する場合、膨大な開発作業を行ってこのような機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="5be62-108">Typically, you achieve such functionality by an extensive development effort to implement a data warehouse.</span></span> <span data-ttu-id="5be62-109">しかし、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の BAM では、アクティビティやビューの定義に基づいて SQL および OLAP のインフラストラクチャを自動的に生成することで、このプロセスを大幅に簡略化しています。</span><span class="sxs-lookup"><span data-stu-id="5be62-109">BAM in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] greatly simplifies this process, however, by automatically generating the SQL and OLAP infrastructure based on your activity and view definitions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5be62-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5be62-110">In This Section</span></span>  
  
-   [<span data-ttu-id="5be62-111">BAM 定義とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5be62-111">What Is a BAM Definition?</span></span>](../core/what-is-a-bam-definition.md)  
  
-   [<span data-ttu-id="5be62-112">BAM 定義スキーマとは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5be62-112">What Is a BAM Definition Schema?</span></span>](../core/what-is-a-bam-definition-schema.md)  
  
-   [<span data-ttu-id="5be62-113">アクティビティ データのストレージ</span><span class="sxs-lookup"><span data-stu-id="5be62-113">Activity Data Storage</span></span>](../core/activity-data-storage.md)  
  
-   [<span data-ttu-id="5be62-114">集計とは何ですか。</span><span class="sxs-lookup"><span data-stu-id="5be62-114">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)  
  
-   [<span data-ttu-id="5be62-115">BAM データを照会します。</span><span class="sxs-lookup"><span data-stu-id="5be62-115">Querying BAM Data</span></span>](../core/querying-bam-data.md)  
  
-   [<span data-ttu-id="5be62-116">BAM インフラストラクチャの制限</span><span class="sxs-lookup"><span data-stu-id="5be62-116">BAM Infrastructure Limitations</span></span>](../core/bam-infrastructure-limitations.md)  
  
-   [<span data-ttu-id="5be62-117">英語以外のインストールで範囲外の数値ディメンション警告を定義する方法</span><span class="sxs-lookup"><span data-stu-id="5be62-117">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)