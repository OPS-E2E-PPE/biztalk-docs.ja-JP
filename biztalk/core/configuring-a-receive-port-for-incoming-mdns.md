---
title: "構成、着信 Mdn の受信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d156beae-e145-48de-9f02-37457073ef97
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8585ae946e15d2677e225d42f6c123d5dd5e8e49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a>受信 MDN の受信ポートの構成
AS2 MDN を受信するには、メッセージを受信してパーティに応答を返すための一方向の HTTP 受信ポートを作成します。  
  
 AS2 メッセージの受信に使用する双方向の要求 - 応答の受信ポートは、MDN メッセージの受信には使用できません。 MDN に要求 - 応答受信ポートを使用すると、受信 MDN に応答して 200OK メッセージが返されなくなるため、MDN 送信の不要な再試行が行われます。  
  
 受信 MDN の処理には、AS2Receive と AS2EdiReceive のいずれかのパイプラインを使用できます。 ただし、AS2EdiReceive を使用する場合することはできませんに MDN をルーティング、メッセージ ボックス データベースを設定して、**メッセージ ボックスに受信 MDN をルーティング/配信用処理**プロパティを**受信確認**ページ一方向アグリーメント タブです。この操作を実行しようとすると、MDN を処理できない EDI デコーダーに対して MDN が渡されるため、EDI エラーが発生します。 MDN がメッセージ ボックスに送信されないと、AS2 デコーダーは MDN を利用 (消費) するため、MDN は EDI デコーダーに渡されません。  
  
 次の構成を使用して受信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**受信ポートのプロパティ: 全般**|[ポートの種類]|一方向|  
|**受信場所のプロパティ: 全般**|トランスポートの種類|HTTP<br /><br /> **注**mdn の場合、される EDIINT/AS2 でエンコードされたメッセージを転送するため、HTTP アダプタのみを使用できます。 このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。|  
|**受信場所のプロパティ: 全般**|[受信ハンドラー]|BizTalkServerIsolatedHost|  
|**受信場所のプロパティ: 全般**|受信パイプライン。|AS2Receive または AS2EdiReceive|  
|**HTTP トランスポートのプロパティ**|仮想ディレクトリと ISAPI 拡張|/\<仮想ディレクトリの名前\>>/btshttpreceive.dll|  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートの構成](../core/configuring-ports-for-an-as2-solution.md)