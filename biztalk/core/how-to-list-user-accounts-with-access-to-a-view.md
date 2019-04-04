---
title: ビューにアクセス権を持つアカウントのユーザーの一覧を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e27f1f48846c1eb134c2ee71bf9c00c72d4a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981707"
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a>ビューへのアクセス権を持つユーザー アカウントを一覧表示する方法
管理者を使用して、 **get アカウント**ビュー ロールの場合、指定されたビューへのアクセスを持つすべてのユーザー アカウントを意味するすべてのユーザー アカウントの一覧を取得する BAM 管理ユーティリティ コマンド。  
  
 BAM ビューを表示する方法については、[BAM ビューをリストする方法](../core/how-to-list-bam-views.md)を参照してください。  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a>ビューへのアクセス権を持つユーザー アカウントを一覧表示するには  
  
1. 次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. 移動します[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡  
  
3. 型**bm get-アカウントのビュー:\<ビュー名\>** します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)