---
title: 構成エラー。 メッセージの署名は&#39;t が予期される値と一致します。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a89d1124bc417b8af4d18271b05d3579d6935b99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391504"
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a>構成エラー。 メッセージの署名は&#39;t が予期される値と一致します。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                              |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                              |
| 製品バージョン |                                                          [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                          |
|    イベント ID     |                                                                                      -                                                                                       |
|  イベント ソース   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                            |
|    コンポーネント    |                                                                                  AS2 エンジン                                                                                  |
|  シンボル名  |                                                                   AS2DecoderPartySigningConfigurationError                                                                   |
|  メッセージ テキスト   | 構成エラー。 メッセージの署名と、予期される値と一致しません。 送信元パートナーに連絡し、署名の使用を確認します。 AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティ設定で署名が指定されてが AS2 メッセージが署名されていない、または有効にするには、いない署名が指定されているためにで、AS2 メッセージが受信パイプラインの AS2 デコーダー コンポーネントでした処理することを示しますメッセージの署名します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、として指定は、パーティ設定で署名が指定されている場合、メッセージが署名されても、受信 AS2 メッセージが署名されていないことに署名する場合、受信 AS2、パーティ設定で無効になっていることを確認します。 次のいずれかの操作を行います。  
  
1.  場合、**受信メッセージのプロパティをオーバーライド**として、BizTalk Server 管理コンソールでの AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの送信者 ページで、パーティ プロパティが選択されている、**メッセージは署名付きをする必要があります**プロパティが選択されているが、メッセージが署名されていない、メッセージを送信したパーティにお問い合わせくださいとメッセージに署名するように依頼して、再送信します。 または、オフにすることができます、**メッセージに署名する必要があります**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティ。  
  
2.  場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージに署名する必要があります**、しないように依頼して、メッセージを送信したパーティにお問い合わせくださいプロパティをオフになっても、メッセージの署名メッセージに署名し、再送信します。 選択することができます、**メッセージに署名する必要があります**プロパティ。