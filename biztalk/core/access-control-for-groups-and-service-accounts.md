---
title: "グループおよびサービス アカウントのアクセス制御 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a04129427b524f0e183012ba7f10df1288327a8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="access-control-for-groups-and-service-accounts"></a>グループおよびサービス アカウントのアクセス制御
BizTalk ホスト インスタンスは、ユーザーが作成したサービス アカウントで実行されます。 コンピュータにホスト インスタンスを作成するときには、サービス アカウントとパスワードを指定する必要があります。 その後、BizTalk Server では、これらのサービス アカウントがローカルまたはドメインの Windows グループに追加され、次に、そのホストに固有の SQL Server データベース ロールに追加されます。これで、ジョブの実行に必要な最小限のユーザー権限がアカウントに許可されます。  
  
 この方法には次の利点があります。  
  
-   ホスト インスタンスごとに異なるサービス アカウントを設定して、サーバーをオフラインにせずに各ホスト インスタンスのパスワードを変更できます。 サービスを中断せずに、パスワード更新のロールを実行できます。  
  
    > [!NOTE]
    >  認証が信頼済みに設定されているホストと認証が信頼済みに設定されていないホストで、同じサービス アカウントを使用することはできません。  
  
-   リソース ユーザー権限を Microsoft SQL Server™ レベルでローカル グループまたはドメイン グループに許可すると、SQL Server で許可されているユーザー権限を変更することなくサービス アカウントの追加や削除を実行できるため、所有者の管理の負担や総コストが軽減されます。  
  
 サービス アカウントに対し、ジョブ実行に必要な最小限のユーザー権限が許可されるようにするため、BizTalk Server でサービス アカウントに作成される SQL Server データベース ロールは、すべての BizTalk Server データベースで重複しないようになっています。 管理データベースおよび追跡データベースでは、ホスト インスタンス サービス アカウントはすべて同じ SQL Server オブジェクトにアクセスする必要があるため、BizTalk Server では BTS_Host_User という名前の単一の SQL Server データベース ロールが作成されます。 BizTalk ホスト用に作成された Windows グループは、すべてこの SQL Server データベース ロールに追加されます。  
  
 メッセージ ボックス データベースでは、各ホストに専用のリソースが割り当てられています。 BizTalk Server ホストごとに、bts _ という名前の SQL Server データベース ロールを作成する\<*hostname*\>(_u)、1 つのアクセスをブロックするために、それぞれの SQL Server データベース ロールには各ホストの Windows グループに追加されます別のホストのリソースをホストします。  
  
## <a name="accounts-not-supported-by-biztalk-server"></a>BizTalk Server でサポートされていないアカウント  
 BizTalk Server では、次の組み込み Windows アカウントの使用はサポートされていません。  
  
-   NT_AUTHORITY\NetworkService  
  
-   LocalSystem  
  
-   NT_AUTHORITY\LocalService  
  
## <a name="see-also"></a>参照  
 [管理ロールのアクセス制御](../core/access-control-for-administrative-roles.md)   
 [セキュリティ保護のための最小ユーザー権限](../core/minimum-security-user-rights.md)   
 [Windows グループと BizTalk Server でのユーザー アカウント](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [アクセス制御とデータ セキュリティ](../core/access-control-and-data-security.md)