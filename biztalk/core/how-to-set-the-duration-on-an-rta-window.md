---
title: "RTA 時間帯の期間を設定する方法 |Microsoft ドキュメント"
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
- Set-RTAWindow command [BAM]
- managing [BAM], time intervals
ms.assetid: 3042c3f5-be0f-48fb-9831-daa4868b90fe
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09a1b9e0514a2c83d927a956bb890c1a89864a07
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-the-duration-on-an-rta-window"></a>特定の RTA 時間帯の期間を設定する方法
管理者を使用して、**セット rtawindow**コマンドを指定されたリアルタイム集計 (RTA) の期間を設定します。  
  
### <a name="to-set-the-duration-on-an-aggregation"></a>集計の期間を設定するには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3.  型**bm セット rtawindow-ビュー:\<ビュー名 >-アクティビティ:\<アクティビティ名 >-名前:\<RTA 名 > - TimeLength:\<整数の番号 > - TimeUnit: 日 & #124 です。1 時間 & #124 です。分**です。  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [期間には、RTA ウィンドウを取得する方法](../core/how-to-get-the-duration-on-an-rta-window.md)