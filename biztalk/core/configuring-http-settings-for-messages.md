---
title: メッセージの HTTP 設定の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ed400f1-561d-4812-adf1-20e4300fd048
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a5e216ec76fa4ccbf6255d802f337c9c0ac47ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391045"
---
# <a name="configuring-http-settings-for-messages"></a>メッセージの HTTP 設定を構成します。
メッセージ関連の HTTP 設定の一部として、AS2 メッセージを受信する Web サーバーで予期されるプロパティを指定できます。  
  
> [!IMPORTANT]
>  プロパティが無効になりません**パーティ A にパーティ B->** オフにした場合、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する** チェック ボックスパーティ A の同じページで、ただし、すべてのプロパティが無効に、**パーティ B には、パーティ A が->**  A を作成するときに、チェック ボックスを選択した場合のタブ  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-message-related-http-settings"></a>メッセージ関連の HTTP 設定を構成するには  
  
1.  AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**ローカル ホスト設定**セクションで、**メッセージの HTTP 設定**します。  
  
3.  選択、**を無視する SSL 証明書名の不一致**サーバー名が SSL 証明書が生成されたサーバー名が一致しない場合、SSL 接続は引き続きことを確認する チェック ボックスが受け入れられます。  
  
4.  クリックして**HTTP expect: 100-continue** HTTP Expect ヘッダーを 100 に設定する-続行すると、ポストされたデータは、最初の HTTP 要求がコンテンツを要求するサーバーの間、待機に含まれないことを指定します。  
  
5.  クリックして**保持の HTTP 接続をアライブ**要求と応答のサイクルが完了した後、HTTP 接続がアライブする保持を要求します。  
  
6.  クリックして**HTTP のヘッダー**を 1 行に、HTTP content-type ヘッダーをオンにします。  
  
7.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)