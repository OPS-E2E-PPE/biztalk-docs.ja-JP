---
title: アクセス制御とデータ セキュリティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e34babf08ccc18d0e20165b5f3a39914ad7324e1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362259"
---
# <a name="access-control-and-data-security"></a>アクセス制御とデータ セキュリティ
BizTalk Server は、最小限のユーザーの権限を使用して、プロセスとデータベースへのアクセスを制限します。Microsoft Windows Server から機能を使用して、セキュリティで保護された重要なデータのシステムに役立ちます。 セキュリティ上の理由から、BizTalk Server 管理者と BizTalk ホストは必要ありません、ジョブを実行するために必要なユーザー権限。  
  
 両方ツールおよびデータベースを使用して直接データへのアクセスを制御するための SQL ロールを使用してデータにアクセスする BizTalk 制御管理します。 データへの BizTalk ホストでは、ホスト ユーザー グループとアカウントを使用して制御されます。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、2 つの管理ロール: BizTalk Server 管理者、および BizTalk Server Operator します。 インストールや、BizTalk Server 管理コンソールを使用して BizTalk Server データベースを作成するときにいつでも BizTalk Server により、これら両方の管理ロール用の SQL ロールがそのデータベースに自動的に作成します。 BizTalk Server では、各ロール、およびロールに割り当てられているすべての SQL Server ログインで SQL Server オブジェクト (テーブル、ビュー、ストアド プロシージャなど) をそのデータベースでの管理タスクを実行する管理者の必要最小限のユーザー権限を付与します。  
  
 BizTalk Server の管理者は、構成データおよび追跡データへのアクセスを高い特権を持つロールです。 BizTalk Server Operator は、監視とトラブルシューティング操作にのみアクセス権を持つ特権の低いロールです。 この後者のロールできますサービスの状態とメッセージ フローを表示しできます開始またはアプリケーションを停止および終了および再開サービス インスタンスしますが、メッセージのプロパティを構成またはビューとコンテンツを変更することはできません。  
  
 同様に、BizTalk Server は、各ホストの各データベースでユーザー グループ用の SQL ロールを作成し、このロールをホストするためのタスクを実行するユーザー グループに必要な最小ユーザー権限が付与されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server の Windows グループ アカウントとユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)  
  
-   [グループ アカウントおよびサービス アカウントのアクセス制御](../core/access-control-for-groups-and-service-accounts.md)  
  
-   [管理ロールのアクセス制御](../core/access-control-for-administrative-roles.md)  
  
-   [企業情報へのアクセス制御](../core/access-control-to-business-information.md)  
  
-   [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)