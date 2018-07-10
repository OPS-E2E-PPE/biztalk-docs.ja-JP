---
title: 専用の追跡ホストの構成 |Microsoft Docs
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
ms.openlocfilehash: defed64020300ebe6843e8e06bb15a51af2c4ec3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986715"
---
# <a name="configuring-a-dedicated-tracking-host"></a>専用の追跡ホストの構成
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] メインのオーケストレーションとメッセージング エンジンは実際に移動イベントまたはメッセージ、BizTalk 追跡 (DTA) またはビジネス アクティビティ監視 (BAM) データベースに直接がプライマリからこれらのエンジンをそらすはこのため、スループットを最適化します。ビジネス プロセスを実行するジョブ。 代わりに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ ボックス データベース内のイベントとメッセージのままにし、BizTalk 追跡または BAM データベースへの移行を必要とするとしてマークを付けます。 バック グラウンド プロセス (追跡ホスト) し、BizTalk 追跡データベースに SQL Server エージェント ジョブのコピー追跡したメッセージの中に、BizTalk の追跡と BAM データベースにイベントを移動します。  
  
## <a name="advantages-of-using-a-dedicated-tracking-host"></a>専用の追跡ホストを使用する利点  
 追跡をホストする BizTalk ホストは、DTA と BAM 追跡データをメッセージ ボックス データベースから BizTalk 追跡 (DTA) と BAM プライマリ インポート データベースへの移動を担当します。 この移動の追跡データは、追跡をホストしている同じホストで実行されている他の BizTalk アイテムのパフォーマンスに影響を与えます。 したがって、何も行いませんが、ホストの追跡専用のホストを使用する必要があります。  
  
 妨げることがなく他の BizTalk ホストを停止することもできます専用の追跡ホストを使用して[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡します。 追跡メッセージ ボックス データベースからデータの移動が正常性の重要な[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]システム。 BizTalk グループ内の追跡データの移動を行う BizTalk ホストが停止している場合、データのデコードに追跡サービスは実行されません。 この効果は次のとおりです。  
  
- HAT 追跡データは、BizTalk 追跡データベースにメッセージ ボックス データベースから移動されません。  
  
- BAM の追跡データは、BAM プライマリ インポート データベースにメッセージ ボックス データベースから移動されません。  
  
- データが移動されていないために、メッセージ ボックス データベースから削除できません。  
  
- データのデコードに追跡サービスを停止すると、追跡インターセプターが実行され、メッセージ ボックス データベースに追跡データを書き込みます。 データが移動されていない場合は、これにより、いっぱいになるメッセージ ボックス データベースは時間の経過と共にパフォーマンスに影響します。 場合でも、カスタム プロパティは追跡されませんまたは BAM プロファイルが設定されていない、既定ではいくつかのデータが追跡 (など、パイプラインは、受信/送信イベントおよびオーケストレーションのイベント)。 データのデコードに追跡サービスを実行しない場合は、すべての追跡インターセプターをデータベースにデータ保存しないようにオフにします。 グローバル追跡を無効にするを参照してください。[グローバル追跡をオフにする方法](http://go.microsoft.com/fwlink/?LinkId=154193)(<http://go.microsoft.com/fwlink/?LinkId=154193>) 使用して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]選択的に追跡イベントを無効にする管理コンソール。  
  
## <a name="optimizing-performance-for-a-dedicated-tracking-host"></a>専用の追跡ホストのパフォーマンスを最適化します。  
 このホストを実行するには少なくとも 2 つのコンピューターで実行する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)](に備えて冗長性のいずれかが失敗)。 最適なパフォーマンスを少なくとも 1 つの追跡がある必要がありますメッセージ ボックス データベースごとにホストのインスタンス。 追跡ホスト インスタンスの実際の数が n+1 にする必要があります、N = メッセージ ボックス データベースの数。 「+ 1」冗長性実現のためです。 以上の機能も、1 つだけの追跡は、インスタンスをホストするための追加の特典が特定のメッセージ ボックス データベースのデータを移動しないがあります。 その結果、ロックする必要がありますしない問題があります。 1 つ追加追跡ホスト インスタンスがフォールト トレランスの追加インスタンスの失敗をホスト、追跡のいずれかの追加のインスタンスは、失敗したインスタンスの職務と想定されます。  
  
 追跡ホスト インスタンスが特定のメッセージ ボックス データベースの追跡データを移動しますが、されません 1 つ以上の追跡ホスト インスタンスの特定のメッセージ ボックス データベースのデータを移動します。 たとえば、3 つのメッセージ ボックス データベースとホスト インスタンスを追跡するだけの 2 つある場合は、そのホスト インスタンスの 1 つ必要があります、メッセージ ボックス データベースの 2 つのデータを移動します。 追跡ホスト インスタンスを追跡する 3 つ目の追加は分散作業を実行している別のコンピューターのホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 このシナリオで、4 つ目のホスト インスタンスの追跡は、複数の追跡ホストを配布できませんを追加するが提供されます余分なフォールト トレランスのホスト インスタンスを追跡します。  
  
 BAM イベント バス サービスの詳細については、BizTalk Server ヘルプで、次のトピックを参照してください。  
  
