---
title: システム トレーラー |Microsoft ドキュメント
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
ms.openlocfilehash: a0a8c5b7be12a90aa2d31e828298cf7b95834036
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214082"
---
# <a name="system-trailers"></a>システムのトレーラー
システムのトレーラーは、SWIFT メッセージの詳細を追加または特別なを伝達します。 いずれかの最初の 3 つのシステム トレーラーは、次の順序で発生しました。 残りのシステム トレーラーは、任意の順序で発生します。  
  
|トレーラー コード|名前|  
|------------------|----------|  
|**CHK**|Checksum|  
|**SYS**|システムにメッセージが発生しました。|  
|**TNG**|トレーニング|  
|**PDM**|使用可能な重複するメッセージ|  
|**DLM**|遅延メッセージ|  
|**MRF**|メッセージのリファレンス|  
  
-   **システムでは、(SYS) のメッセージのトレーラーを開始します。** システム メッセージまたは PLT システムによって生成される、サービスのメッセージは、SYS トレーラーを持っています。 要求の MIR が含まれて、および時間を含めることはすべて 01 のサービス識別子を持つシステム メッセージを要請します。  
  
     次のコードでは、SYS トレーラー形式の例を示します。  
  
    ```  
    {SYS:[<time><mir>]}  
    ```  
  
-   **テストとメッセージ (TNG) トレーラーをトレーニングします。** TNG トレーラーは FIN および GPA メッセージ (01 のサービス識別子) を使用して、送信または、テストとトレーニング論理ターミナル (LT) に配信するために必須です。 このトレーラーがあり、タグにのみ、値はありません。  
  
     次のコードでは、TNG トレーラー形式の例を示します。  
  
    ```  
    {TNG:}  
    ```  
  
-   **考えられる重複する出力 (PDE) トレーラです。** メッセージの送信先は、PDE トレーラーを使用します。 FIN ユーザー-ユーザーへのメッセージ (01 のサービス識別子) と銀行メッセージ用に予約されてメッセージのカテゴリにのみ適用されます。 システムでは、複数 PDEs を含めることがあります。 システムは、順を確認したり (メッセージの最大の長さ) を除く数に制限はありません。  
  
     システムは、ユーザーとシステム メッセージに適用 PDE トレーラーを正しい形式を受け入れますが、それらを処理しません。 つまり、システムは、元のメッセージが存在するかどうかはチェックされません。 そのため、システムが PDE トレーラーで 2 回送信取得要求を処理可能性があります: システムが、元のメッセージを受信した場合。  
  
     次のコードでは、PDE トレーラー形式の例を示します。  
  
    ```  
    {PDE:[<time><mir>]}  
    where <time><mir> refers to the emission of the previous possible issue  
    ```  
  
-   **遅延メッセージ (DLM) トレーラです。** DLM トレーラーは、その陳腐化の期間を超えているすべての FIN ユーザー-ユーザーへの出力メッセージに追加されます。 GPA または FIN のシステム メッセージにこのトレーラが表示されたら、無視できます。 このトレーラーがあり、タグにのみ、値はありません。  
  
     陳腐化期間は次のとおりです。  
  
    -   U = 15 分  
  
    -   N = 100 分  
  
     DLM トレーラー形式の例を次のコードには。  
  
    ```  
    {DLM:}  
    ```  
  
-   **使用可能な重複するメッセージ (PDM) トレーラです。** 出力メッセージ (GPA および FIN 01 のサービス識別子を持つ) に、PDM トレーラーが、システムによって追加された前の配布が有効でないために再送信されます。 PLT システムでは、PDM トレーラーでレポート要求を受信した場合、応答は (省略可能な配信のリファレンス) なし plain PDM を持ちます。 ユーザーには、unsuccessful 配信失敗の回数他 Pdm を追加する可能性があります。  
  
     次のコードでは、PDM トレーラー形式の例を示します。  
  
    ```  
    {PDM:[<time><mor>]}  
    where <time> and the Message Output Reference <mor> are that of the previous attempt  
    ```  
  
-   **メッセージ (MRF) の参照をトレーラです。** MRF トレーラーは、サーバーの全体の機関メッセージへの MT 096 FIN コピーで元のユーザー メッセージのメッセージ参照を指定します。  
  
     次のコードでは、MRF トレーラー形式の例を示します。  
  
    ```  
    {MRF:<date><full-time><mir>}  
    where <mir> is that of the original user message whose fields are copied in the MT 096 FIN  
    Copy to Central Institution Message  
    ```  
  
    > [!NOTE]
    >  MRF トレーラーは FIN コピーに特有の MT 096 FIN へのコピーで中央管理機関のメッセージが自動的に生成します。 このトレーラーは、MT 097 を応答 MT 096 を識別するのにフィールド 109 MT 096 FIN コピーの中央管理機関のメッセージをでのみ使用できます。 MRF の形式は変更されます。  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)