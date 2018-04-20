---
title: AS2 メッセージを検証するときにエラーが発生しました |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0cf97c63-2bff-4474-9cd8-f68634493dcc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73f1c9b7cf4e444e256aadc3ade717fcf30735bd
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="an-error-occurred-when-validating-an-as2-message"></a>AS2 メッセージの検証中にエラーが発生しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|-|  
|メッセージ テキスト|AS2 メッセージの検証中にエラーが発生しました。 使用した証明書の有効期限が切れていないこと、および失効していないことを確認してください。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 受信パイプラインまたは AS2 送信パイプラインで AS2 メッセージを検証できなかったことを示します。 これは、署名の確認プロセスで使用された証明書が有効でないか、適切な場所に格納されていないか、署名プロセスで使用された証明書と一致しない場合に発生することがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  
  
-   AS2 メッセージの署名ラッパーが有効であることを確認します。 有効でない場合は、メッセージがエンコーダーによって適切に署名されていない理由を確認します。  
  
-   署名プロセスで使用される秘密キーと、署名の確認プロセスで使用される公開キーが一致しているかどうかを確認します。  
  
-   署名および署名の確認に使用される証明書の "キー使用法" プロパティが "データの暗号化" に設定されていることを確認します。  
  
-   中間証明機関のチェーンが切れていないことを確認します。 切れている場合は、古い証明書を削除し、新しい証明書を作成して使用します。  
  
-   証明書の有効期限を証明書ストアで調べて (証明書スナップインを含む MMC を使用)、証明書の有効期限が切れていないことを確認します。  
  
-   証明書失効リストを調べて、証明書が失効していないことを確認します。 (BizTalk Server が、証明書失効リストのチェック、AS2 の全般プロパティでプロパティを確認してこれを自動的に確認を持つことができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです)。  
  
-   署名の確認に使用される証明書が、ホスト インスタンス サービス アカウントごとに MIME/SMIME デコーダー パイプラインをホストする各 BizTalk サーバーの [ローカル コンピューター/その他のユーザー] ストアに格納されていることを確認します。