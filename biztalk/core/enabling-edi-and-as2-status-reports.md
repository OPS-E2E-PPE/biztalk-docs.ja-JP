---
title: "EDI および AS2 状態レポートの有効化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa40fbad-51ad-40e0-9fe3-68e54beb11a5
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cef3d25040c253badd0f517326cc7830b6962df8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="enabling-edi-and-as2-status-reports"></a>EDI および AS2 状態レポートの有効化
このトピックでの EDI および AS2 状態レポートを構成する方法を説明する、**グループの概要**のページ、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
 状態レポート追跡データは、以下の手順で選択するストレージのプロパティに従って、BizTalk 追跡データベース (BizTalkDTADb) に格納されます。 各アグリーメントの状態レポート機能を有効にするように [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を構成できます。 格納するデータ量に応じて、アクティブなストアからデータを定期的にアーカイブし、その後にアーカイブ ストアから適宜消去する必要があります。 BizTalkDTADb データベースの管理の詳細については、次を参照してください。[アーカイブ化および BizTalk 追跡データベースを削除](../core/archiving-and-purging-the-biztalk-tracking-database.md)です。  
  
 状態レポートは次の 3 種類の方法で有効にできます。  
  
-   アグリーメントに解決される受信 EDI インターチェンジまたは送信 EDI インターチェンジに対して状態レポート機能を有効にする  
  
-   インターチェンジの EDI 状態レポートがアクティブ化されて EDI フォールバック アグリーメント プロパティの状態レポートを有効にして[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のアグリーメントを特定できませんでした。  
  
-   AS2 メッセージの状態レポート機能を有効にする  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループまたは BizTalk Server B2B Operators グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-enable-edi-status-reports-for-an-agreement"></a>アグリーメントの EDI 状態レポート機能を有効にするには  
  
1.   **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理**コンソールで、をクリックして、**パーティ**ノードの下、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]と**BizTalk グループ**ノード。  
  
2.  **パーティとビジネス プロファイル** ウィンドウで、状態レポートを有効にする X12 または EDIFACT アグリーメントを含むパーティをクリックします。  
  
3.  **契約**セクションで、状態レポートを有効にし、をクリックするアグリーメントを右クリックして**プロパティ**です。  
  
4.  **全般**] タブで、**共通のホスト設定**セクションで、[**レポートをオンに**です。  
  
    > [!NOTE]
    >  これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの状態レポートの UI にメッセージ エントリが入力されるようになります。  
  
5.  選択**レポート用にトランザクション セット/ペイロードを格納**トランザクションを格納する、追跡 (BizTalkDTADb) データベースの EDI テーブルに設定します。  
  
    > [!NOTE]
    >  バッチ処理オーケストレーションのインスタンスがアクティブなときにトランザクション セットのストレージを有効にした場合は、作成中のバッチについてのトランザクション セットが格納されません。 ただし、バッチ処理オーケストレーションのインスタンスがアクティブなときにトランザクション セットのストレージを無効にした場合は、ストレージがバッチ処理の途中で無効になります。  
  
6.  **[OK]**をクリックします。  
  
7.  [コンピューターの管理] ダイアログ ボックスで BizTalk サービスを再起動します。 AS2EdiReceive パイプラインまたは AS2EdiSend パイプラインは、ソリューションで使用されているが場合、IIS Admin サービスを再起動 (を使用して、 *iisreset*コマンド)、およびです。  
  
    > [!NOTE]
    >  EDI 状態レポートをアクティブ化または非アクティブ化した後は、変更を有効にするために、BizTalk サービスを再起動する必要があります。 ソリューションで AS2EdiReceive パイプラインまたは AS2EdiSend パイプラインを使用している場合は、変更を有効にするために、BizTalk サービスと IIS サービスの両方を再起動する必要があります。 AS2 状態レポート機能を有効にする場合は、この操作は不要です。  
  
### <a name="to-enable-edi-status-reports-for-fallback-agreements"></a>フォールバック アグリーメントの EDI 状態レポート機能を有効にするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、ノードを右クリックして**パーティ**を選択し、 **X12 フォールバック設定**または**EDIFACT フォールバックの設定**です。  
  
    > [!NOTE]
    >  フォールバック アグリーメントで状態レポートを構成する場合は、メッセージのアグリーメントが特定されていないときにのみ、構成が適用されます。  
  
2.  **フォールバック設定の全般ページ** タブで、をクリックして**EDI のアクティブ化レポート**です。  
  
    > [!NOTE]
    >  これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの状態レポートの UI にメッセージ エントリが入力されるようになります。  
  
3.  選択**レポート用にトランザクション セット/ペイロードを格納**トランザクションを格納する、追跡 (BizTalkDTADb) データベースの EDI テーブルに設定します。  
  
    > [!NOTE]
    >  **EDIFACT でエンコードされたメッセージ**: EDI グローバル プロパティ ダイアログ ボックスの UNB セグメントの定義 ページで unb3.2 フィールド (コード修飾子) の値を選択する場合、このプロパティを選択するもする必要があります。 既定では、このプロパティが設定されていないと場合、インターチェンジは中断されます**レポート用にトランザクション セット/ペイロードを格納**が選択されているが、UNB3.2 の値が選択されていません。  
  
4.  **[OK]**をクリックします。  
  
### <a name="to-enable-as2-status-reports"></a>AS2 状態レポート機能を有効にするには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]と**BizTalk グループ**、ノードをクリックして、**パーティ**ノード。  
  
2.  **パーティとビジネス プロファイル** ウィンドウで、状態レポートを有効にする X12 または EDIFACT アグリーメントを含むパーティをクリックします。  
  
3.  **契約**セクションで、状態レポートを有効にし、をクリックするアグリーメントを右クリックして**プロパティ**です。  
  
4.  **共通のホスト設定**セクションで、**レポートをオンに**です。  
  
    > [!NOTE]
    >  これにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの状態レポートの UI にメッセージ エントリが入力されるようになります。  
  
5.  一方向アグリーメント タブで、**アグリーメントのプロパティ** ダイアログ ボックスをクリックして、**受信者メッセージの追跡 (NRR)**ページ。  
  
6.  **受信者メッセージの追跡 (NRR)**  ページで、をクリックして**受信のエンコードされた AS2 メッセージの有効な NRR**受信メッセージのワイヤ形式の表示を有効にします。  
  
    > [!NOTE]
    >  AS2 メッセージおよび関連 MDN の状態 ページでメッセージを右クリックし、をクリックすると、ワイヤ形式のメッセージが表示されます**メッセージのワイヤ形式**です。  
  
    > [!NOTE]
    >  **レポートをオンに**否認不可データベース内のデータの格納を有効にするためのプロパティを選択する必要があります。 このプロパティまたは否認不可データベースへの格納を有効にする他のプロパティを選択した場合は、AS2 レポートをアクティブにするように通知するポップアップが表示されます。 クリックすると**はい**、AS2 レポートをするに対してアクティブ化されます。  
  
7.  **受信者メッセージの追跡 (NRR)**  ページで、をクリックして**受信のデコードされた AS2 メッセージの有効な NRR**受信メッセージのデコードされた形式の表示を有効にします。  
  
8.  **受信者メッセージの追跡 (NRR)** ] ページで [**送信 MDN の NRR の有効化**受信メッセージへの MDN 応答を表示できるようにします。  
  
9. 一方向アグリーメント タブで、**アグリーメントのプロパティ** ダイアログ ボックスをクリックして、**送信者メッセージ追跡 (NRR)**ページ。  
  
10. **送信者メッセージ追跡 (NRR)**  ページで、をクリックして**エンコードされた送信の AS2 メッセージに対して有効な NRR**送信メッセージのワイヤ形式の表示を有効にします。  
  
11. **送信者メッセージ追跡 (NRR)**  ページで、をクリックして**送信のデコードされた AS2 メッセージに対して有効な NRR**送信メッセージのデコードされた形式の表示を有効にします。  
  
12. **送信者メッセージ追跡 (NRR)** ] ページで [**受信 MDN の NRR の有効化**送信メッセージへの MDN 応答を表示できるようにします。  
  
13. **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [EDI および AS2 ソリューションの監視](../core/monitoring-edi-and-as2-solutions.md)   
 [EDI および AS2 状態レポートの構成](../core/configuring-an-edi-and-as2-status-report.md)   
 [EDI および AS2 状態レポート](../core/edi-and-as2-status-reporting.md)   