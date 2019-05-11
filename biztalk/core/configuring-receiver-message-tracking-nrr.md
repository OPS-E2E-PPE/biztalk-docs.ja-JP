---
title: 受信者メッセージの追跡 (NRR) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce30737a-341b-45be-81a0-a7336219185e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05b57c9b032fb557c23e7ec11a6e6f60fd6692b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355285"
---
# <a name="configuring-receiver-message-tracking-nrr"></a>受信者メッセージの追跡 (NRR) を構成します。
このページの設定の一部として、受信メッセージとその確認 (Mdn) が、否認不可データベースに格納されているかどうかを指定できます。 詳細については、次を参照してください。 [BizTalk Server での AS2 処理](../core/as2-processing-in-biztalk-server.md)します。  
  
 否認不可データベースにメッセージを保存するには、は、パーティが AS2 アグリーメントのプロパティの一部として NRR (受信の否認) を有効にする必要があります。 NRR によって、メッセージの受信者からの署名の確認メッセージを送信者のパーティが確認する必要があること。 概念的には、NRR は変更されずに送信先に到達するメッセージの送信者に否定の証拠です。 元のメッセージと確認メッセージがデジタル署名されている場合にのみ、NRR を確立できます。  
  
> [!IMPORTANT]
>  プロパティが無効になりません**パーティ A にパーティ B-> **オフにした場合、一方向アグリーメント タブの**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する** チェック ボックスパーティ A の同じページで、ただし、すべてのプロパティが無効に、**パーティ B には、パーティ A が-> ** A を作成するときに、チェック ボックスを選択した場合のタブ  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-message-tracking-for-inbound-as2-messages-and-outbound-mdn"></a>受信 AS2 メッセージおよび送信 MDN に対してメッセージの追跡を構成するには  
  
1.  AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**ローカル ホスト設定**セクションで、**受信者メッセージ追跡 (NRR)** します。  
  
    > [!NOTE]
    >  受信の否認を保証するためには、認証とメッセージの整合性を確立する必要があります。 実行のお勧めの方法は、メッセージのデジタル署名を使用してためです。 その結果、否認不可データベースにメッセージを格納するプロパティのいずれかを選択した場合はメッセージに署名するを選択して、**メッセージに署名する必要があります**プロパティを**検証**ページ。  
  
3.  選択**受信のエンコードされた AS2 メッセージに対して有効な NRR**エンコードされた AS2 メッセージを送信を否認不可データベースに格納します。  
  
4.  選択**受信のデコードされた AS2 メッセージに対して有効な NRR**デコードされた AS2 メッセージを送信を否認不可データベースに格納します。  
  
5.  選択**送信 MDN の NRR の有効化**受信 MDN を否認不可データベースに格納します。  
  
6.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)