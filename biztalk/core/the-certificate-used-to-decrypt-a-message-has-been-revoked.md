---
title: メッセージの解読に使用する証明書が失効 |Microsoft ドキュメント
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
ms.openlocfilehash: 7cd9404f13f737b4cb82317193344e006979d333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277914"
---
# <a name="the-certificate-used-to-decrypt-a-message-has-been-revoked"></a>メッセージの解読に使用する証明書は失効しています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|DecryptionCertificateHasBeenRevokedError|  
|メッセージ テキスト|メッセージの解読に使用する証明書は失効しています。 証明書の拇印: {0}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、メッセージの暗号化解除に使用する証明書が失効しているため、受信パイプラインで受信メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   失効した証明書を置換する新しい証明書を作成します。 作成した証明書を "現在のユーザー/個人用" 証明書ストアに追加し、証明書の公開キーを AS2 メッセージの送信元に送信します。  
  
-   失効リストの確認を無効にします。それには、BizTalk Server 管理コンソールを開き、送信メッセージについて解決されたパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[全般] ノードをクリックし、[証明書失効リストを確認する] プロパティをオフにします。