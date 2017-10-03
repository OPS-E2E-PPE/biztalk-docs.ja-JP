---
title: "ビューからアカウントを削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Excel add-in [BAM], security
- managing [BAM], deleting accounts from views
- Remove-Account command [BAM]
ms.assetid: b74a64a0-ddb3-45d2-add7-6261c31be0f0
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80c0909a5544334cd9f0f8540ff5a4c357b851e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-accounts-from-a-view"></a>ビューからアカウントを削除する方法
管理者を使用して、**削除アカウント**コマンドを BAM ビューからユーザーを削除して、BAM Excel ワークシート ビューを不正アクセスから保護します。  
  
 BAM ビューを表示する方法については、次を参照してください。[リスト BAM ビューの表示方法](../core/how-to-list-bam-views.md)です。  
  
### <a name="to-remove-an-account-from-a-view"></a>ビューからアカウントを削除するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡  
  
3.  型**bm 削除アカウント-accountname:\<アカウント名 >-ビュー:\<ビュー名 >**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)