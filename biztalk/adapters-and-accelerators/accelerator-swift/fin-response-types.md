---
title: FIN 応答タイプ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, response types
- deploying, schemas
- FIN Response Reconciliation, message types
- FRR, deploying schemas
- schemas, deploying
- FIN Response Reconciliation, response types
- messages, message types
- response types [FIN Response Reconciliation]
ms.assetid: a6ef2f20-08ab-40d3-a0a5-cc4048ce0987
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54c890a5e0f51207cce1897b10095a87ae438793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22208066"
---
# <a name="fin-response-types"></a>FIN 応答の種類
FIN 対応調整 (FRR) は、カテゴリ、0 ~ 9 SWIFT FIN メッセージに応答を調整します。 SWIFT FIN アプリケーションは常に、少なくとも 1 つと、複数の可能性のあるいずれかの確認 (ACK) の送信、これらの FIN メッセージに応答または否定受信確認 (NAK)。 次の表に、メッセージの送信および受信の種類を (応答) FRR によって処理されるメッセージ。  
  
|送信/<br /><br /> 受信|メッセージ型|メッセージの状態|  
|----------------------------|------------------|--------------------|  
|送信|すべてのカテゴリ、0 ~ 9 SWIFT FIN メッセージ型|なし|  
|受信|MQ 系列パン/NAN (MQ Series トランスポート レベル ACK/NAK)|MQSeries トランスポートの受信確認|  
||MT010 (配信不能警告)|SWIFT が正常に送信元は、取引先、メッセージ、パートナーがメッセージを受信することを示す値がありません。 場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]は複数の配信不能の警告 (NDW) メッセージを受信ループを実行し、次の予期されるメッセージを待ちます。|  
||MT011 (配信通知)|SWIFT が正常に送信元は、パートナーにメッセージの送受信、パートナーがメッセージを受信することを示す値です。|  
||MT012 (送信者 Notification)|SWIFT から元のメッセージを正常に受信された[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。|  
||MT015 (DNK、または遅延 NAK)|SWIFT が、パートナーに、元のメッセージを正常に送信していないがします。|  
||MT019 (通知を中止)|SWIFT のメッセージ転送が中止されました。|  
||MTS21_FIN_ACKNAK (受信確認メッセージまたは否定受信確認 (ACK/NAK)、LT によって送信された FIN メッセージの)|SWIFT 成功と失敗からのメッセージを受信した[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。 このメッセージは、このような場合の両方について説明します。 ACK と NAK であるかは、メッセージ (ACK 用の「0」) と NAK の「1」の 451 フィールドの値によって決まります。 これに配信された最初の応答になります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]です。|  
  
## <a name="deployment-of-schemas-for-frr"></a>FRR 用にスキーマの展開  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップでは、(上記の表に示すように) として FrrSchemas.dll でシステム レベルのすべてのメッセージのスキーマが配置されます。 FRR オーケストレーションでは、これらのスキーマを展開する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ FrrSchemas.dll でこれらのスキーマを配置するには、する必要はありませんしてする必要がある別のプロジェクトでこれらのスキーマを展開します。 そうと、エラーが生成されます。  
  
 FRRSchemas.dll には、次のスキーマが含まれています。  
  
-   TransportAck  
  
-   MT010  
  
-   MT011  
  
-   MT012  
  
-   MT015  
  
-   MT019  
  
-   MTS21_FIN_ACKNAK