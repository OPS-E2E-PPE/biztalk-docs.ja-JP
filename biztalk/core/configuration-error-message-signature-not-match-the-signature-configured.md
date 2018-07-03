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
ms.openlocfilehash: 729fff283d8fa63ce9e933a0dc69a4a8f2200874
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980459"
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
|  メッセージ テキスト   | 構成エラー。 メッセージの署名がこのパーティ用に構成された署名と一致しません。 送信元パートナーに問い合わせて、使用された証明書を確認してください。 AS2-から:"{0}"AS2-を:"{1}"MessageID:"{2}" |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、MIME 処理の実行時に AS2 受信パイプラインで署名を検証できなかったことを示します。 この原因として、送信者がメッセージの署名に使用したものとは異なる証明書を使用して、受信したメッセージを処理した可能性があります。 BizTalk Server が間違ったパーティの設定を使用して、受信した AS2 メッセージの署名を検証した可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   受信 AS2 メッセージに対して、パーティ解決プロセスで正しいパーティが特定されるようにします。 そのためには、BizTalk Server が、受信メッセージの AS2-From ヘッダーと、[パーティのプロパティ] ダイアログ ボックスの [全般] ページの [エイリアス] 一覧にある EDIINT-AS2 From の値を照合しようとするときに、正しいパーティが解決されることを確認します。 パーティが解決されない場合は、BizTalk Server が、受信メッセージに対して設定されている AS2-From コンテキスト プロパティと、パーティの名前との一致を見つけようとするときに、正しいパーティが解決されることを確認します。  
  
-   [パーティのプロパティ] ダイアログ ボックスの [証明書] ページに定義されている証明書と、"ローカル コンピューター\その他のユーザー" ストアに格納されている証明書が、メッセージの署名に使用される証明書に対応することを確認します。