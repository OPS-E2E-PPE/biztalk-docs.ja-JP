---
title: "スケーリング、サービス指向ソリューション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scaling, service solutions
- service solution tutorial, scaling
ms.assetid: 6c22a68d-03e7-4174-b612-0e2246aa9413
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3026664d3a365630c93bf1c61d7cf635fdd9dc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-the-service-oriented-solution"></a>スケーリング、サービス指向ソリューション
短いメッセージ待機時間を維持しながら高いスループットをサポートできるようにソリューションを拡張するには、インライン バージョンのソリューションを使用します。 インライン ソリューションはバックエンド システムとやり取りするとき、メッセージ ボックス データベースをバイパスします。  
  
 オーケストレーションを実行する BizTalk Server 処理サーバーを追加することもできます。 これによって各サーバーの使用率が低下して新しい要求が迅速に処理されます。 メッセージ ボックス サーバーをスケール アップして、メッセージ スループットの増加に対応できるだけの容量を追加することもできます。  
  
 ただし、サービス指向アーキテクチャ ソリューションでは、複数のメッセージ ボックス データベースを使用してもパフォーマンスの向上は期待できません。 複数のメッセージ ボックス データベースを使用する場合は分散トランザクション コーディネータ (DTC) トランザクションが必要です。 このトランザクションを使用すると、全体としてのメッセージ待機時間が長くなります。  
  
 応答時間は MQSeries のヘッダー情報を追加するパイプライン コンポーネントを除外することによって短縮できます。 詳細については、次を参照してください。[サービス指向ソリューションの実装が強調表示](../core/implementation-highlights-of-the-service-oriented-solution.md)です。  
  
## <a name="see-also"></a>参照  
 [指向ソリューションのサービスの開発](../core/developing-a-service-oriented-solution.md)