-   [BAM イベント バス サービスの管理](http://go.microsoft.com/fwlink/?LinkId=154194)(http://go.microsoft.com/fwlink/?LinkId=154194)  
  
-   [BAM イベント バス サービスのインスタンスを作成する](http://go.microsoft.com/fwlink/?LinkId=154195)(http://go.microsoft.com/fwlink/?LinkId=154195)  
  
## <a name="configuring-a-dedicated-tracking-host"></a>専用の追跡ホストの構成  
 このセクションでは、手順を実行するには、ホストの追跡を許可するホストのプロパティを変更するための次のユーザー権利が必要です。  
  
- メンバーである必要がありますが、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  
  
- SQL Server には次の権利が必要です。  
  
  -   SQL Server の管理者またはのメンバーのいずれかにある必要があります、 *db_owner*または*db_securityadmin* BizTalk 追跡データベース (BizTalk DTADb)、メッセージ ボックス データベース (SQL Server データベース ロールBizTalkMsgBoxDb)、および BAM プライマリ インポート データベース (BAMPrimaryImport)。  
  
  -   メッセージ ボックス データベース、またはのメンバーのすべてのコンピューター上の sysadmin SQL Server ロールのメンバーである、 *db_owner*または*db_ddladmin*すべてのメッセージ ボックス データベースの SQL Server ロール。  
  
#### <a name="to-enable-host-tracking"></a>ホストの追跡を有効にするには  
  
1. クリックして**開始**、] をクリックして**プログラム**、] をクリックして**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**[BizTalk グループ]、をクリックして**プラットフォームの設定**、] をクリックし、**ホスト**します。  
  
3. 詳細ペインで、変更、およびクリックするホストを右クリックして**プロパティ**します。  
  
4. **ホストのプロパティ**] ダイアログ ボックスで、**全般**タブ、オンまたはオフ**オプション]-[ホストの追跡を許可する**、順にクリックします **[ok]**。  
  
    ホストで BizTalk の追跡コンポーネントを読み込んで、状態監視データおよびビジネス データを処理する場合は、このチェック ボックスをオンにします。 このチェック ボックスをオンにすると、メッセージ ボックス データベースの追跡テーブルおよび追跡データベースに対する読み取り/書き込みアクセスが現在のホストに許可されます。 これに伴い、このホスト内で実行されるオブジェクトにも、これらのデータベースに対する読み取りと書き込みのアクセス許可が与えられます。  
  
    チェック ボックスをオフにした場合、ホストはメッセージ ボックス データベースに追跡テーブルへの書き込みアクセス権のみし、追跡データベースへのアクセスはありません。  
  
## <a name="see-also"></a>参照  
 [チェックリスト: BizTalk Server の構成](../technical-guides/checklist-configuring-biztalk-server.md)