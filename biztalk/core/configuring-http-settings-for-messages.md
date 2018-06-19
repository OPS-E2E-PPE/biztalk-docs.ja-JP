---
title: メッセージの HTTP 設定の構成 |Microsoft ドキュメント
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
ms.openlocfilehash: d15ebb5ff5be6678c4dc2aee3f9333f36c75c89f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233090"
---
# <a name="configuring-http-settings-for-messages"></a>メッセージの HTTP 設定を構成します。
メッセージ関連の HTTP 設定の一部として、AS2 メッセージを受信する Web サーバーが予期するプロパティを指定できます。  
  
> [!IMPORTANT]
>  プロパティが無効**パーティ A にパーティ B->** をオフにした場合は、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する** チェック ボックスパーティ A の同じ ページで、ただし、すべてのプロパティが無効にします**パーティ B には、パーティ A が->**   タブの A の作成中に、チェック ボックスを選択した場合  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-message-related-http-settings"></a>メッセージ関連の HTTP 設定を構成するには  
  
1.  AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**ローカル ホストの設定**セクションで、**メッセージの HTTP 設定**です。  
  
3.  選択、**を無視する SSL 証明書名の不一致**サーバー名が SSL 証明書の生成対象サーバー名が一致しない場合、SSL 接続があることを確認する チェック ボックスが受け入れられます。  
  
4.  をクリックして**HTTP expect 100 continue** HTTP Expect ヘッダーを 100 に設定する-続行すると、ポストされたデータを最初の HTTP 要求が、サーバー コンテンツを要求するまで待機に含まれないことを指定します。  
  
5.  をクリックして**保持の HTTP 接続をアライブ**こと、HTTP 接続維持される要求と応答のサイクルが完了した後に要求します。  
  
6.  をクリックして**を展開する HTTP ヘッダー** HTTP content-type ヘッダーを 1 行に展開する場合。  
  
7.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)