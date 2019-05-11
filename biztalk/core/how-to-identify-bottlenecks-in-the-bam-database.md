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
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a>BAM データベースのボトルネックを特定する方法
BAM データベースのボトルネックを特定するには、次の手順を実行します。  
  
1.  アクティブ インスタンス数が増えていないことを確認します。  
  
2.  SQL エージェント サービスが実行されていることを確認します。  
  
3.  OLAP 分析が構成されている場合は、BAM_AN_ ジョブが定期的に実行されることを確認します。  
  
4.  BAM_DM_ (データ管理) ジョブが定期的に実行されるようにスケジュール済みであることを確認します。