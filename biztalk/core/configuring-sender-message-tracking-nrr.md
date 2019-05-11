---
title: 送信者メッセージ追跡 (NRR) の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6ca2709-ac4b-48c0-82f8-8a43971a86cb
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c920328b86569a24c510d463f55aaaea6480fbe1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390756"
---
# <a name="configuring-sender-message-tracking-nrr"></a>送信者メッセージ追跡 (NRR) を構成します。
このページの設定の一部として、送信メッセージとその確認 (Mdn) が、否認不可データベースに格納されているかどうかを指定できます。 詳細については、次を参照してください。 [BizTalk Server での AS2 処理](../core/as2-processing-in-biztalk-server.md)します。  
  
 否認不可データベースにメッセージを保存するには、は、パーティが AS2 アグリーメントのプロパティの一部として NRR (受信の否認) を有効にする必要があります。 NRR によって、メッセージの受信者からの署名の確認メッセージを送信者のパーティが確認する必要があること。 概念的には、NRR は変更されずに送信先に到達するメッセージの送信者に否定の証拠です。 元のメッセージと確認メッセージがデジタル署名されている場合にのみ、NRR を確立できます。  
  
> [!IMPORTANT]
>  オフにした場合、このページで、すべてのプロパティが無効に、**ローカルの BizTalk パーティまたはこのパーティからのメッセージの送信をサポートして受信したメッセージを処理する**チェック ボックスを作成するパーティを作成するときに、契約です。  
>   
>  プロパティが無効になるのは、パーティから受信中のインターチェンジのプロパティに対応する一方向のアグリーメント タブ上のみです。 たとえば、2 つのパーティのパーティ A とパーティ B を作成するチェック ボックスをオフにしたパーティ A の場合は、上記のプロパティが無効になります、**パーティ A にパーティ B]-> [** 一方向アグリーメント タブ。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-configure-message-tracking-for-outbound-as2-messages-and-inbound-mdn"></a>送信 AS2 メッセージのメッセージの追跡と受信 MDN を構成するには  
  
1.  AS2 契約の作成」の説明に従って[全般設定の構成 (AS2)](../core/configuring-general-settings-as2.md)します。 既存の AS2 アグリーメントを更新するでアグリーメントを右クリックし、**パーティとビジネス プロファイル**ページ、およびクリックして**プロパティ**します。  
  
2.  一方向アグリーメント タブで、**ローカル ホスト設定**セクションで、**送信者メッセージ追跡 (NRR)** します。  
  
    > [!NOTE]
    >  受信の否認を保証するためには、認証とメッセージの整合性を確立する必要があります。 実行のお勧めの方法は、メッセージのデジタル署名を使用してためです。 その結果、否認不可データベースにメッセージを格納するプロパティのいずれかを選択した場合はメッセージに署名するを選択して、**メッセージに署名する必要があります**プロパティを**検証**ページ。  
  
3.  選択**エンコードされた送信の AS2 メッセージに対して有効な NRR**エンコードされた AS2 メッセージを送信を否認不可データベースに格納します。  
  
4.  選択**送信のデコードされた AS2 メッセージに対して有効な NRR**デコードされた AS2 メッセージを送信を否認不可データベースに格納します。  
  
5.  選択**受信 MDN の NRR の有効化**受信 MDN を否認不可データベースに格納します。  
  
6.  をクリックして**適用**構成では、続行する前に、変更を受け入れるか、をクリックする**OK**変更を検証し、ダイアログ ボックスを閉じます。  
  
## <a name="see-also"></a>参照  
 [ローカル ホスト設定の構成 (AS2)](../core/configuring-local-host-settings-as2.md)