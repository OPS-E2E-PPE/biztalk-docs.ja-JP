---
title: "メッセージの署名に使用される証明書が失効 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f822235a-8ad8-4b63-94de-9b7f9361a071
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8527f89d03d3250a7685380fcabf484254fbbf86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-certificate-used-for-signing-a-message-has-been-revoked"></a>メッセージの署名に使用する証明書が無効にされています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|SigningCertificateHasBeenRevokedError|  
|メッセージ テキスト|メッセージの署名に使用する証明書は失効しています。 証明書の拇印: {0}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、署名証明書として識別された証明書が失効しているため、送信パイプラインで送信メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   失効した証明書を置き換える新しい証明書を作成します。 [現在のユーザー] 証明書ストアに証明書を追加し、その証明書を [グループのプロパティ] ダイアログ ボックスの [証明書] ページで署名証明書として指定し、証明書の公開キーを AS2 メッセージの受信者に送信します。  
  
-   失効リストの確認を無効にします。それには、BizTalk Server 管理コンソールを開き、送信メッセージについて解決されたパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[全般] ノードをクリックし、[証明書失効リストを確認する] プロパティをオフにします。