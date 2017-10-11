---
title: "構成エラー。 メッセージの署名ではありません &#39; t が期待値と一致します。 | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1f067351-b6b0-479d-b2ff-81e9f45b5924
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa0bacd605908abae984247b3d7ed775ea8f5de4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-the-message-signing-doesn39t-match-the-expected-value"></a>構成エラー。 メッセージの署名ではありません &#39; t が期待値と一致します。
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|AS2DecoderPartySigningConfigurationError|  
|メッセージ テキスト|構成エラー。 メッセージの署名が予期された値と一致しません。 送信元パートナーに問い合わせて、使用された署名を確認してください。 AS2-から:"{0}"AS2-を:"\ "MessageID:"\ {2 \}"|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、パーティの設定で署名が指定されているにもかかわらず、AS2 メッセージが署名されていないか、署名が有効にならないように指定されているのにメッセージが署名されているため、受信パイプラインの AS2 デコーダー コンポーネントが AS2 メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、パーティの設定で署名が指定されている場合は受信 AS2 メッセージが署名されていることを確認します。または、パーティの設定で署名が有効にならないように指定されている場合は、受信 AS2 メッセージが署名されていないことを確認します。 次のいずれかの操作を行います。  
  
1.  場合、**受信メッセージのプロパティをオーバーライド**の [パーティ-AS2 メッセージの送信者] ページで AS2 のプロパティ ダイアログ ボックスのプロパティが選択されて、[!INCLUDE[prague](../includes/prague-md.md)]管理コンソールで、**メッセージは署名付きをする必要があります**プロパティが選択されているが、メッセージが署名されていない、メッセージを送信したパーティに連絡し、メッセージに署名するように依頼して、再送信します。 クリアするか、**メッセージに署名する必要があります**プロパティ、または**受信メッセージのプロパティをオーバーライド**プロパティです。  
  
2.  場合、**受信メッセージのプロパティをオーバーライド**プロパティが選択されている、**メッセージに署名する必要があります**プロパティをオフにしたが、メッセージが署名されているメッセージを送信したパーティに連絡、しないように依頼してくださいメッセージに署名し、再送信します。 選択することができます、**メッセージに署名する必要があります**プロパティです。