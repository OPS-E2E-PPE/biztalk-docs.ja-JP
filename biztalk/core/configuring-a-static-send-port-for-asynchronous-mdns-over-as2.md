---
title: AS2 経由で Mdn が非同期の静的送信ポートの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc43e767-d9d7-4b02-b3fc-0cfdfd6e61c4
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e023dc6f2165e9427fa57e109715dda6cdb258f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968376"
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a>AS2 経由の非同期 MDN の静的送信ポートの構成
このトピックでは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成して、EDIINT/AS2 でエンコードされた非同期 MDN メッセージを静的送信ポート経由で送信する方法について説明します。 構成では、静的送信ポートを作成し、必要に応じて、送信ポートで使用される暗号化証明書のセットアップを行います。  
  
> [!NOTE]
>  静的送信ポートの代わりに、動的送信ポートを構成して MDN メッセージを送信することもできます。 詳細については、次を参照してください。 [AS2 経由で Mdn が非同期の動的送信ポートを構成する](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)です。  
  
 MDN メッセージを送信するには、次の構成を使用して一方向の HTTP 送信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ: 全般**|ポートの種類|静的な一方向送信ポート|  
|**送信ポートのプロパティ: 全般**|トランスポートの種類|HTTP**注:** EDIINT/AS2 でエンコードされたメッセージを転送するため、HTTP アダプタのみを使用できます。 このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。|  
|**送信ポートのプロパティ: 全般**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ: 全般**|[送信パイプライン]|AS2Send|  
|**HTTP トランスポートのプロパティ**|送信先 URL|\<送信先 URL の文字列\>|  
|**HTTP トランスポートのプロパティ**|[チャンク エンコードを有効にする]|クリア|  
|**送信ポートのプロパティ: フィルター**|プロパティ|EdiIntAS.IsAS2AsynchronousMdn**注:** で指定されたアドレス宛ての MDN メッセージだけが送信ポートであることを確認する追加のフィルター式がこのサブスクリプション フィルターによって選択されても指定する必要があります。|  
|**送信ポートのプロパティ: フィルター**|演算子|==|  
|**送信ポートのプロパティ: フィルター**|値|True|  
|**送信ポートのプロパティ: 証明書**|"一般名" および "拇印"|送信 MDN メッセージで暗号化証明書を使用する場合は、証明書の名前および拇印を入力します。|  
  
 非同期 MDN で指定されたアドレスに送信する必要があります、 **- Receipt-delivery-option**受信した AS2 メッセージのヘッダー。 動的送信ポートのためには、自動的に対し、静的な送信ポートがメッセージを送信、**送信先 URL**送信ポートのプロパティにします。 静的送信ポートを使用して非同期 MDN を送信するときは、送信先の URL が正しいことを確認してください。  
  
## <a name="functionality"></a>機能  
 送信ポートとパイプラインは、MDN を送信する際に次の処理を行う必要があります。  
  
-   `EdiIntAS.IsAS2AsynchronousMdn==True` プロパティに基づいてフィルター処理を行い、MDN を取得します。  
  
-   AS2 メッセージを生成します。 このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)です。  
  
-   送信ポートで定義されたアドレスに MDN をルーティングする。  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートの構成](../core/configuring-ports-for-an-as2-solution.md)