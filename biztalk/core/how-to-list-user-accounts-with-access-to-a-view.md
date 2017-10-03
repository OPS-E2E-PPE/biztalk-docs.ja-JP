---
title: "ビューにアクセス権を持つアカウントのユーザーを一覧表示する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- user accounts, BAM
- managing [BAM], user accounts
- Get-Accounts utility [BAM]
ms.assetid: 690fb45a-6de0-489e-9ddd-e88e29413c16
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 099a2b8f3d914297529a192def9e5c23a49d31af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-list-user-accounts-with-access-to-a-view"></a>ビューへのアクセス権を持つユーザー アカウントを一覧表示する方法
管理者を使用して、 **get アカウント**BAM 管理ユーティリティのコマンド一覧を取得する、すべてのユーザー アカウントのビュー ロールの場合、指定されたビューへのアクセス権を持つすべてのユーザー アカウントを意味します。  
  
 BAM ビューを表示する方法については、次を参照してください。[リスト BAM ビューの表示方法](../core/how-to-list-bam-views.md)です。  
  
### <a name="to-list-user-accounts-with-access-to-a-view"></a>ビューへのアクセス権を持つユーザー アカウントを一覧表示するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡  
  
3.  型**bm get-アカウントの表示:\<ビュー名 >**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)