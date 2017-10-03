---
title: "送信者メッセージ追跡 (NRR) の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e6ca2709-ac4b-48c0-82f8-8a43971a86cb
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1785a5502bc1adb9cc8b9aa7f85b6a4473d21c5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-sender-message-tracking-nrr"></a>送信者メッセージ追跡の構成 (NRR)
このページでの設定の一部として、送信メッセージとそれらの確認 (MDN) を否認不可データベースに保存するかどうかを指定できます。 詳細については、次を参照してください。 [BizTalk Server での AS2 処理](../core/as2-processing-in-biztalk-server.md)です。  
  
 否認不可データベースにメッセージを保存するには、AS2 アグリーメント プロパティの一部として NRR (Non-repudiation of receipt) を有効にする必要があります。 NRR によって、送信側パーティは、メッセージ受信者からの署名付きの確認メッセージを検証できます。 概念上、NRR は、メッセージ送信者にとって、メッセージが変更されずに送信先に到達したことを示す確実な証拠です。 NRR を確立できるのは、元のメッセージと確認メッセージが電子署名されている場合のみです。  
  
> [!IMPORTANT]
>  オフにした場合のこのページですべてのプロパティは無効、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信メッセージを処理する**チェック ボックスを作成するパーティを作成するときに、アグリーメント。  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成して、チェック ボックスをオフにしたパーティ A、に対して、上記のプロパティの無効になりますで、**パーティ A にパーティ B]-> [**一方向アグリーメント タブです。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-message-tracking-for-outbound-as2-messages-and-inbound-mdn"></a>送信 AS2 メッセージと受信 MDN のメッセージ追跡を設定するには  
  
1.  AS2 アグリーメントを作成する」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)です。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル** ページで、をクリックして**プロパティ**です。  
  
2.  一方向アグリーメント タブの下にある**ローカル ホストの設定**セクションで、**送信者メッセージ追跡 (NRR)**です。  
  
    > [!NOTE]
    >  受信の否認不可を確実に行うには、メッセージの認証と整合性を保証する必要があります。 メッセージのデジタル署名を使用して認証と整合性を確立することをお勧めします。 結果として、否認不可データベースにメッセージを格納するプロパティのいずれかを選択した場合はメッセージに署名する を選択して、**メッセージに署名する必要があります**プロパティを**検証**ページ。  
  
3.  選択**エンコードされた送信の AS2 メッセージに対して有効な NRR**にエンコードされた送信の AS2 メッセージを否認不可データベースに格納します。  
  
4.  選択**送信のデコードされた AS2 メッセージに対して有効な NRR**送信のデコードされた AS2 メッセージを否認不可データベースに格納します。  
  
5.  選択**受信 MDN の NRR の有効化**受信 MDN を否認不可データベースに格納します。  
  
6.  をクリックして**適用**構成を続行する前に、変更を受け入れるか、をクリックする**OK**を変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)