---
title: "構成エラー。 メッセージの暗号化ではありません &#39; 期待値と一致する t |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b17460c4dcd6f9d2a8c18e5e7284cd36940d6820
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a>構成エラー。 メッセージの暗号化ではありません &#39; 一致予期される値
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|AS2DecoderPartyEncryptionConfigurationError|  
|メッセージ テキスト|構成エラー。 メッセージの暗号化が予期された値と一致しません。 送信元パートナーに問い合わせて、使用された暗号化を確認してください。 AS2-から:"{0}"AS2-を:"\ "MessageID:"\ {2 \}"|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティの設定で暗号化が指定されているにもかかわらず、AS2 メッセージが暗号化されていないか、暗号化が有効にならないように指定されているのにメッセージが暗号化されているため、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パーティ設定で暗号化が指定されている場合は受信 AS2 メッセージが暗号化されていることを確認し、パーティ設定で暗号化を有効にしないように指定されている場合は、受信 AS2 メッセージが暗号化されていないことを確認します。 次のいずれかの操作を行います。  
  
1.  場合、**受信メッセージのプロパティのプロパティが選択されている上書き**パーティの AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの送信者 ページで、[!INCLUDE[prague](../includes/prague-md.md)]管理コンソールで、**メッセージを暗号化する必要があります**プロパティが選択されているが、メッセージが暗号化されていない、メッセージを送信したパーティに連絡し、メッセージを暗号化するように依頼して、再送信します。 クリアするか、**メッセージを暗号化する**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティです。  
  
2.  場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージを暗号化する**プロパティをオフにしたが、メッセージが暗号化されて、メッセージを送信したパーティに連絡しように依頼してメッセージを暗号化して、再送信する必要はありません。 選択することができます、**メッセージを暗号化する**プロパティです。