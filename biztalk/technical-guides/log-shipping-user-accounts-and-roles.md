---
title: ログ配布のユーザー アカウントとロール |Microsoft Docs
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
ms.openlocfilehash: f60dedeadb90f01daeb6e476727b75af1e0ea5be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400376"
---
# <a name="log-shipping-user-accounts-and-roles"></a>ログ配布のユーザー アカウントとロール
BizTalk Server のバックアップおよびログを復元するプロセスを自動化するログ配布は SQL Server エージェント ジョブによって実行されます。 不適切なアクセス許可には、復元操作が失敗する BizTalk Server ログ配布によって実行される可能性があります。 データベースを復元するように構成するユーザー アカウントは、BizTalk 管理データベースをホストする実稼働データベースのインスタンスへのアクセスに必要です。 ほとんどの場合つまりサービス アカウントのディザスター リカバリーを BizTalk Server のログ配布ジョブを促進する SQL Server エージェント ジョブ[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスは、ログインと、をホストする実稼働データベースのインスタンスでアクセス許可が必要です[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。管理データベース。 これにより、ジョブの所有者として、SQL Server エージェント サービス アカウントが構成されていることを前提としています。  

 BizTalk Server には BTS_BACKUP_USERS という名前のデータベースを復元するように構成するユーザー アカウントに SQL Server システム管理者のアクセス許可が必要としないように SQL Server ロールが含まれています。  

 BizTalk Server ログ配布の一部としてデータベースの復元操作を実行するユーザー アカウントを構成する場合は、次の点を確認してください。  

- マップされたユーザーで構成されているドメイン アカウントで実行する SQL Server エージェント サービスを構成する[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Management Studio (で**セキュリティ**、**ログイン**) 各[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]インスタンスに移動ホスト[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]で復元されたデータベース、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配布ジョブ ログに記録します。  

- 構成、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]ログインこのユーザー アカウントし、このユーザーを各サーバーでの BizTalk BTS_BACKUP_USERS SQL ロールに割り当てます。  

- このユーザーを割り当てる、[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]システム管理者の役割が実行されているコンピューター[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]を格納、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理データベース。  

- バックアップを実行するアカウントと復元操作の読み取りが必要と UNC への書き込みアクセスは、バックアップ ファイルが作成される場所を共有します。
