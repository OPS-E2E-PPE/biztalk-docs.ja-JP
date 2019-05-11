---
title: ACK メッセージ スキーマの種類 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, ACK schemas
- acknowledgements, ACK schema types
- ACK messages
ms.assetid: da6981a0-a70a-481e-8db4-4a6851f205f1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923cd9122f1b0d322f5a12d3be38f660a67d054e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247570"
---
# <a name="ack-message-schema-types"></a>ACK メッセージ スキーマの種類
受信確認メッセージのスキーマは 2 つの形式があります。  

- **一般的な確認 (ACK)** します。 一般的な確認 (ACK) を使用するには、アプリケーションが特別な基幹業務アプリケーション レベルの受信確認メッセージを定義していない、またはアプリケーションの処理にエラーが発生しました。 これを使用することもできますの受信確認のレベルをそのまま使用します。 次の表では、ACK メッセージの構造を示します。  


  | ACK^varies^ACK | 一般的な受信確認 | 」の章 |
  |----------------|------------------------|---------|
  |      MSH       |     メッセージ ヘッダー     |    2    |
  |      MSA       | メッセージの受信確認 |    2    |
  |    [エラー]     |         [エラー]          |    2    |


- **遅延確認応答 (mcf という)** します。 このメッセージは、HL7 バージョン 2.1 の旧バージョンと互換性のためにのみ存在します。 非同期のアプリケーション レベル確認、MCF メッセージの一般的なフォームを作成するプロトコルの一部として使用するとします。 次の表では、MCF メッセージの構造を示します。  

  |MCF^varies^ACK|受信確認の遅延|」の章|  
  |--------------------|----------------------------|-------------|  
  |MSH|メッセージ ヘッダー|2|  
  |MSA|メッセージの受信確認|2|  
  |[エラー]|[エラー]|2|  

  受信確認メッセージがある、MSH9 フィールドに設定するか**ACK ^\<**<em>トリガー イベント</em>**\>^ ACK**または**MCF ^\<** <em>トリガー イベント</em>**\>^ ACK**します。 その結果、MSH9 の最初のコンポーネントは ACK スキーマを決定するための十分です。 ドキュメント名を Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パイプラインの名前空間として HL7 を常に含まれます。 型名は、これは ACK または MCF MSH9_1 フィールドの内容です。 結果として、上記の例のように、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]パイプラインが HL7 の名前を持つスキーマを探します。ACK または HL7 します。MCF、MSH9_1 フィールドの値によって決まります。 メッセージ本文のスキーマは、2.X バージョンのすべてのメッセージに同じです。  

> [!NOTE]
>  内のバッチで/バッチ アウト シナリオの確認、ACK ヘッダーの内容は次のようにします。  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH1、2、8、15 日に、ユーザー インターフェイスの構成を設定します。  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH7 システム時刻に設定します。  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH9 を確認する設定します。  

- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 2.4、2.5 MSH12 に設定します。  

## <a name="see-also"></a>参照  
 [作成して、受信確認の処理](../../adapters-and-accelerators/accelerator-hl7/creating-and-processing-acknowledgments.md)   
 [メッセージの受信確認セグメント](../../adapters-and-accelerators/accelerator-hl7/message-acknowledgment-segment.md)   
 [Ack を受信するための送信ポートの設定](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)   
 [受信確認エラーの条件](../../adapters-and-accelerators/accelerator-hl7/acknowledgment-error-conditions.md)