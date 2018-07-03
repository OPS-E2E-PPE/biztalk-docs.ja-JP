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
ms.openlocfilehash: 5dfe2b610724a346ed31fb0951aa90c660f41d82
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975939"
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
|  メッセージ テキスト   | 構成エラー。 メッセージの署名が予期された値と一致しません。 送信元パートナーに問い合わせて、使用された署名を確認してください。 AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティの設定で署名が指定されているにもかかわらず、AS2 メッセージが署名されていないか、署名が有効にならないように指定されているのにメッセージが署名されているため、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パーティの設定で署名が指定されている場合は受信 AS2 メッセージが署名されていることを確認します。または、パーティの設定で署名が有効にならないように指定されている場合は、受信 AS2 メッセージが署名されていないことを確認します。 次のいずれかの操作を行います。  
  
1.  場合、**受信メッセージのプロパティをオーバーライド**として、BizTalk Server 管理コンソールでの AS2 のプロパティ ダイアログ ボックスの AS2 メッセージの送信者 ページで、パーティ プロパティが選択されている、**メッセージは署名付きをする必要があります**プロパティが選択されているが、メッセージが署名されていない、メッセージを送信したパーティにお問い合わせくださいとメッセージに署名するように依頼して、再送信します。 または、オフにすることができます、**メッセージに署名する必要があります**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティ。  
  
2.  場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージに署名する必要があります**、しないように依頼して、メッセージを送信したパーティにお問い合わせくださいプロパティをオフになっても、メッセージの署名メッセージに署名し、再送信します。 選択することができます、**メッセージに署名する必要があります**プロパティ。