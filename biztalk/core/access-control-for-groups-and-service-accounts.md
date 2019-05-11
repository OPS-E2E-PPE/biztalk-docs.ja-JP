---
title: グループおよびサービス アカウントのアクセス制御 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- access control, service accounts
- user accounts, default accounts
- service accounts, security
- user accounts, unsupported
- access control, groups
- service accounts, access control
- groups, access control
- groups, security
ms.assetid: 411a7bfa-6675-4d09-9e37-83e2941df3c6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f3e34d34f9b6a79b1379c98aa362c266a52424c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362066"
---
# <a name="access-control-for-groups-and-service-accounts"></a>グループおよびサービス アカウントのアクセス制御
各 BizTalk ホスト インスタンスは、ユーザーが作成したサービス アカウントで実行されます。 サービス アカウントを指定する必要があり、時に、パスワード、コンピューター上にホスト インスタンスを作成します。 BizTalk Server では、次のアカウントに、さらに、追加されることをホストするには特定の SQL Server データベース ロールにローカルまたはドメイン Windows グループに各サービス アカウントを追加することで、ジョブの実行に必要な最小ユーザー権限があることによりできます。  
  
 このアプローチには次の利点があります。  
  
- 付与できます各ホスト インスタンスに異なるサービス アカウントにサーバーをオフラインにしなくても、各ホスト インスタンス用のパスワードを変更できるようにします。 サービスを中断せず、パスワードのローリング更新プログラムを実行できます。  
  
  > [!NOTE]
  >  認証が信頼済みであるホストと信頼されている認証ではないホストを同じサービス アカウントを使用することはできません。  
  
- リソース ユーザー権限をローカルまたはドメイン グループ Microsoft SQL Server™ レベルを付与する場合は、追加し、管理の負担や総所有コストの削減、SQL Server で許可されるユーザー権限を変更することがなくサービス アカウントを減算します。  
  
  サービス アカウントが、ジョブの実行に必要な最小ユーザー権限を持っていることを確認するには、は、BizTalk サーバーのサービス アカウントを作成する SQL Server データベース ロールは、すべての BizTalk Server データベースで同一ではありません。 管理および追跡データベースですべてのホスト インスタンス サービス アカウント必要があります、同じ SQL Server オブジェクトへのアクセスのため、BizTalk Server は BTS_Host_User という名前の 1 つの SQL Server データベース ロールを作成します。 BizTalk は、この SQL Server データベース ロールに BizTalk ホスト用に作成されたすべての Windows グループを追加します。  
  
  メッセージ ボックス データベースの場合は、各ホストは専用のリソースの一部が。 BizTalk Server は、bts _ という名前のホストごとの SQL Server データベース ロールを作成します。\<*ホスト名*\>(_u)、1 つのアクセスをブロックするために、それぞれの SQL Server データベース ロールには、各ホストの Windows グループを追加します。別のホストのリソースをホストします。  
  
## <a name="accounts-not-supported-by-biztalk-server"></a>BizTalk Server でサポートされていないアカウント  
 BizTalk Server では、次の組み込み Windows アカウントのいずれかを使用することはできません。  
  
-   NT_AUTHORITY\NetworkService  
  
-   LocalSystem  
  
-   NT_AUTHORITY\LocalService  
  
## <a name="see-also"></a>参照  
 [管理ロールのアクセス制御](../core/access-control-for-administrative-roles.md)   
 [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)   
 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)