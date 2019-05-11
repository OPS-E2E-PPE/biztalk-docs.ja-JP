---
title: メッセージの解読に使用する証明書が失効しています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01767cb2-b16e-4b4b-ac4d-cd79b6c8860a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8302b4893b6014a260ce5f26e96138f7093bbf0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298853"
---
# <a name="the-certificate-used-to-decrypt-a-message-has-been-revoked"></a>メッセージの解読に使用する証明書が失効しています
## <a name="details"></a>詳細  
  
|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    イベント ID     |                                            -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI  |
|    コンポーネント    |                                       AS2 エンジン                                        |
|  シンボル名  |                        DecryptionCertificateHasBeenRevokedError                         |
|  メッセージ テキスト   | メッセージの解読に使用する証明書が失効しています。 証明書の拇印: {0} |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージの解読に使用される証明書が失効しているためにで、受信メッセージが受信パイプラインでした処理することを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   失効した証明書を置換する新しい証明書を作成します。 現在のユーザー/個人用証明書ストアに証明書を追加し、AS2 メッセージを送信する証明書の公開キーを送信します。  
  
-   失効リストの確認を無効にします。それには、BizTalk Server 管理コンソールを開き、送信メッセージについて解決されたパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[全般] ノードをクリックし、[証明書失効リストを確認する] プロパティをオフにします。