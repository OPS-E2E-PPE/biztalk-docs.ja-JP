---
title: "AS2 ソリューションのポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 715358b1-4226-476b-b0de-2b91434aa24c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8f02c5de0edd7956f00e10ce8782e4865033076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-ports-for-an-as2-solution"></a>AS2 ソリューションのポートの構成
AS2 経由で EDI メッセージおよび非 EDI メッセージを転送するには、次の受信ポートと送信ポートを使用します。  
  
 **受信ポート**  
  
|受信対象|送信対象|ポートの種類|  
|----------------|-------------|------------------|  
|EDI メッセージ、非 EDI メッセージ、または受信確認|MDN 応答 (同期モードの場合) または HTTP 応答 (非同期モードの場合)|双方向 (要求 - 応答) の HTTP 受信ポート|  
|MDN 応答|-|一方向の HTTP 受信ポート|  
  
 **送信ポート**  
  
|送信対象|受信対象|ポートの種類|  
|-------------|----------------|------------------|  
|EDI メッセージ、非 EDI メッセージ、または受信確認<br /><br /> (アグリーメント ベースのルーティング)|-|静的な一方向の HTTP 送信ポート|  
|EDI メッセージ、非 EDI メッセージ、または受信確認<br /><br /> (コンテンツ ベースのルーティング)|MDN 応答|動的な双方向 (送信請求 - 応答) の HTTP 送信ポート|  
|EDI メッセージ、非 EDI メッセージ、または受信確認<br /><br /> (コンテンツ ベースのルーティング)|-|動的な一方向の HTTP 送信ポート|  
|非同期の MDN 応答<br /><br /> (コンテンツ ベースのルーティング)|-|動的な一方向の送信ポート|  
|非同期の MDN 応答|-|静的な一方向の送信ポート|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [構成、AS2 経由でメッセージの受信ポート](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [構成、着信 Mdn の受信ポート](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [AS2 経由でメッセージの静的送信ポートを構成します。](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [AS2 経由でメッセージの動的送信ポートを構成します。](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [AS2 経由で Mdn が非同期の静的送信ポートを構成します。](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [AS2 経由で Mdn が非同期の動的送信ポートを構成します。](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a>参照  
 [開発と BizTalk Server AS2 ソリューションの構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)