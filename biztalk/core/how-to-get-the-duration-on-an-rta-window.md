---
title: "期間には、RTA ウィンドウを取得する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- managing [BAM], time intervals
- Get-RTAWindow command [BAM]
ms.assetid: 4e7ad0fd-e7ed-47f7-9435-ef01bbe17afa
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb930c3e9d252a23653f0464e1adaa1e18b4f45
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-get-the-duration-on-an-rta-window"></a>RTA 時間帯の期間を取得する方法
管理者を使用して、 **rtawindow プロパティの get**コマンドを指定されたリアルタイム集計 (RTA) の実行時間を取得します。 このコマンドにより、期間の長さと、その期間の基準となる単位が返されます。  
  
### <a name="to-get-the-duration-on-an-aggregation"></a>集計の期間を取得するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking フォルダーに移動します。  
  
3.  型**bm get rtawindow-ビュー:\<ビュー名 >-アクティビティ:\<アクティビティ名 > -Rta:\<RTA 名 >**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [RTA 時間帯の期間を設定する方法](../core/how-to-set-the-duration-on-an-rta-window.md)