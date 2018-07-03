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
ms.openlocfilehash: 3ff40db932a7fa1932830289557e1e0bb71b61c7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974571"
---
# <a name="security-considerations-for-message-and-instance-data-tracking"></a>メッセージとインスタンス データの追跡のセキュリティに関する考慮事項
セキュリティ上の理由により、メッセージとサービス インスタンスの追跡では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の以前のリリースとは異なりブラウザーや URL を使用しません。 この監視オプションは BizTalk Server 管理コンソールの [グループの概要] ページに含まれています。  下位互換性のため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ではセキュリティ上の理由からシェル内で Microsoft Internet Explorer をホストします。  

 メッセージとサービス インスタンス データを追跡することで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のトラブルシューティングと最適化に必要な技術的な詳細にアクセスできます。 この追跡データは強力なので、実稼働環境ではアクセスを制限し、悪意のあるユーザーや未承認のユーザーが危害を及ぼさないようにしてください。 BizTalk Server 管理コンソールをセキュリティで保護して環境で使用するには、次のガイドラインに従うことをお勧めします。  

- BizTalk Server 管理コンソールを使用してデータを表示するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンする必要があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールの [グループの概要] セクションのメッセージ本文にアクセスするには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンする必要があります。  

   メッセージとサービス インスタンスの追跡を使用すると、次のデータベースにアクセスできます。  


  |               [データベース]               |                                                                                                   ユーザー グループ/アクセス許可                                                                                                   |
  |--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
  |  BizTalk 管理 (BizTalkMgmtDb)  |              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators               |
  | BizTalk メッセージ ボックス (BizTalkMsgBoxDb) | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators、または読み取り書き込みアクセス許可 |
  |   BizTalk 追跡 (BizTalkDTADb)    | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators、または読み取り専用アクセス許可  |


- メッセージとサービス インスタンスの追跡により、クエリのパラメーターに基づいて [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境のすべてのホストに関するレポートが生成されます。 情報漏えいの可能性を最小限に抑えるため、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーのみが BizTalk Server 管理コンソールを使用してこれらのクエリを実行できます。 この追跡プロセスで生成されるデータに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者の全員がアクセスできることを希望しない場合、データにアクセスするメンバーを制限するために、BizTalk 追跡 (BizTalkDTADb) データベースの SQL Server ロール HM_EVENT_WRITER と BAM_EVENT_WRITER に対して、ユーザーの追加と削除を行います。  

- SQL Server ロール BAM_EVENT_WRITER と HM_EVENT_WRITER は、追跡データベースの追跡データを読み取ったり書き込んだりする権限を管理者グループのメンバーに許可または拒否するために使用されます。その際、ロールのメンバーシップは使用されません。 これらの SQL Server ロールは削除しないでください。 追跡をホストしていないホストからホストを変更すると (またはその逆) adm_ChangeHostTrackingPrivilege ストアド プロシージャが呼び出されます。 このストアド プロシージャで、SQL Server ロール BAM_EVENT_WRITER と HM_EVENT_WRITER の定義が読み取られ、対応する GRANT/DENY ステートメントが Host Windows グループに適用されます。 この動作は、それぞれの SQL ロールに Host Windows グループを追加するのと同等の効果があります。  

- アーカイブ済みのデータベースのデータを表示するように BizTalk Server 管理コンソールの基本設定を構成している場合、追跡クエリは現在アクティブな BizTalk 追跡 (BizTalkDTADb) データベースではなく、アーカイブ済みのデータが保存されているデータベースに接続されます。  

- ネットワーク アドレス変換 (NAT) ファイアウォールを経由してライブ オーケストレーションをデバッグすることはできません。 ライブ オーケストレーションをデバッグするには、処理ドメインに管理用のコンピューターを用意する必要があります。  

- 追跡とパイプラインの構成の方法によっては、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] にメッセージ コンテキスト内の機密情報が保存される場合があります。 WMI または追跡を使用してメッセージ本文をファイルの場所に保存する場合、その場所の随意アクセス制御リスト (DACL) を強化して、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者のみにメッセージ本文の読み取りアクセス許可を与えるようにしてください。 メッセージ本文、および本文のアーカイブと復元が可能な BizTalk 以外のデータベースを保存する場所には、同一の DACL を適用します。  

- [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループに、Tracking Analysis Server (BizTalkAnalysisDb) データベースへのアクセス許可を手動で与える必要があります。既定では、このデータベースにアクセスできるのは OLAP 管理者のみです。  

## <a name="see-also"></a>参照  
 [メッセージとインスタンスの追跡の計画](../core/planning-for-message-and-instance-tracking.md)   
 [追跡メッセージおよびインスタンス データの表示](../core/viewing-tracked-message-and-instance-data.md)