---
title: "ACK メッセージ スキーマの種類 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, ACK schemas
- acknowledgements, ACK schema types
- ACK messages
ms.assetid: da6981a0-a70a-481e-8db4-4a6851f205f1
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c29657226c993a68b8cd557a39a7837717e2c66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="ack-message-schema-types"></a>ACK メッセージ スキーマの種類
受信確認メッセージのスキーマは 2 つの形式があります。  
  
-   **一般的な確認 (ACK)**です。 アプリケーションは、特定の基幹業務アプリケーション レベルの受信確認メッセージを定義していない、またはエラーが発生したアプリケーションの処理が除外は、一般的な確認 (ACK) を使用できます。 これを使用することもできますのレベルの受信確認をそのまま使用します。 次の表は、ACK メッセージの構造を示します。  
  
    |ACK ^ 異なります ^ ACK|一般的な受信確認|章|  
    |--------------------|----------------------------|-------------|  
    |MSH|メッセージ ヘッダー|2|  
    |MSA|メッセージの受信確認|2|  
    |[エラー]|[エラー]|2|  
  
-   **遅延確認応答 (MCF)**です。 このメッセージは、HL7 バージョン 2.1 で旧バージョンとの互換性のためだけ存在します。 非同期のアプリケーション レベル受信確認、MCF メッセージの一般的なフォームを作成するプロトコルの一部として使用するとします。 次の表は、MCF メッセージの構造を示します。  
  
    |MCF ^ 異なります ^ ACK|受信確認の遅延|章|  
    |--------------------|----------------------------|-------------|  
    |MSH|メッセージ ヘッダー|2|  
    |MSA|メッセージの受信確認|2|  
    |[エラー]|[エラー]|2|  
  
 受信確認メッセージがある、MSH9 フィールドに設定するか**ACK ^\<***トリガー イベント***> ^ ACK**または**MCF ^\<** *トリガー イベント***> ^ ACK**です。 その結果、MSH9 の最初のコンポーネントは ACK スキーマを決定するだけで十分です。 ドキュメント名を[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パイプラインには、名前空間として HL7 常に含まれています。 型名は、これは ACK または MCF MSH9_1 フィールドの内容です。 上記の例と同様にその結果、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パイプラインは、HL7 の名前を持つスキーマを検索します。ACK または HL7 します。MCF、MSH9_1 フィールドの値によって決まります。 メッセージ本文のスキーマは、同じ 2.X バージョンのすべてのメッセージです。  
  
> [!NOTE]
>  内のバッチで/ACK シナリオでは、ACK のヘッダーの内容をバッチは次のようにします。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MSH1、2、8、およびユーザー インターフェイスでの構成を 15 に設定します。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]システム時刻を MSH7 を設定します。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]確認を MSH9 に設定します。  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.4 または 2.5 MSH12 に設定します。  
  
## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [メッセージ受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [受信確認エラー条件](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)