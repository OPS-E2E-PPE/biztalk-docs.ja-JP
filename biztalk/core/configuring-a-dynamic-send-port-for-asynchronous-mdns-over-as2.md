---
title: "AS2 経由で Mdn が非同期の動的送信ポートの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72646c90-89db-4884-824b-6921bb824f8d
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 754917ed1a089e3182c8543e8a132a9eff73615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a>AS2 経由の非同期 MDN の動的送信ポートの構成
EDIINT/AS2 でエンコードされた非同期 MDN メッセージを HTTP/HTTPS 経由で送信するには、次のように構成された動的な HTTP 送信ポートを作成します。  
  
|場所|プロパティ|設定|  
|--------------|--------------|-------------|  
|**送信ポートのプロパティ: 全般**|ポートの種類|動的な一方向|  
|**送信ポートのプロパティ: 全般**|[送信パイプライン]|AS2Send|  
|**送信ポートのプロパティ: フィルター**|プロパティ|EdiIntAS.IsAS2AsynchronousMdn|  
|**送信ポートのプロパティ: フィルター**|演算子|==|  
|**送信ポートのプロパティ: フィルター**|値|True|  
  
 非同期 MDN に含まれているアドレスに送信する必要があります、 **- Receipt-delivery-option**受信した AS2 メッセージのヘッダー。 動的送信ポートのためには、静的な送信ポートがメッセージを送信する一方、**送信先 URL**送信ポートの定義にします。 この例外は場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ設定されて**検証**の一方向アグリーメント タブのページ、**アグリーメントプロパティ** ダイアログ ボックス。 送信ポートに入力された URL に MDN メッセージを送信できる場合は、 **- Receipt-delivery-option**アグリーメントのプロパティです。 ただし、その際に使用される送信ポートは、静的送信ポートではなく動的送信ポートである必要があります。  
  
 この送信ポートは、MDN と EDI 受信確認の両方を返すように構成できます。 インスタンスで、EDIINT/AS2 でエンコードされたメッセージが HTTP/HTTPS 経由で正常に送信されたが、EDI でエンコードされたペイロードの処理が失敗した場合、元のメッセージの送信者は、AS2 が正常に処理されたことを示す MDN と EDI の処理が失敗したことを示す EDI 受信確認の両方を受け取ります。 EDI でエンコードされたペイロードは中断され、エラー通知です。  
  
## <a name="functionality"></a>機能  
 送信ポートとパイプラインは、MDN を送信する際に次の処理を行う必要があります。  
  
-   `EdiIntAS.IsAS2AsynchronousMdn==True` プロパティに基づいてフィルター処理を行い、MDN を取得します。  
  
-   AS2 メッセージを生成します。 このプロセスの詳細については、次を参照してください。[送信 AS2 メッセージを生成する](../core/generating-an-outgoing-as2-message.md)です。  
  
-   アドレスに MDN をルーティングする、 **- Receipt-delivery-option**メッセージのヘッダー行にします。  
  
    > [!NOTE]
    >  場合、**検証および MDN に対してメッセージ ヘッダーの代わりにアグリーメントの設定を使用して**プロパティ設定されて**検証**の一方向アグリーメント タブのページ、**アグリーメントのプロパティ** ダイアログ ボックスで、送信ポートから送信 MDN メッセージに入力された URL に、 **- Receipt-delivery-option**アグリーメントのプロパティに記載されているアドレスがない**-Receipt-delivery-option**受信した AS2 メッセージのヘッダー。  
  
## <a name="see-also"></a>参照  
 [AS2 ソリューションのポートを構成します。](../core/configuring-ports-for-an-as2-solution.md)