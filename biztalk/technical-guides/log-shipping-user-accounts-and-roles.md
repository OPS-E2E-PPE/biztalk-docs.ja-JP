---
title: "ログ配布のユーザー アカウントとロール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2056ea90-5e9f-4501-95d6-18c905db4023
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b19a7d7c87289e07c7ac7a26bacd0c96f9090c9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="log-shipping-user-accounts-and-roles"></a>ログ配布のユーザー アカウントとロール
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ログ配布は、バックアップおよびログを復元するプロセスを自動化する SQL Server エージェント ジョブによって左右されます。 不適切なアクセス許可によって実行される復元操作が発生することができます[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ログ配布が失敗します。 データベースを復元するように構成するユーザー アカウントは、BizTalk 管理データベースをホストしている実稼働データベース インスタンスへのアクセスに必要です。 ほとんどの場合これは意味をサービス アカウント、SQL Server エージェント ジョブを推進するため、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]災害復旧でログ配布ジョブ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは、ログインや、をホストしている実稼働データベースインスタンスに対するアクセス許可が必要です[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。管理データベース。 これにより、ジョブの所有者として、SQL Server エージェント サービス アカウントが構成されていることを前提としています。  
  
 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]データベースを復元するように構成するユーザー アカウントに SQL Server システム管理者権限が必要がないように、BTS_BACKUP_USERS をという名前の SQL Server ロールが含まれます。  
  
 一部としてデータベースの復元操作を実行するユーザー アカウントを構成するときに[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]ログ配布、次を確認してください。  
  
-   構成されているマップされたユーザーのドメイン アカウントで実行する SQL Server エージェント サービスを構成する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio (で**セキュリティ**、**ログイン**) ごとに[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスですホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で復元されたデータベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配布ジョブを記録します。  
  
-   構成、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインこのユーザーのアカウントし、各サーバー上で BizTalk BTS_BACKUP_USERS SQL ロールにこのユーザーを割り当てます。  
  
-   このユーザーを割り当てる、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システム管理者ロールを実行するコンピューターの[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理データベース。  
  
-   バックアップを実行するアカウントと復元操作の読み取りが必要と UNC への書き込みアクセスは、バックアップ ファイルが作成される場所を共有します。