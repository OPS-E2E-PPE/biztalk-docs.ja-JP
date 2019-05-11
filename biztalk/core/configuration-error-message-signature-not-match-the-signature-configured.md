---
title: 構成エラー。 メッセージの署名は&#39;このパーティ用に構成された署名が一致しない |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7cea0016-12e8-4ee8-ac44-11024b5e74ef
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b78dc27ff21787c6b57e65a2cadb7564e080c1a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391557"
---
# <a name="configuration-error-the-message-signature-doesn39t-match-the-signature-configured-for-this-party"></a>構成エラー。 メッセージの署名は&#39;このパーティ用に構成された署名が一致しません。
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                             |
| 製品バージョン |                                                                         [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                                         |
|    イベント ID     |                                                                                                     -                                                                                                      |
|  イベント ソース   |                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                                                           |
|    コンポーネント    |                                                                                                 AS2 エンジン                                                                                                 |
|  シンボル名  |                                                                                                     -                                                                                                      |
|  メッセージ テキスト   | 構成エラー。 メッセージの署名は、このパーティ用に構成された署名と一致しません。 送信元パートナーに連絡し、使用する証明書を確認します。 AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 の受信を示す MIME 処理を実行するときに、パイプラインは、署名を確認できませんでした。 別の証明書を使用してメッセージに署名するために使用する送信者よりも、受信したメッセージを処理する可能性があります。 これは、BizTalk Server では、間違ったパーティの設定を使用して、受信 AS2 メッセージの署名を検証する場合に発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   受信 AS2 メッセージのパーティの解決プロセスで正しいパーティが決定されることを確認します。 BizTalk Server が AS2 の間の一致を検索しようとしたときに、正しいパーティが解決されるかを確認し、そのため、ヘッダー、着信メッセージとパーティのプロパティ ダイアログ ボックスの 全般 ページの エイリアス 一覧の ediint-as2 From の値。 パーティが解決しない場合は、BizTalk Server が AS2 の間の一致を検索しようとしたときに、正しいパーティが解決されることを確認の受信メッセージとパーティの名前に設定されているコンテキスト プロパティから。  
  
-   パーティのプロパティ ダイアログ ボックスの 証明書 ページで定義され、Local computer \other People ストアに格納されている証明書は、メッセージの署名に使用する証明書に対応していることを確認します。