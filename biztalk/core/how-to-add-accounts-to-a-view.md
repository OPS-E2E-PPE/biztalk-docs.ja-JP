---
title: "ビューにアカウントを追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- Add-Account command [BAM]
- managing [BAM], adding accounts to views
ms.assetid: 0875796c-82a4-4165-9bed-88e8ba466548
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc8d369eb24d1a239f1c305ab74230eab0f32d67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-accounts-to-a-view"></a>アカウントをビューに追加する方法
管理者を使用して、**アカウントの追加**ユーザーを BAM ビューに関連付けるし、BAM Excel ワークシート ビューを不正アクセスから保護するコマンド。 ユーザーが BAM ビューを保存するときに、ビューはブック内で非表示になっている SQL 接続文字列を参照します。 ブックは保護されていますが、さらにドキュメントが確実に保護されるようにする必要があります。  
  
 ユーザーを BAM ビューに関連付けるときに、アクセスを許可したユーザーまたはグループのみにビューへのアクセスを制限します。  
  
> [!IMPORTANT]
>  リアルタイム集計 (Rta) を使用している場合で追加されたユーザー**アカウントの追加**SQL Server を実行しているコンピューターへのログオン権限を自動的に付与することはできません。 RTA を使用している場合は、RTA のビューを表示しなければならないすべてのユーザーを含む、Windows ユーザー グループの作成を検討してください。 そのグループ、BAM プライマリ インポート データベースをホストする SQL server で SQL Server ログオン権限を明示的に許可します。  
  
 BAM ビューを表示する方法については、次を参照してください。[リスト BAM ビューの表示方法](../core/how-to-list-bam-views.md)です。  
  
### <a name="to-add-an-account-to-a-view"></a>アカウントをビューに追加するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3.  型**bm アカウントの追加-accountname:\<アカウント名 >-ビュー:\<ビュー名 >**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)