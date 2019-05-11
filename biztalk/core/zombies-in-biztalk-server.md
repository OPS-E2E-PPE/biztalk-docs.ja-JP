---
title: BizTalk Server のゾンビ |Microsoft Docs
description: BizTalk Server のゾンビ メッセージの一般的な原因
ms.custom: ''
ms.date: 03/23/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c684891-e984-442f-b5fd-de5f7cf32b44
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc41a06c15738c63812ddd9320c7ebbfe9c52d7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320809"
---
# <a name="zombies-in-biztalk-server"></a>BizTalk Server のゾンビ

## <a name="what-is-a-zombie"></a>ゾンビとは何ですか。  
  
-   ゾンビ メッセージは、メッセージ ボックス データベースから実行中のオーケストレーションにルーティングされますが、"インフライト"であったメッセージ、オーケストレーションが終了しました。 "インフライト"でメッセージは、ですが、サービス インスタンスにルーティングされているし、サービス インスタンス宛てのメッセージ ボックス キューはメッセージです。 メッセージをサブスクライブするオーケストレーション インスタンスが利用できなくできます、ため、メッセージが中断され、"中断 (再開不可)"の ServiceInstance/状態値でマークされました。  
  
-   ゾンビ サービス インスタンスは、まだ"インフライト"で、メッセージ ボックスからオーケストレーション インスタンスにルーティングされるメッセージがされたときに終了したオーケストレーションのインスタンスです。 オーケストレーション インスタンスが終了したため、"インフライト"でメッセージを使用してためが中断され ServiceInstance/状態値が「中断 (再開不可)」とマークされています。  
  
## <a name="typical-causes"></a>一般的な原因
ゾンビの発生は、通常、次のカテゴリのいずれかに分類されます。  
  
1. **終了コントロール メッセージ**– オーケストレーション エンジンは、特定のオーケストレーション インスタンスで現在実行されているすべての処理を取り消すコントロール メッセージの使用を許可します。 コントロール メッセージでは、実行中のオーケストレーションがすぐに停止し、ためゾンビ インスタンスが予期しません。 さまざまなヒューマン ワークフロー関連の設計は、その他の設計と同様にこのメカニズムを使用する傾向があります。  
  
2. **並列待機受信**– n 個のメッセージの 1 のこのシナリオでは、サービス インスタンスが待機して特定のメッセージを受信したときに何らかの処理を終了します。 サービス インスタンスの終了と同様、並列分岐でメッセージを受信すると、ゾンビが作成されます。  
  
3. **非確定的なエンドポイントを持つシーケンシャルなコンボイ**– 何らかの種類のシステム設計要件を満たすために、特定の種類のすべてのメッセージを処理するために、このシナリオではマスター オーケストレーション スケジュールが設計されています。 これらの設計要件には、順次配送、リソース ディスペンサー、およびバッチ処理を含めることができます。 このシナリオでは、傾向、しばらくを定義するが、受信、およびその他の後に一部のコンストラクトを while ループをことを示すためにいくつかの変数を設定する遅延図形を持つ 1 つの分岐で、リッスンを囲むループを停止する必要があります。 遅延が発生する可能性が、メッセージが引き続き配信されるため、非決定的です。 このような非決定論的なエンドポイントは、ゾンビを生成しやすくします。  
  
   ゾンビ サービス インスタンスが中断されると、次のエラー メッセージが生成されます。  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 使用することができます、 [BizTalk 終端記号](https://www.microsoft.com/download/details.aspx?id=2846)ゾンビを削除します。  
  
## <a name="see-also"></a>参照  
 **中断されたサービス インスタンスを削除します。** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]