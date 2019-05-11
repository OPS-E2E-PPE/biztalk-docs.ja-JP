---
title: AS2 経由で非同期 Mdn の静的送信ポートの構成 |Microsoft Docs
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
ms.openlocfilehash: 24119db6566207455867b0a2e6b998870d445d74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391406"
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a>AS2 経由での非同期 Mdn の静的送信ポートを構成します。
このトピックでは、構成する方法を説明[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]静的経由での非同期の MDN の EDIINT/AS2 でエンコードされたメッセージを送信するポートを送信します。 この構成には、静的な送信ポートとかどうか、必要な暗号化を設定する証明書の送信ポートで使用する作成が含まれています。  
  
> [!NOTE]
>  MDN メッセージを送信するには、送信ポートの静的ではなく動的送信ポートを構成することができます。 詳細については、次を参照してください。 [AS2 経由での非同期 Mdn の動的送信ポートを構成する](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)します。  
  
 MDN メッセージを送信するには、次の構成で一方向 HTTP 送信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ:[全般]**|ポートの種類|静的な一方向送信ポート|  
|**送信ポートのプロパティ:[全般]**|トランスポートの種類|HTTP**に注意してください。** EDIINT/AS2 でエンコードされたメッセージには、HTTP アダプタのみ使用できます。 このトランスポートは、HTTP アダプタ以外のアダプタでは使用できません。|  
|**送信ポートのプロパティ:[全般]**|送信ハンドラー|BizTalkServerApplication|  
|**送信ポートのプロパティ:[全般]**|[送信パイプライン]|AS2Send|  
|**HTTP トランスポートのプロパティ**|送信先 URL|\<送信先 URL の文字列\>|  
|**HTTP トランスポートのプロパティ**|[チャンク エンコードを有効にする]|クリア|  
|**送信ポートのプロパティ:フィルター**|プロパティ|EdiIntAS.IsAS2AsynchronousMdn**に注意してください。** この送信ポートで指定したアドレス宛ての MDN メッセージだけがこのサブスクリプション フィルターによって取り出されることを確認する追加のフィルター式を指定することも必要があります。|  
|**送信ポートのプロパティ:フィルター**|演算子|==|  
|**送信ポートのプロパティ:フィルター**|値|True|  
|**送信ポートのプロパティ:証明書**|"一般名" および "拇印"|送信 MDN メッセージの暗号化証明書を使用する場合は、証明書名と拇印を入力します。|  
  
 指定されたアドレスに非同期 MDN を送信する必要があります、 **- Receipt-delivery-option**受信 AS2 メッセージのヘッダー。 動的送信ポートのためには、自動的に対し、静的な送信ポートがメッセージを送信、**送信先 URL**で送信ポートのプロパティ。 非同期 MDN では、静的な送信ポートを送信する場合に送信する URL が正しいことを確認します。  
  
## <a name="functionality"></a>機能  
 送信ポートとパイプラインは MDN を送信するには、次を行う必要があります。  
  
-   フィルタ リングして、MDN を取得、`EdiIntAS.IsAS2AsynchronousMdn==True`プロパティ。  
  
-   AS2 メッセージを構築します。 このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)します。  
  
-   送信ポートで定義されているアドレスに MDN をルーティングします。  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートの構成](../core/configuring-ports-for-an-as2-solution.md)