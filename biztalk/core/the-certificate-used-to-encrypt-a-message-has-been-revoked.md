---
title: メッセージの暗号化に使用する証明書が失効 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c90690-002a-43bc-85f2-8aa5e7511ffa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fbe34dcd2906d79a8d80ebdd00c3d9f293e6559
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279610"
---
# <a name="the-certificate-used-to-encrypt-a-message-has-been-revoked"></a>メッセージの暗号化に使用する証明書は失効しています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|EncryptionCertificateHasBeenRevokedError|  
|メッセージ テキスト|メッセージの暗号化に使用する証明書は失効しています。 証明書の拇印: {0}|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、暗号化証明書として識別された証明書が失効しているため、送信パイプラインで送信メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
-   メッセージの受信者に対して、新しい証明書を作成し、公開キーを送信するように依頼します。 "ローカル コンピューター\その他のユーザー" 証明書ストアに証明書を追加し、[送信ポートのプロパティ] ダイアログ ボックスの [証明書] ページで、暗号化証明書としてその証明書を識別します。  
  
-   失効リストの確認を無効にします。それには、BizTalk Server 管理コンソールを開き、送信メッセージについて解決されたパーティの [AS2 のプロパティ] ダイアログ ボックスを開きます。次に、[全般] ノードをクリックし、[証明書失効リストを確認する] プロパティをオフにします。