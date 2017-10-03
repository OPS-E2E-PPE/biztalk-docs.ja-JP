---
title: "アクティビティ リレーションシップ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: activities [BAM], relationships
ms.assetid: da7c7205-18c6-44df-af03-3140214c84e6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3709ad02ed082595665c68485502847b52e5a1d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="activity-relationships"></a>アクティビティの関係
アクティビティ リレーションシップは、アクティビティが他の 1 つまたは複数のアクティビティに関連している場合に存在します。 この例として、単一の発注アクティビティに複数の出荷アクティビティが関連している場合や、単一の出荷アクティビティに 2 つの発注アクティビティの項目が含まれている場合などが挙げられます。  
  
 2 つのアクティビティが関連していることを示すには、AddRelatedActivity を呼び出すために、両方のアクティビティの名前とメモリ内の対応する ActivityID が必要です。 この API では、対応するアクティビティ レコード間のリンクが作成されます。  
  
 次の図で強調表示されているコード行は、発注アクティビティ インスタンス #123 と出荷アクティビティ #1549、1550、および 1551 との間にリレーションシップを作成する方法を示しています。  
  
 ![](../core/media/activity-relationships-example.gif "activity_relationships_example")  
  
 ビジネス エンド ユーザーは、Web ページを表示して発注の履歴を確認します。 午前 10 に示す場合があります。 受信して、2 日後に承認が、ページが実際のドキュメントへのリンクを提供します。 上記の図のコードにより、このページには、ビジネス エンド ユーザーが対応する出荷 Web ページに移動するためのハイパーリンクも表示されます。  
  
> [!NOTE]
>  すべての呼び出しを`AddRelatedActivity`間に行われる必要があります`BeginActivity`と`EndActivity`です。  
  
## <a name="see-also"></a>参照  
  
 [アクティビティ Continuation](../core/activity-continuation.md)   
 [BAM 動的インフラストラクチャ](../core/bam-dynamic-infrastructure.md)   
 [BAM API (BizTalk Server サンプル)](../core/bam-api-biztalk-server-sample.md)   
 [オーケストレーションの式 (BizTalk Server サンプル) から BAM API](../core/bam-api-from-an-orchestration-expression-biztalk-server-sample.md)