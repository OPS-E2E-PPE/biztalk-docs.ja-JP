---
title: FIN 応答の種類 |Microsoft Docs
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
ms.openlocfilehash: 382e0e628d01903a6274dd3f0321379f71fc7a15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995403"
---
# <a name="fin-response-types"></a>FIN 応答の種類
FIN 応答の調整 (FRR) は、0 ~ 9 のカテゴリ SWIFT FIN メッセージに応答を調整します。 少なくとも 1 つと、場合によっては複数のいずれかの確認 (ACK) を送信する SWIFT FIN アプリケーションは常に FIN メッセージへの応答、否定受信確認 (NAK)。 次の表に、送信および受信のメッセージ型 (応答) FRR によって処理されるメッセージ。  


| 送信/<br /><br /> 受信 |                                             メッセージ型                                              |                                                                                                                                                                                                                             メッセージの状態                                                                                                                                                                                                                              |
|-------------------------------|-------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|           送信            |                              すべてのカテゴリ 0 ~ 9 SWIFT FIN メッセージの種類                              |                                                                                                                                                                                                                                   なし                                                                                                                                                                                                                                   |
|            受信            |                         MQ Series パン/NAN (MQ Series トランス ポート レベル ACK/NAK)                         |                                                                                                                                                                                                                    MQSeries トランスポートの受信確認                                                                                                                                                                                                                    |
|                               |                                     MT010 (警告の配信不能)                                      |                                                                     正常に元に送信する SWIFT では、パートナーにメッセージしますが、パートナーがメッセージを受信することを示す値がありません。 場合[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]は複数の警告 (NDW) の配信不能メッセージを受信ループを実行し、[次へ] の予期されるメッセージを待ちます。                                                                     |
|                               |                                     MT011 (配信通知)                                     |                                                                                                                                                                     SWIFT 元が正常に送信は、パートナーにメッセージの送受信、パートナーがメッセージを受信することを示す値です。                                                                                                                                                                      |
|                               |                                      MT012 (送信者の通知)                                      |                                                                                                                                                            SWIFT からの元のメッセージを正常に受信[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。                                                                                                                                                             |
|                               |                                      MT015 (DNK、または遅延 NAK)                                      |                                                                                                                                                                                                  SWIFT が、パートナーに、元のメッセージを正常に送信していませんが。                                                                                                                                                                                                   |
|                               |                                      MT019 (通知を中止)                                       |                                                                                                                                                                                                                 SWIFT でメッセージの転送が中止されました。                                                                                                                                                                                                                  |
|                               | MTS21_FIN_ACKNAK (受信確認または否定応答 (ACK/NAK)、LT によって送信された FIN メッセージの) | SWIFT からのメッセージを受信成功したか、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 このメッセージは、このような場合の両方について説明します。 ACK または NAK は、メッセージ (確認用の「0」) と NAK の「1」の 451 フィールドの値によって決まります。 これは、最初の応答への提供となります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]します。 |

## <a name="deployment-of-schemas-for-frr"></a>FRR のスキーマの配置  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] セットアップでは、(上記の表に示した) と、システム レベルのすべてのメッセージの FrrSchemas.dll 内のスキーマが配置されます。 FRR オーケストレーションでは、これらのスキーマを展開する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]セットアップ FrrSchemas.dll でこれらのスキーマでは、そうでない必要があり、する必要はありませんこれらのスキーマを別のプロジェクトをデプロイします。 そうと、エラーが生成されます。  

 FRRSchemas.dll には、次のスキーマが含まれています。  

-   TransportAck  

-   MT010  

-   MT011  

-   MT012  

-   MT015  

-   MT019  

-   MTS21_FIN_ACKNAK