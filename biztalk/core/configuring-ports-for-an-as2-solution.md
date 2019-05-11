---
title: AS2 ソリューションのポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715358b1-4226-476b-b0de-2b91434aa24c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b045a18893153d6c2982b7b6214b7eea6e1852fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390860"
---
# <a name="configuring-ports-for-an-as2-solution"></a>AS2 ソリューションのポートを構成します。
次の受信に使用でき、AS2 経由で EDI および非 EDI メッセージを送信する送信ポート。  
  
 **受信ポート**  
  
|受信するには|送信するには|ポートの種類|  
|----------------|-------------|------------------|  
|EDI または非 EDI メッセージまたは確認|MDN 応答 (同期モードの場合) または HTTP 応答 (非同期モードの場合)|双方向の要求-応答の HTTP 受信ポート|  
|MDN 応答|-|一方向 HTTP 受信ポート|  
  
 **送信ポート**  
  
|送信するには|受信するには|ポートの種類|  
|-------------|----------------|------------------|  
|EDI または非 EDI メッセージまたは確認<br /><br /> (アグリーメント ベースのルーティング)|-|静的な一方向の HTTP 送信ポート|  
|EDI または非 EDI メッセージまたは確認<br /><br /> (コンテンツ ベースのルーティング)|MDN 応答|動的な双方向送信請求-応答 HTTP 送信ポート|  
|EDI または非 EDI メッセージまたは確認<br /><br /> (コンテンツ ベースのルーティング)|-|動的な一方向の HTTP 送信ポート|  
|非同期の MDN 応答<br /><br /> (コンテンツ ベースのルーティング)|-|動的な一方向送信ポート|  
|非同期の MDN 応答|-|静的な一方向送信ポート|  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [AS2 経由でのメッセージの受信ポートの構成](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [受信 MDN の受信ポートの構成](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [AS2 経由でのメッセージの静的送信ポートの構成](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [AS2 経由でのメッセージの動的送信ポートの構成](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [AS2 経由の非同期 MDN の静的送信ポートの構成](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [AS2 経由の非同期 MDN の動的送信ポートの構成](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a>参照  
 [BizTalk Server AS2 ソリューションの開発と構成](../core/developing-and-configuring-biztalk-server-as2-solutions.md)