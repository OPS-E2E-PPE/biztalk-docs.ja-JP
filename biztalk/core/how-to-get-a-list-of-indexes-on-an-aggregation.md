---
title: "集計のインデックスの一覧を取得する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- indexes [BAM], listing indexes
- aggregations [BAM], listing indexes
- Get-Index command [BAM]
ms.assetid: 46a4a2fc-10f8-499c-bf2a-d0a19bb84151
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b8b636534738dfc7445421ad79fd01e7b120b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-get-a-list-of-indexes-on-an-aggregation"></a>集計のインデックスの一覧を取得する方法
管理者を使用して、 **get インデックス**コマンドを指定されたアクティビティですべてのインデックスの一覧を取得します。  
  
### <a name="to-get-a-list-of-indexes-on-an-aggregation"></a>集計のインデックスの一覧を取得するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking に移動します。  
  
3.  型**bm get インデックス-アクティビティ:\<アクティビティ名 >**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [インデックスを削除する方法](../core/how-to-delete-an-index.md)   
 [インデックスを作成する方法](../core/how-to-create-an-index.md)