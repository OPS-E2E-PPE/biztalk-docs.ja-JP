---
title: 管理ロールのアクセス制御 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- roles, administrative
- administrator accounts, administrative roles
- administrative roles
- access control, administrative roles
ms.assetid: 328e049b-921d-4057-85f0-7d008ec308bb
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfc7b1891cd266457af97c18f2ad6220145e00ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225818"
---
# <a name="access-control-for-administrative-roles"></a>管理ロールのアクセス制御
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ツールを開いてデータベースや Windows リソースにアクセスし、そのツールがサポートしているさまざまな作業を実行するには、SQL Server および Windows で適切なユーザー権限が与えられていなければなりません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のツールは [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースにアクセスします。 したがって BizTalk Server では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者に対して、データベースごとに適切なアクセス権を付与する必要があります。 ただしセキュリティ上の理由から、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者に対し、業務の遂行に不要なユーザー権限は設定しないようにします。 SQL Server データベース ロールを使用すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で両方の条件を満たすことができます。 インストール中、または [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールを使用して [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] データベースを作成すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、2 つの管理ロール用の SQL ロールがデータベースに自動的に作成されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]各ロール、およびロールに割り当てられているすべての SQL Server ログイン (テーブル、ビュー、ストアド プロシージャなど) をそのデータベースに対する管理タスクを実行する SQL Server オブジェクト上の管理者によって必要な最小ユーザー権限を付与します。  
  
> [!NOTE]
>  ホスト インスタンスの作成など、管理タスクによっては、SQL Server ロールで BizTalk 管理者に与えられた以上の権限が必要となる場合があります。 追加のアクセス許可の詳細については、次を参照してください。[最低限のセキュリティ ユーザー権限](../core/minimum-security-user-rights.md)です。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者と [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operator の 2 種類の管理者ロールがあります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者は権限レベルの高いロールで、構成データおよび追跡データにアクセスできます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operator は権限レベルの低いロールで、監視操作とトラブルシューティング操作にのみアクセスできます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループ:   
  
-   権限の低い管理ロールで、メッセージ データにアクセスする権限はありません。  
  
-   メンバーは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のエラー、中断したメッセージやインスタンスへのクエリ、ビュー構成を監視できます。  
  
-   メンバーは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 構成を変更できません。 たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operator は、送信ポート、受信場所、ポート上のフィルターを変更できず、新しいアイテムを展開できません。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を初めてインストールすると、既定の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者ロールが作成されます。 既定では、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]この[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者は、別の名前を選択することができます。  
  
 同様に、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、各ホストのユーザー グループ用の SQL Server Database ロールが各データベースに作成されます。作成されたロールには、ユーザー グループがそのホストに対してタスクを実行するときに必要となる最小限のユーザー権限が許可されます。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者は、シングル サインオン関連管理者グループに追加する必要があります。 エンタープライズ シングル サインオンに関する詳細については、次を参照してください。[を使用して SSO](../core/using-sso.md)です。  
  
> [!CAUTION]
>  BizTalk 管理者は、システムに展開するアセンブリのソースが信頼済みであることを確認する必要があります。 信頼済みでないコードが含まれるアセンブリを展開すると、BizTalk 環境が攻撃の対象になる可能性があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、BizTalk エンジンでカスタム コード コンポーネントが呼び出された場合、このコンポーネントで実行される処理に対しては制限が適用されません。  
  
## <a name="see-also"></a>参照  
 [アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)   
 [BizTalk Server の Windows グループ アカウントとユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)