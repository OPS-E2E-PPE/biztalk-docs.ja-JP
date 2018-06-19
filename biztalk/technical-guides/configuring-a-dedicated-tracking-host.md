---
title: 専用の追跡ホストの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f997bcc2-08fd-4e9a-ba44-542ec8460d6d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b91a4b65c6e9a9b293e967385b8f0ac4eece1aa4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010843"
---
# <a name="configuring-a-dedicated-tracking-host"></a>専用の追跡ホストの構成
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]最適化されているため、スループット、メインのオーケストレーションとメッセージング エンジン実際には移動しないでイベントやメッセージ、BizTalk 追跡 (DTA) またはビジネス アクティビティ監視 (BAM) データベースに直接ので、これは、プライマリからこれらのエンジンを迂回させますビジネス プロセスを実行中のジョブです。 代わりに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]イベントとメッセージがメッセージ ボックス データベースになり、BizTalk 追跡データベースまたは BAM データベースへの移行を必須としてマークを付けます。 バック グラウンド プロセス (追跡ホスト) してから、BizTalk 追跡データベースに SQL Server エージェント ジョブ コピー追跡したメッセージの中に、BizTalk の追跡と BAM データベースに移動するイベント。  
  
## <a name="advantages-of-using-a-dedicated-tracking-host"></a>専用の追跡ホストを使用する利点  
 追跡をホストする BizTalk ホストとは、DTA と BAM 追跡データをメッセージ ボックス データベースから、BizTalk 追跡 (DTA) データベースおよび BAM プライマリ インポート データベースへの移動を担当します。 この移動の追跡データは、追跡をホストしている同じホストで実行されているその他の BizTalk アイテムのパフォーマンスに影響を及ぼします。 したがって、ホストの追跡が何も実行しない専用のホストを使用する必要があります。  
  
 専用の追跡ホストを使用することもできますを妨げることがなく他の BizTalk ホストを停止する[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡します。 追跡メッセージ ボックス データベースからデータの移動は重大で正常な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システムです。 BizTalk グループ内の追跡データの移動を担当する BizTalk ホストを停止すると、データのデコードに追跡サービスは実行されません。 この効果は次のとおりです。  
  
-   HAT 追跡データは、BizTalk 追跡データベースにメッセージ ボックス データベースから移動されません。  
  
-   BAM の追跡データは、BAM プライマリ インポート データベースにメッセージ ボックス データベースから移動されません。  
  
-   データが移動されていないために、メッセージ ボックス データベースから削除できません。  
  
-   場合データのデコードに追跡サービスを停止すると、追跡インターセプターは引き続き実行され、メッセージ ボックス データベースに追跡データを書き込みます。 データが移動されていない場合は、メッセージ ボックス データベースになります肥大化、時間の経過と共にパフォーマンスが低下する可能性がなります。 場合でも、カスタム プロパティは追跡されませんまたは BAM プロファイルが設定されていない、既定では一部のデータは、追跡 (など、パイプラインは、受信/送信イベントおよびオーケストレーションのイベント)。 データのデコードに追跡サービスを実行しないようにする場合は、すべての追跡インターセプターをデータベースにデータ保存しないようにオフにします。 グローバル追跡を無効にするを参照してください。[グローバル追跡を無効にする方法](http://go.microsoft.com/fwlink/?LinkId=154193)(http://go.microsoft.com/fwlink/?LinkId=154193) を使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールを選択的に追跡イベントを無効にします。  
  
## <a name="optimizing-performance-for-a-dedicated-tracking-host"></a>専用の追跡ホストのパフォーマンスを最適化します。  
 このホストを実行するには、少なくとも 2 つのコンピューターで実行する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](の場合に備えた冗長性のいずれかに失敗する)。 最適なパフォーマンスが必要には、少なくとも 1 つの追跡メッセージ ボックス データベースごとにホストのインスタンス。 追跡ホスト インスタンスの実際の数が n+1、する必要があります、N、メッセージ ボックス データベースの数を = です。 「+ 1」は、冗長性のためです。 1 つだけの追跡は、インスタンスをホストするための追加よりも多くのメリットが特定のメッセージ ボックス データベースのデータを移動されません。 その結果、ロックする必要がありますしない問題。 追加の 1 つのフォールト トレランス追加ホスト インスタンスの追跡ホストする場合は、追跡のいずれかのインスタンスが失敗する、追加のインスタンスは、失敗したインスタンスの職務と仮定します。  
  
 追跡ホスト インスタンスが特定のメッセージ ボックス データベースの追跡データを移動しますが、されません 1 つ以上の追跡ホスト インスタンスの特定のメッセージ ボックス データベースのデータを移動します。 たとえば、3 つのメッセージ ボックス データベースと 2 つのホスト インスタンスの追跡がある場合は、そのホスト インスタンスのいずれかの必要があります、メッセージ ボックス データベースの 2 つのデータを移動します。 追跡ホスト インスタンスの追跡、3 番目の追加は分散作業を実行している別のコンピューターのホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。 このシナリオでは、複数の追跡ホストの配布と 4 つ目のホスト インスタンスの追跡を追加する機能しますが、余分なは、フォールト トレランスのホスト インスタンスを追跡します。  
  
 BAM イベント バス サービスの詳細については、BizTalk Server ヘルプの次のトピックを参照してください。  
  
-   [BAM イベント バス サービスを管理する](http://go.microsoft.com/fwlink/?LinkId=154194)(http://go.microsoft.com/fwlink/?LinkId=154194)  
  
-   [BAM イベント バス サービスのインスタンスを作成する](http://go.microsoft.com/fwlink/?LinkId=154195)(http://go.microsoft.com/fwlink/?LinkId=154195)  
  
## <a name="configuring-a-dedicated-tracking-host"></a>専用の追跡ホストの構成  
 このセクションで、手順を実行するには、ホストの追跡を許可するホストのプロパティを変更するための次のユーザー権利があります。  
  
-   メンバーである必要がある必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
-   SQL Server には次の権利が必要です。  
  
    -   SQL Server の管理者またはのメンバーのいずれかにする必要があります、 *db_owner*または*db_securityadmin* BizTalk 追跡データベース (BizTalk DTADb)、メッセージ ボックス データベース (SQL Server データベース ロールBizTalkMsgBoxDb)、および BAM プライマリ インポート データベース (BAMPrimaryImport)。  
  
    -   メッセージ ボックス データベース、またはのメンバーのすべてのコンピューター上の sysadmin SQL Server ロールのメンバーがあります、 *db_owner*または*db_ddladmin*すべてのメッセージ ボックス データベースの SQL Server ロール。  
  
#### <a name="to-enable-host-tracking"></a>ホストの追跡を有効にするには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**[BizTalk グループ]、をクリックして**プラットフォームの設定**、クリックして**ホスト**です。  
  
3.  詳細ウィンドウで、変更、およびをクリックするホストを右クリックして**プロパティ**です。  
  
4.  **ホストのプロパティ**ダイアログ ボックスの**全般** タブ、オンまたはオフ**オプション-ホストの追跡を許可する**、順にクリック**ok**です。  
  
     ホストで BizTalk の追跡コンポーネントを読み込んで、状態監視データおよびビジネス データを処理する場合は、このチェック ボックスをオンにします。 このチェック ボックスをオンにすると、メッセージ ボックス データベースの追跡テーブルおよび追跡データベースに対する読み取り/書き込みアクセスが現在のホストに許可されます。 これに伴い、このホスト内で実行されるオブジェクトにも、これらのデータベースに対する読み取りと書き込みのアクセス許可が与えられます。  
  
     チェック ボックスをオフにした場合、ホストはメッセージ ボックス データベースに追跡テーブルへの書き込みアクセスのみを持つし、追跡データベースへのアクセス権がないです。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)