---
title: BAM 動的インフラストラクチャ |Microsoft Docs
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
ms.openlocfilehash: 2ed2c99ad52068d26a1144bb47cf3d247c6456d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358558"
---
# <a name="bam-dynamic-infrastructure"></a><span data-ttu-id="a48b1-102">BAM 動的インフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="a48b1-102">BAM Dynamic Infrastructure</span></span>
<span data-ttu-id="a48b1-103">SQL Server のテーブル、BAM ビュー、ストアド プロシージャ、およびデータ変換サービス (DTS) パッケージとして構成され、増分使用して管理される BAM データベース (プライマリ インポート、アーカイブ、スター スキーマ、および分析) での BAM インフラストラクチャの構成します。BAM 定義の展開。</span><span class="sxs-lookup"><span data-stu-id="a48b1-103">The BAM infrastructure consists of SQL Server tables, BAM views, stored procedures, and Data Transformation Services (DTS) packages in the BAM databases (Primary Import, Archive, Star Schema, and Analysis) as configured and managed through incremental deployments of BAM definitions.</span></span> <span data-ttu-id="a48b1-104">インフラストラクチャは、ここで、実行時に、イベント、相関、集計、およびユーザーがクエリで使用可能になります。</span><span class="sxs-lookup"><span data-stu-id="a48b1-104">The infrastructure is where, at run time, events are correlated, aggregated, and then made available for querying by users.</span></span>  
  
 <span data-ttu-id="a48b1-105">このセクションでは、このインフラストラクチャ プロセスの一部について説明します。</span><span class="sxs-lookup"><span data-stu-id="a48b1-105">This section describes some of these infrastructure processes.</span></span> <span data-ttu-id="a48b1-106">たとえば、(BAM 定義)、アプリケーションから目的のデータを抽出するとできます保存するクエリで使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="a48b1-106">For example, once you extract the data of interest from your applications (the BAM definition), you can store it so that it is available for queries.</span></span> <span data-ttu-id="a48b1-107">さらに、集計クエリの高速のデータの特定の事前に作成した集計を維持することができます。</span><span class="sxs-lookup"><span data-stu-id="a48b1-107">Additionally, you can maintain certain pre-created aggregations of the data for faster aggregated queries.</span></span>  
  
 <span data-ttu-id="a48b1-108">通常、データ ウェアハウスを実装するために膨大な開発作業でこのような機能を実現します。</span><span class="sxs-lookup"><span data-stu-id="a48b1-108">Typically, you achieve such functionality by an extensive development effort to implement a data warehouse.</span></span> <span data-ttu-id="a48b1-109">Microsoft で BAM[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]大幅に簡略化このプロセスは、ただし、アクティビティとビューの定義に基づいて SQL および OLAP のインフラストラクチャを自動的に生成しています。</span><span class="sxs-lookup"><span data-stu-id="a48b1-109">BAM in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] greatly simplifies this process, however, by automatically generating the SQL and OLAP infrastructure based on your activity and view definitions.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a48b1-110">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a48b1-110">In This Section</span></span>  
  
-   [<span data-ttu-id="a48b1-111">BAM 定義について</span><span class="sxs-lookup"><span data-stu-id="a48b1-111">What Is a BAM Definition?</span></span>](../core/what-is-a-bam-definition.md)  
  
-   [<span data-ttu-id="a48b1-112">BAM 定義スキーマについて</span><span class="sxs-lookup"><span data-stu-id="a48b1-112">What Is a BAM Definition Schema?</span></span>](../core/what-is-a-bam-definition-schema.md)  
  
-   [<span data-ttu-id="a48b1-113">アクティビティ データのストレージ</span><span class="sxs-lookup"><span data-stu-id="a48b1-113">Activity Data Storage</span></span>](../core/activity-data-storage.md)  
  
-   [<span data-ttu-id="a48b1-114">集計について</span><span class="sxs-lookup"><span data-stu-id="a48b1-114">What Is an Aggregation?</span></span>](../core/what-is-an-aggregation.md)  
  
-   [<span data-ttu-id="a48b1-115">BAM データのクエリ</span><span class="sxs-lookup"><span data-stu-id="a48b1-115">Querying BAM Data</span></span>](../core/querying-bam-data.md)  
  
-   [<span data-ttu-id="a48b1-116">BAM インフラストラクチャの制限</span><span class="sxs-lookup"><span data-stu-id="a48b1-116">BAM Infrastructure Limitations</span></span>](../core/bam-infrastructure-limitations.md)  
  
-   [<span data-ttu-id="a48b1-117">英語以外のインストールで範囲外の数値ディメンション警告を定義する方法</span><span class="sxs-lookup"><span data-stu-id="a48b1-117">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>](../core/define-out-of-range-numeric-dimension-alerts-in-non-english-installations--bam.md)