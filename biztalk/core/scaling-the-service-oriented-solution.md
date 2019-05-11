---
title: スケーリング、サービス指向ソリューション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, service solutions
- service solution tutorial, scaling
ms.assetid: 6c22a68d-03e7-4174-b612-0e2246aa9413
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 895b0ad325e9dce4086c90bccf932f73226780e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308910"
---
# <a name="scaling-the-service-oriented-solution"></a>スケーリング、サービス指向ソリューション
短いメッセージを維持しながらより高いスループットをサポートするために、ソリューションを拡張するには、待機時間は、ソリューションのインライン バージョンを使用することが必要です。 インライン ソリューションは、バックエンド システムと対話するときに、メッセージ ボックス データベースを無視します。  
  
 オーケストレーションを実行する BizTalk Server 処理サーバーを追加することもできます。 これにより、新しい要求が迅速に処理できるように、各サーバーの使用率が低下します。 メッセージのスループットを処理するための十分な追加の容量があるように、メッセージ ボックス サーバーをスケールもできます。  
  
 ただし、サービス指向アーキテクチャ ソリューションでは、複数のメッセージ ボックス データベースからのメリットはありません。 複数のメッセージ ボックスには、分散トランザクション コーディネーター (DTC) トランザクションが必要です。 トランザクションは、メッセージの全体的な待機時間を増やします。  
  
 MQSeries ヘッダーの情報を追加するパイプライン コンポーネントを排除することにより、応答時間を減らすことができます。 詳細については、次を参照してください。[サービス指向ソリューションの実装が強調表示](../core/implementation-highlights-of-the-service-oriented-solution.md)します。  
  
## <a name="see-also"></a>参照  
 [開発、サービス指向ソリューション](../core/developing-a-service-oriented-solution.md)