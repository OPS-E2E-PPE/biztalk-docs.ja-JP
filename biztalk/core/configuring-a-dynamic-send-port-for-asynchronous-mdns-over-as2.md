---
title: AS2 経由で非同期 Mdn の動的送信ポートの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72646c90-89db-4884-824b-6921bb824f8d
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c6d8c962e1a417e1b97fd6fe8224718785133fd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391421"
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a>AS2 経由での非同期 Mdn の動的送信ポートを構成します。
非同期 MDN の EDIINT/AS2 でエンコードされたメッセージを HTTP/HTTPS 経由で送信するには、次の構成で動的な HTTP 送信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ:[全般]**|ポートの種類|動的な一方向|  
|**送信ポートのプロパティ:[全般]**|[送信パイプライン]|AS2Send|  
|**送信ポートのプロパティ:フィルター**|プロパティ|EdiIntAS.IsAS2AsynchronousMdn|  
|**送信ポートのプロパティ:フィルター**|演算子|==|  
|**送信ポートのプロパティ:フィルター**|値|True|  
  
 非同期 MDN に含まれるアドレスに送信する必要があります、 **- Receipt-delivery-option**受信 AS2 メッセージのヘッダー。 動的送信ポートのためには、静的な送信ポートがメッセージを送信する一方、**送信先 URL**で送信ポートの定義。 この例外は場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティで設定されて**検証**の一方向アグリーメント タブのページ、**アグリーメントプロパティ** ダイアログ ボックス。 送信ポートに入力された URL に MDN メッセージを送信できる場合、 **- Receipt-delivery-option**アグリーメントのプロパティ。 ただし、これを行うために使用する送信ポートには、動的送信ポートをする必要があります、しない静的な送信ポート。  
  
 Mdn と EDI の両方を返すには、この送信ポートを構成する受信確認。 EDIINT/AS2 でエンコードされたメッセージは正常に HTTP または HTTPS 経由で転送が EDI でエンコードされたペイロードの処理が失敗した場合、元のメッセージの送信者は MDN の受信両方、成功の AS2 処理と EDI を示す場合は、インスタンスのEDI の処理の失敗を示す受信確認。 EDI でエンコードされたペイロードは中断され、エラー通知されます。  
  
## <a name="functionality"></a>機能  
 送信ポートとパイプラインは MDN を送信するには、次を行う必要があります。  
  
-   フィルタ リングして、MDN を取得、`EdiIntAS.IsAS2AsynchronousMdn==True`プロパティ。  
  
-   AS2 メッセージを構築します。 このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。  
  
-   内のアドレスに MDN をルーティング、 **- Receipt-delivery-option**メッセージのヘッダー内の行。  
  
    > [!NOTE]
    >  場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティで設定されて**検証**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスで、送信ポートは送信 MDN メッセージに入力された URL に、 **- Receipt-delivery-option**アグリーメントのプロパティに記載されているアドレスがない **-Receipt-delivery-option**受信 AS2 メッセージのヘッダー。  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートの構成](../core/configuring-ports-for-an-as2-solution.md)