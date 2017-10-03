---
title: "アクセス制御とデータのセキュリティ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- access control, BizTalk Server Operator role
- databases, SQL roles
- access control, about access control
- BizTalk Server Administrator role
- databases, access control
- access control
- access control, BizTalk Server Administrator role
- access control, SQL roles
- user accounts, access control
- BizTalk Server Operator role
ms.assetid: f04fd4a3-0f8c-4170-934a-9cc77edd7f34
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11cb00eabf6110de78e2d194e0a25bfac6a3b6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="access-control-and-data-security"></a>アクセス制御とデータのセキュリティ
BizTalk Server では、ユーザー権限を最小限にすることでプロセスとデータベースへのアクセスを制限しています。システム内の重要なデータは、Microsoft Windows Server の機能を使用して、セキュリティで保護できます。 セキュリティ上の理由から、BizTalk Server 管理者および BizTalk ホストに対して、業務の遂行に不要なユーザー権限を設定しないでください。  
  
 BizTalk では、データへの管理アクセスは SQL ロールを使用して制御されます。この方法により、ツールを使用する場合も直接データベースを利用する場合もデータへのアクセスを制御できます。 BizTalk ホストからのデータへのアクセスは、ホスト ユーザー グループとアカウントを使用して制御されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、BizTalk Server 管理者と BizTalk Server Operator の 2 種類の管理者ロールがあります。 インストールまたは BizTalk Server 管理コンソールを使用して BizTalk Server データベースを作成する BizTalk Server により、これら両方の管理ロール用の SQL ロールがそのデータベースに自動的に作成します。 各ロール、およびロールに割り当てられる SQL Server ログインには、管理者がデータベースで管理タスクを実行するときに SQL Server オブジェクト (テーブル、ビュー、ストアド プロシージャなど) に対して持っている必要のある最小限のユーザー権限が許可されます。  
  
 BizTalk Server 管理者は権限レベルの高いロールで、構成データおよび追跡データにアクセスできます。 BizTalk Server Operator は、監視とトラブルシューティング操作にのみアクセス権を持つ特権の低いロールです。 BizTalk Server Operator ロールはサービスの状態とメッセージ フローを表示したり、アプリケーションを開始および停止したり、サービス インスタンスを終了および再開することができますが、構成を変更したり、メッセージのプロパティと内容を表示することはできません。  
  
 同様に、BizTalk Server では、各ホストのユーザー グループ用の SQL ロールが各データベースに作成されます。作成されたロールには、ユーザー グループがそのホストに対してタスクを実行するときに必要となる最小限のユーザー権限が許可されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server の Windows グループ アカウントとユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [グループおよびサービス アカウントのアクセス制御](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [管理ロールのアクセス制御](../core/access-control-for-administrative-roles.md)  
  
-   [ビジネス情報へのアクセス制御](../core/access-control-to-business-information.md)  
  
-   [セキュリティの最小ユーザー権限](../core/minimum-security-user-rights.md)