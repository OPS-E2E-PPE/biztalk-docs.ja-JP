---
title: オーケストレーションの退避のパフォーマンス カウンター |Microsoft Docs
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
ms.openlocfilehash: d7e00a5c6c0adb1e964d9872d048a22d1d8b7eae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262859"
---
# <a name="orchestration-dehydration-performance-counters"></a>オーケストレーションの退避のパフォーマンス カウンター
次の表は、オーケストレーション エンジンのパフォーマンス カウンターは、退避の動作の監視に固有の名前を一覧表示します。 パフォーマンス モニターを使用して、退避パラメーターをチューニング中にこれらのカウンターを監視します。  
  
|退避のパフォーマンス カウンター|説明|  
|-------------------------------------|-----------------|  
|待避可能なオーケストレーション|数、ホスト インスタンスによって現在ホストされているができるインスタンスのオーケストレーションの退避します。|  
|オーケストレーションの退避|待避処理中のオーケストレーションの数。|  
|進行中の退避サイクル|現在進行中の退避サイクルがあるかどうかを示します。|  
|退避サイクル|完了した退避サイクルの数。|  
|退避のしきい値|どの程度積極的にオーケストレーションが退避されているかを決定するミリ秒数。 インスタンスをこのしきい値より長い時間の量の推定された待避可能するは、オーケストレーション エンジンを予測する場合、インスタンス待避されます。|  
|退避されたオーケストレーション|オーケストレーション インスタンスの数は、ホスト インスタンスの起動以降に待避されました。|  
|Orchestrations dehydrated/sec|1 秒あたりの平均待避数。|  
|リハイド レートされたオーケストレーション|ホスト インスタンスの起動後にリハイド レートされたオーケストレーション インスタンスの数。|  
|Orchestrations rehydrated/sec|1 秒あたりにリハイド レートされた数の平均値|  
|オーケストレーションの退避のスケジュール|対象の保留中の退避要求が、待避可能なオーケストレーションの数。|