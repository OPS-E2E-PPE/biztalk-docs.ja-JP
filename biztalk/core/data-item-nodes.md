---
title: データ項目ノード |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- definition files [BAM], data items
- Data Item nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- Tracking Profile Editor, definition files [BAM]
ms.assetid: 95856bfa-90e3-49d9-b55b-5f1b35a23f78
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a968bf7533697922938eeb8953f17813c77147c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238026"
---
# <a name="data-item-nodes"></a>データ項目ノード
データ項目ノードは、ビジネス アナリストが作成した監視モデルから開発者がインポートするアクティビティ定義ファイルに存在します。 データ項目ノードには、追跡するデータ項目を反映した名前 (たとえば、Customer Name など) が追跡プロファイル エディター (TPE) によって付けられます。 Customer Name に対応するノードには、メッセージ スキーマ ビューから 1 つ以上のデータ項目をドロップします。  
  
## <a name="working-with-data-item-nodes"></a>データ項目ノードの操作  
 データ項目ノードをマップする際に、ビジネス プロセスが複数の追跡プロファイルにまたがっていても、データ項目は 1 つのビジネス プロセスにつき 1 回だけ追跡するようにしてください。 オーケストレーションに条件付きのパスが含まれている場合は、いずれか一方しか実行されないので、両方のパスからデータ項目を選択することができます。 ただし、反復ごとにデータ項目の値が異なる場合を除き、ループ内の図形は選択しないでください。  
  
## <a name="see-also"></a>参照  
 [項目のデータをマップする方法](../core/how-to-map-item-data.md)   
 [TPE アクティビティ ビューのノード](../core/tpe-activity-view-nodes.md)