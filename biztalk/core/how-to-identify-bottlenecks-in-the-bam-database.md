---
title: BAM データベースのボトルネックを特定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6814c0df-3ce1-44f8-8e63-af6e23336c6d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fe47056d70e1b7e0f93bf9ba2451ade489a5c93
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337252"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a><span data-ttu-id="05d75-102">BAM データベースのボトルネックを特定する方法</span><span class="sxs-lookup"><span data-stu-id="05d75-102">How to Identify Bottlenecks in the BAM Database</span></span>
<span data-ttu-id="05d75-103">BAM データベースのボトルネックを特定するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="05d75-103">To identify bottlenecks in the BAM database, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="05d75-104">アクティブ インスタンス数が増えていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="05d75-104">Ensure that the Active Instances count is not climbing.</span></span>  
  
2.  <span data-ttu-id="05d75-105">SQL エージェント サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05d75-105">Ensure that the SQL-Agent Service is running.</span></span>  
  
3.  <span data-ttu-id="05d75-106">OLAP 分析が構成されている場合は、BAM_AN_ ジョブが定期的に実行されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05d75-106">If OLAP Analysis is configured ensure that the BAM_AN_ job is running at periodic intervals.</span></span>  
  
4.  <span data-ttu-id="05d75-107">BAM_DM_ (データ管理) ジョブが定期的に実行されるようにスケジュール済みであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="05d75-107">Ensure that BAM_DM_ (Data Maintenance) job is scheduled to run at periodic intervals.</span></span>