---
title: メッセージ エラーの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transformation stage
- assembly stage
- errors, disassembly stage
- errors, assembly stage
- routing, errors
- errors, transformation stage
- errors, messages [HAT]
- errors, routing
- disassembly stage, errors
- messages, errors [HAT]
ms.assetid: 3a8e1c58-4b53-4439-837d-aaa233eb9158
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8a3dc40d2b82e90332b27719adce36b27f78ebd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984011"
---
# <a name="types-of-message-failures"></a>メッセージ エラーの種類
このトピックでは、メッセージ エラーが発生する可能性のあるさまざまな状況を示します。  
  
 **逆アセンブリ フェーズでのエラー**  
  
 処理は逆アセンブリ フェーズでも失敗することがあります。つまり、いずれかのパイプライン コンポーネントでエラーが発生します。 たとえば、処理サーバーに解読証明書がないことが原因で解読に失敗したり、スキーマやメッセージに問題があることが原因で解析が失敗したりすることがあります。  
  
 **ルーティングでのエラー**  
  
 メッセージが正常に逆アセンブルされた後、次にエラーが発生する可能性のある処理はルーティングです。たとえば、ユーザーがオーケストレーションの対応する受信場所を有効にしたにもかかわらず、オーケストレーションに参加させるのを忘れた場合などが挙げられます。 この場合、受信場所から取得したメッセージはルーティングに失敗し、メッセージ ボックス データベースによってルーティング エラー報告が生成されます。  
  
 ルーティング エラー報告は、再開不可の保留メッセージとして BizTalk Server 管理コンソールに表示されます。 各ルーティング エラー報告には、ルーティング エラーの発生時に作成された、メッセージ プロパティのスナップショットが含まれます。 各エラー報告に示されている情報を使用して、関連メッセージのルーティングが失敗した原因を判断できます。 関連メッセージが再開可能である場合は、ルーティングの問題を修正し、メッセージを再開して、処理を続行できます。 サービス名とサービスの種類が空白の状態でルーティング エラー報告が結果一覧に表示されます。 中断されているインスタンスを終了すると、既定では毎分実行される Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb ジョブによって、そのインスタンスに関連付けられているルーティング エラー報告が自動的に削除されます。 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb ジョブの詳細については、[データベース構造とジョブ](../core/database-structure-and-jobs.md)を参照してください。  
  
 **変換フェーズ中にエラー**  
  
- **メッセージを受信した**します。 メッセージは受信場所からの受信時に、逆アセンブル (解読や解析など) されます。受信ポートに指定された受信マップによって、必要に応じて異なる形式に変換された後、オーケストレーションや送信ポートにルーティングするためにメッセージ ボックスにパブリッシュされます。 この場合、受信マップが正しくないか、スキーマまたは受信したメッセージに問題があることが原因で、変換フェーズ中に処理が失敗することがあります。  
  
- **メッセージを送信する**します。 メッセージは送信場所への送信時に、送信ポートに構成されている送信マップによって、必要に応じて変換されます。 変換後のメッセージはアセンブルされ、最後に送信場所への送信を行うアダプターに渡されます。 この場合、送信マップが正しくないか、スキーマまたは送信元メッセージに問題があることが原因で、変換フェーズ中に処理が失敗する場合があります。  
  
  **メッセージのアセンブリ フェーズでのエラー**  
  
  メッセージのアセンブリ フェーズでもエラーが発生する場合があります。つまり、パイプライン コンポーネントでエラーが発生するということです。 メッセージが正常にアセンブルされたら、次にエラーが発生する可能性のある処理は、送信場所への送信です。たとえば、(パートナーに属している) 送信場所がダウンしていたり存在しない場合にエラーが発生します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)