---
title: BAM データベースのボトルネックを特定する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: b8fa54379d6d314993ac33b7d6395f061e48849d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254106"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-database"></a>BAM データベースのボトルネックを特定する方法
BAM データベースのボトルネックを特定するには、次の手順を実行します。  
  
1.  アクティブ インスタンス数が増えていないことを確認します。  
  
2.  SQL エージェント サービスが実行されていることを確認します。  
  
3.  OLAP 分析が構成されている場合は、BAM_AN_ ジョブが定期的に実行されることを確認します。  
  
4.  BAM_DM_ (データ管理) ジョブが定期的に実行されるようにスケジュール済みであることを確認します。