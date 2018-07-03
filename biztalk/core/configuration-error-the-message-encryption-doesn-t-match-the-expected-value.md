---
title: 構成エラー。 メッセージの暗号化は&#39;予期される値が一致しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 99c37c7d-6654-4004-8345-9d7bfc3659b6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90b08ace29bd4cee6cd5057cdb2b18fd1956b536
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976147"
---
# <a name="configuration-error-the-message-encryption-doesn39t-match-the-expected-value"></a>構成エラー。 メッセージの暗号化は&#39;予期される値が一致しません。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                  |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                |
| 製品バージョン |                                                            [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                            |
|    イベント ID     |                                                                                        -                                                                                         |
|  イベント ソース   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                              |
|    コンポーネント    |                                                                                    AS2 エンジン                                                                                    |
|  シンボル名  |                                                                   AS2DecoderPartyEncryptionConfigurationError                                                                    |
|  メッセージ テキスト   | 構成エラー。 メッセージの暗号化が予期された値と一致しません。 送信元パートナーに問い合わせて、使用された暗号化を確認してください。 AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティの設定で暗号化が指定されているにもかかわらず、AS2 メッセージが暗号化されていないか、暗号化が有効にならないように指定されているのにメッセージが暗号化されているため、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パーティ設定で暗号化が指定されている場合は受信 AS2 メッセージが暗号化されていることを確認し、パーティ設定で暗号化を有効にしないように指定されている場合は、受信 AS2 メッセージが暗号化されていないことを確認します。 次のいずれかの操作を行います。  
  
1.  場合、**受信メッセージのプロパティのプロパティが選択されている上書き**パーティ-AS2 のプロパティ ダイアログ ボックスで、BizTalk Server 管理コンソールの AS2 メッセージの送信者 ページで、**メッセージを暗号化する必要があります**プロパティが選択されているが、メッセージが暗号化されていない、メッセージを送信したパーティにお問い合わせくださいと、メッセージを暗号化するように依頼して、再送信します。 または、オフにすることができます、**メッセージを暗号化する必要があります**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティ。  
  
2.  場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージを暗号化する必要がある**メッセージを送信したパーティに連絡し、依頼プロパティをオフにするが、メッセージが暗号化されますメッセージを暗号化し、再送信します。 選択することができます、**メッセージを暗号化する必要がある**プロパティ。