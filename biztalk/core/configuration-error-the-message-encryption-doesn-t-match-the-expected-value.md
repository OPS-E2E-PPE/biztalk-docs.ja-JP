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
ms.openlocfilehash: 51756b202d554b2ea85eb8e302497729f524ea2a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356508"
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
|  メッセージ テキスト   | 構成エラー。 メッセージの暗号化は、予期される値と一致しません。 送信元パートナーに連絡し、暗号化の使用を確認します。 AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、暗号化は、パーティ設定で指定されたが、AS2 メッセージが暗号化されていない、または暗号化を指定していないためにで、AS2 メッセージが受信パイプラインの AS2 デコーダー コンポーネントでした処理することを示します有効な場合しますが、メッセージが暗号化されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、暗号化は、パーティ設定で指定されたまたは暗号化が指定されている場合、受信 AS2 メッセージは暗号化されません、パーティ設定で有効にしないようにする場合、受信 AS2 メッセージが暗号化されていることを確認します。 次のいずれかの操作を行います。  
  
1.  場合、**受信メッセージのプロパティのプロパティが選択されている上書き**パーティ-AS2 のプロパティ ダイアログ ボックスで、BizTalk Server 管理コンソールの AS2 メッセージの送信者 ページで、**メッセージを暗号化する必要があります**プロパティが選択されているが、メッセージが暗号化されていない、メッセージを送信したパーティにお問い合わせくださいと、メッセージを暗号化するように依頼して、再送信します。 または、オフにすることができます、**メッセージを暗号化する必要があります**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティ。  
  
2.  場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージを暗号化する必要がある**メッセージを送信したパーティに連絡し、依頼プロパティをオフにするが、メッセージが暗号化されますメッセージを暗号化し、再送信します。 選択することができます、**メッセージを暗号化する必要がある**プロパティ。