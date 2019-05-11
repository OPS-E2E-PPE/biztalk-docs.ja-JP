---
title: メッセージとインスタンス データ追跡のセキュリティに関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- permissions, HAT
- MessageBox database, HAT
- Tracking database, HAT
- security, HAT
- HAT, permissions
- HAT, security
- Management database, HAT
ms.assetid: 83e47dc2-c8e2-42a2-9c85-d511e7dae83f
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4cce159d9012b3fd52405114898f1a2b257a2297
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280309"
---
# <a name="security-considerations-for-message-and-instance-data-tracking"></a>メッセージとインスタンス データの追跡のセキュリティに関する考慮事項
セキュリティ上の理由から、メッセージとサービス インスタンスの追跡を使用しませんブラウザーや Url の以前のリリースのように[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 この監視オプションは、BizTalk Server 管理コンソールの [グループ概要] ページの一部として含まれています。  旧バージョンと互換性のため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セキュリティ上の理由からシェル内で Microsoft Internet Explorer を引き続きホストします。  

 メッセージとサービス インスタンスのデータを追跡してトラブルシューティングし、最適化に必要な技術的な詳細を表示できます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境。 この追跡データは、強力なであるために、悪質または不正なユーザーが危害を及ぼさないように、実稼働環境でアクセスを制限する必要があります。 セキュリティで保護して環境内で、BizTalk Server 管理コンソールを使用してこれらのガイドラインに従うことをお勧めします。  

- メンバーとしてログオンする必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループ、BizTalk Server 管理コンソールを使用してデータを表示します。 メッセージ本文のグループの概要のセクションにアクセスする、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのメンバーとしてログオンする必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。  

   メッセージとサービス インスタンスの追跡を使用すると、次のデータベースにアクセスできます。  


  |               [データベース]               |                                                                                                   ユーザー/グループの権限                                                                                                   |
  |--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |  BizTalk 管理 (BizTalkMgmtDb)  |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]演算子               |
  | BizTalk メッセージ ボックス (BizTalkMsgBoxDb) | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者は、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators、または読み取り/書き込みアクセス許可 |
  |   BizTalk 追跡 (BizTalkDTADb)    | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者は、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators、または読み取り専用アクセス許可  |


- 追跡メッセージおよびサービスのインスタンスのすべてのホストに関するレポートを生成する、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]クエリのパラメーターに基づいて環境。 メンバーのみ、情報の漏えいの可能性を最小限に抑える、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループは、BizTalk Server 管理コンソールを使用して、これらのクエリを実行します。 ただし、すべてしない場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者がデータにアクセスするこの追跡プロセスで生成してから、BizTalk のロール HM_EVENT_WRITER と BAM_EVENT_WRITER SQL Server の ユーザーの追加と削除、データへのアクセスを制限します。追跡 (BizTalkDTADb) データベース。  

- BizTalk では、BAM_EVENT_WRITER と HM_EVENT_WRITER の SQL Server の役割を使用して、許可/拒否のメンバーがロールのメンバーシップではなく、追跡データベースに追跡データの読み取り/書き込みアクセスを許可します。 これらの SQL Server ロールは削除しないでください。 追跡をホストしていないホストからホストを変更すると (またはその逆) adm_ChangeHostTrackingPrivilege ストアド プロシージャが呼び出されます。 このストアド プロシージャは、BAM_EVENT_WRITER と HM_EVENT_WRITER の SQL Server ロールの定義を読み取って、ホスト Windows グループに対応する GRANT/DENY ステートメントを適用します。 これには、これらの SQL ロールに、ホスト Windows グループを追加すると同じ効果が得られます。  

- アーカイブ済みのデータベースからデータを表示する BizTalk Server 管理コンソールの基本設定を構成するときに、現在アクティブな BizTalk 追跡 (BizTalkDTADb) がアーカイブ済みのデータを保持するデータベースにここで、追跡クエリ接続します。データベース。  

- ネットワーク アドレス変換 (NAT) ファイアウォールを介したライブ オーケストレーションをデバッグすることはできません。 管理用コンピューターは、ライブ オーケストレーションをデバッグするには、処理ドメインが必要です。  

- 追跡およびパイプラインの構成方法に応じて[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]メッセージ コンテキストに含まれる機密情報を格納することがあります。 メッセージ本文をファイルの場所に保存する WMI または追跡を使用する場合は、場所がだけが強力な随意アクセス制御リスト (DACL) を持つことを確認[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者がこれらのメッセージ本文へのアクセス許可を読み取る。 非 BizTalk データベースのアーカイブし、復元可能性がありますも含め、メッセージ本文を保存する任意の場所に同一の DACL を適用します。  

- アクセス許可を手動で付与する必要があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators グループ、Tracking Analysis Server (BizTalkAnalysisDb) データベースへのアクセスに既定では、OLAP 管理者のみがあることへのアクセス許可。  

## <a name="see-also"></a>参照  
 [メッセージとインスタンスの追跡の計画](../core/planning-for-message-and-instance-tracking.md)   
 [追跡メッセージおよびインスタンス データの表示](../core/viewing-tracked-message-and-instance-data.md)