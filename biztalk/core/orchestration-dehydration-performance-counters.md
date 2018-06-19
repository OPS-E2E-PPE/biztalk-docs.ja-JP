---
title: オーケストレーションの退避のパフォーマンス カウンター |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ab92e0e-6a33-4aaa-ab14-0c82322b04d5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e81052f0061ff4ad802a084536c09d48cb6cb55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263786"
---
# <a name="orchestration-dehydration-performance-counters"></a>オーケストレーションの退避のパフォーマンス カウンター
次の表に、退避の動作を監視するために使用される、オーケストレーション エンジンのパフォーマンス カウンターを示します。 パフォーマンス モニターを使用すると、これらのカウンターを監視しながら退避パラメーターを調整できます。  
  
|退避のパフォーマンス カウンター|Description|  
|-------------------------------------|-----------------|  
|Dehydratable orchestrations|ホスト インスタンスが現在ホストしている、待避可能なオーケストレーション インスタンスの数。|  
|Dehydrating orchestrations|待避処理中のオーケストレーション数。|  
|Dehydration cycle in progress|待避サイクルが現在進行中であるかどうか。|  
|Dehydration cycles|完了した待避サイクルの数。|  
|Dehydration threshold|オーケストレーションを待避する頻度を決定するしきい値 (ミリ秒)。 オーケストレーション エンジンによって推定された待避可能時間が、このしきい値を超えた場合、インスタンス待避されます。|  
|Orchestrations dehydrated|ホスト インスタンスの起動以降に待避されたオーケストレーション インスタンスの数。|  
|Orchestrations dehydrated/sec|1 秒あたりの平均待避数。|  
|Orchestrations rehydrated|ホスト インスタンスの起動以降に復元されたオーケストレーション インスタンスの数。|  
|Orchestrations rehydrated/sec|1 秒あたりに復元した数の平均値|  
|Orchestrations scheduled for dehydration|保留中の待避要求が存在する、待避可能なオーケストレーション数。|