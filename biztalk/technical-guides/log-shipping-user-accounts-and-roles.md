---
title: ログ配布のユーザー アカウントとロール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7dbec7cfa23c8a1e07e32cdf0c3ce7b044651ec
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010603"
---
# <a name="log-shipping-user-accounts-and-roles"></a>ログ配布のユーザー アカウントとロール
BizTalk Server のバックアップとログを復元するプロセスを自動化する SQL Server エージェント ジョブはログ配布、実行します。 不適切なアクセス許可には、復元操作が失敗する BizTalk Server ログ配布によって実行される可能性があります。 データベースを復元するように構成するユーザー アカウントは、BizTalk 管理データベースをホストしている実稼働データベース インスタンスへのアクセスに必要です。 ほとんどの場合つまり、このサービス アカウントの災害復旧の BizTalk Server のログ配布ジョブを推進 SQL Server エージェント ジョブ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは、ログインや、をホストしている実稼働データベースインスタンスに対するアクセス許可が必要です[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。管理データベース。 これにより、ジョブの所有者として、SQL Server エージェント サービス アカウントが構成されていることを前提としています。  
  
 BizTalk Server には、データベースを復元するように構成するユーザー アカウントに SQL Server システム管理者権限が必要がないように、BTS_BACKUP_USERS をという名前の SQL Server ロールが含まれています。  
  
 BizTalk Server のログ配布の一部としてデータベースの復元操作を実行するユーザー アカウントを構成する場合は、次の点を確認してください。  
  
-   構成されているマップされたユーザーのドメイン アカウントで実行する SQL Server エージェント サービスを構成する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio (で**セキュリティ**、**ログイン**) ごとに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスですホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で復元されたデータベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配布ジョブを記録します。  
  
-   構成、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインこのユーザーのアカウントし、各サーバー上で BizTalk BTS_BACKUP_USERS SQL ロールにこのユーザーを割り当てます。  
  
-   このユーザーを割り当てる、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システム管理者ロールを実行するコンピューターの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理データベース。  
  
-   バックアップを実行するアカウントと復元操作の読み取りが必要と UNC への書き込みアクセスは、バックアップ ファイルが作成される場所を共有します。