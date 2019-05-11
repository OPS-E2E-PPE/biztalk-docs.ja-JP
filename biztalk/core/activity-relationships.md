---
title: アクティビティ リレーションシップ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], relationships
ms.assetid: da7c7205-18c6-44df-af03-3140214c84e6
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3266501df57b9350e70369327fdc3142b3019d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361659"
---
# <a name="activity-relationships"></a>アクティビティ リレーションシップ
アクティビティに関連するその他の 1 つまたは複数のアクティビティと、アクティビティのリレーションシップが存在します。 この例には、1 つの注文書アクティビティ、または 2 つの注文書アクティビティから項目を含む 1 つの出荷アクティビティに関連する複数の出荷アクティビティが発生しました。  
  
 2 つのアクティビティが関連していることを示すには、両方の名前を知るし、AddRelatedActivity を呼び出すためにメモリに対応する Activityid がある必要があります。 この API は、対応するアクティビティ レコード間のリンクを作成します。  
  
 次の図では、強調表示された行のコードは、注文書アクティビティ インスタンス #123 と出荷アクティビティ #1549、1550、および 1551 との間のリレーションシップを作成する方法を説明します。  
  
 ![](../core/media/activity-relationships-example.gif "activity_relationships_example")  
  
 ビジネス エンドユーザーが 1 つの Web ページを注文書の履歴を表示します。 午前 10 に示すことがあります。 受信した、2 日後に承認が、およびページが実際のドキュメントへのリンクを提供します。 前の図に、コードのため、ページは、対応する出荷 Web ページには、ビジネス エンドユーザーを取るハイパーリンクも提供されます。  
  
> [!NOTE]
>  すべての呼び出しを`AddRelatedActivity`間に行われる必要があります`BeginActivity`と`EndActivity`します。  
  
## <a name="see-also"></a>参照  
  
 [アクティビティ Continuation](../core/activity-continuation.md)   
 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)   
 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)   
 [オーケストレーション式からの BAM API (BizTalk Server サンプル)](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)