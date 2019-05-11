---
title: システム トレーラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- trailers [SWIFT]
- SWIFT, trailers
ms.assetid: 2fd49be9-afe8-47c6-a613-fa469faa2126
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 995ed2a0214b9de3f50c7aac2298138da1d6df73
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529735"
---
# <a name="system-trailers"></a>システム トレーラー
システム トレーラーは、SWIFT メッセージの詳細を追加または特殊なを伝達します。 最初の 3 つのシステム トレーラーが存在する次の順序で出現します。 残りのシステム トレーラーは、任意の順序で発生します。  
  
|トレーラー コード|名前|  
|------------------|----------|  
|**CHK**|チェックサム|  
|**SYS**|システムにメッセージが発生しました。|  
|**TNG**|トレーニング|  
|**PDM**|使用可能な重複するメッセージ|  
|**DLM**|遅延メッセージ|  
|**MRF**|メッセージのリファレンス|  
  
- **システムでは、(SYS) のメッセージのトレーラーが開始されます。** システム メッセージまたは PLT システムによって生成される、サービス メッセージは、SYS トレーラーを持っています。 要求の MIR を含めることが、および時間を含めることができますすべて 01 のサービスの識別子を持つシステム メッセージを要請します。  
  
   次のコードでは、SYS トレーラーの形式の例を示します。  
  
  ```  
  {SYS:[<time><mir>]}  
  ```  
  
- **テストと (TNG) メッセージのトレーラーをトレーニングします。** TNG トレーラーはファイナンスと GPA (01 のサービス識別子) を持つ送信、またはメッセージをテストおよびトレーニング論理ターミナル (LT) に配信するために必須です。 このトレーラーには、のみ、タグと値はありませんがあります。  
  
   次のコードでは、TNG トレーラーの形式の例を示します。  
  
  ```  
  {TNG:}  
  ```  
  
- **トレーラーの考えられる重複する出力 (PDE)。** メッセージの送信先は、PDE トレーラーを使用します。 (01 のサービス識別子) を持つユーザーにメッセージを FIN とメッセージの銀行の予約済みメッセージ カテゴリにのみ適用されます。 システムでは、複数の PDEs を含めることができます。 システムは、順を確認したり (メッセージの最大長) を除く数に制限はありません。  
  
   システムは、ユーザーとシステム メッセージに適用 PDE トレーラーを正しい形式を受け入れますが、それらを処理しません。 つまり、システムは、元のメッセージが存在するかどうかを確認しないようにします。 そのため、システムが PDE トレーラーで 2 回送信の取得要求を処理可能性があります-システムは、元のメッセージを受信した場合。  
  
   次のコードでは、PDE トレーラーの形式の例を示します。  
  
  ```  
  {PDE:[<time><mir>]}  
  where <time><mir> refers to the emission of the previous possible issue  
  ```  
  
- **遅延メッセージ (DLM) トレーラです。** DLM トレーラーは、陳腐化期間を超えているすべての FIN ユーザーに出力メッセージに追加されます。 このトレーラー GPA または FIN のシステム メッセージが表示されたら、無視できます。 このトレーラーには、のみ、タグと値はありませんがあります。  
  
   陳腐化期間は次のとおりです。  
  
  - U = 15 分  
  
  - N = 100 分  
  
    DLM トレーラーの形式の例を次のコードに示します。  
  
  ```  
  {DLM:}  
  ```  
  
- **トレーラーの使用可能な重複するメッセージ (PDM)。** PDM トレーラーが (GPA および 01 のサービスの識別子を持つ FIN) 出力メッセージに、システムによって追加される前の配布が無効であるため、再送信してもらいます。 します。 システム PLT PDM トレーラーでレポートの要求を受信する場合、応答には (省略可能な配信のリファレンス) なしのプレーンな PDM があります。 ユーザーには、配信が失敗した試行のため他 PDMs を追加することがあります。  
  
   次のコードでは、PDM トレーラーの形式の例を示します。  
  
  ```  
  {PDM:[<time><mor>]}  
  where <time> and the Message Output Reference <mor> are that of the previous attempt  
  ```  
  
- **メッセージの参照 (MRF) トレーラーします。** MRF トレーラーは、教育機関のサーバーの全体のメッセージには、MT 096 FIN コピーで元のユーザー メッセージのメッセージの参照を指定します。  
  
   次のコードでは、MRF トレーラーの形式の例を示します。  
  
  ```  
  {MRF:<date><full-time><mir>}  
  where <mir> is that of the original user message whose fields are copied in the MT 096 FIN  
  Copy to Central Institution Message  
  ```  
  
  > [!NOTE]
  >  MRF トレーラーでは、FIN コピーに固有ですし、中央機関メッセージには、MT 096 FIN コピーで自動的に生成されます。 このトレーラーは、MT 097 が応答を MT 096 を識別するためにフィールド 109 MT 096 FIN コピーの教育機関のサーバーの全体のメッセージにのみ使用できます。 MRF の形式は変更されます。  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)