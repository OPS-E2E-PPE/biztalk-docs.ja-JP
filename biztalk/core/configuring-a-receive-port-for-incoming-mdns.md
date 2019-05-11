---
title: 構成を受信 Mdn の受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d156beae-e145-48de-9f02-37457073ef97
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b630555d5ec32ca9c1a3d48a8320f138a977284f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391388"
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a>構成を受信 Mdn の受信ポート
AS2 MDN を受信するには、作成、一方向 HTTP 受信ポート、メッセージを受信し、パーティへの応答を返します。  
  
 双方向の要求-応答の受信 MDN メッセージを受信するメッセージを使用しない必要があります AS2 の受信に使用されるポート。 受信ポート 200OK メッセージなるため、MDN 送信の不要な再試行を原因となり、受信 MDN への応答で返される MDN を要求-応答を使用します。  
  
 AS2Receive または AS2EdiReceive パイプラインのいずれかを使用して、受信した MDN を処理することができます。 ただし、AS2EdiReceive を使用する場合ことはできません MDN をルーティングするメッセージ ボックスに設定して、 **MessageBox にルーティング/配信の受信 MDN を処理する**プロパティを**受信確認**ページ一方向アグリーメント タブ。操作を実行しようと、MSN が MDN を処理できない EDI デコーダーに渡されるために、EDI エラーが発生するがします。 メッセージ ボックスに MDN が送信されない場合、AS2Decoder は EDI デコーダーに渡されませんので、MDN を消費します。  
  
 次の構成を使用して受信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**受信ポートのプロパティ。[全般]**|[ポートの種類]|一方向|  
|**受信場所のプロパティ。[全般]**|トランスポートの種類|HTTP<br /><br /> **注**EDIINT/AS2 でエンコードされたメッセージは、Mdn を転送するため、HTTP アダプタのみを使用できます。 このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。|  
|**受信場所のプロパティ。[全般]**|[受信ハンドラー]|BizTalkServerIsolatedHost|  
|**受信場所のプロパティ。[全般]**|受信パイプライン。|AS2Receive または AS2EdiReceive|  
|**HTTP トランスポートのプロパティ**|仮想ディレクトリと ISAPI 拡張|/\<仮想ディレクトリの名前\>>/btshttpreceive.dll|  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートの構成](../core/configuring-ports-for-an-as2-solution.md)