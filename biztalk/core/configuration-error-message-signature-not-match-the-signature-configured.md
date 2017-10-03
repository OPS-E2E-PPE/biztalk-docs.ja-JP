---
title: "構成エラー。 メッセージの署名は &#39; このパーティ用に構成されたシグネチャと一致する t |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7cea0016-12e8-4ee8-ac44-11024b5e74ef
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23214832300fe6125318ce67083f6bee0a364158
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a>構成エラー。 メッセージの署名は &#39; 一致このパーティ用に構成された署名
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|-|  
|メッセージ テキスト|構成エラー。 メッセージの署名がこのパーティ用に構成された署名と一致しません。 送信元パートナーに問い合わせて、使用された証明書を確認してください。 AS2-から:"{0}"AS2-を:"\ "MessageID:"\ {2 \}"|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、MIME 処理の実行時に AS2 受信パイプラインで署名を検証できなかったことを示します。 この原因として、送信者がメッセージの署名に使用したものとは異なる証明書を使用して、受信したメッセージを処理した可能性があります。 BizTalk Server が間違ったパーティの設定を使用して、受信した AS2 メッセージの署名を検証した可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   受信 AS2 メッセージに対して、パーティ解決プロセスで正しいパーティが特定されるようにします。 そのためには、BizTalk Server が、受信メッセージの AS2-From ヘッダーと、[パーティのプロパティ] ダイアログ ボックスの [全般] ページの [エイリアス] 一覧にある EDIINT-AS2 From の値を照合しようとするときに、正しいパーティが解決されることを確認します。 パーティが解決されない場合は、BizTalk Server が、受信メッセージに対して設定されている AS2-From コンテキスト プロパティと、パーティの名前との一致を見つけようとするときに、正しいパーティが解決されることを確認します。  
  
-   [パーティのプロパティ] ダイアログ ボックスの [証明書] ページに定義されている証明書と、"ローカル コンピューター\その他のユーザー" ストアに格納されている証明書が、メッセージの署名に使用される証明書に対応することを確認します。