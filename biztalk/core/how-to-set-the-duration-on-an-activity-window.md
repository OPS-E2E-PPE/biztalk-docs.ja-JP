---
title: アクティビティ ウィンドウの期間を設定する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Set-ActivityWindow command [BAM]
- activities [BAM], time intervals
- managing [BAM], time intervals
ms.assetid: e39c315e-f215-4f81-9774-cf7aedf6ba33
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c7bab9fe9c5969bf4f5d277b83b63f751e6afc9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334227"
---
# <a name="how-to-set-the-duration-on-an-activity-window"></a>アクティビティ ウィンドウの期間を設定する方法
管理者を使用して、**セット activitywindow**指定されたアクティビティの期間を設定するコマンド。  
  
### <a name="to-set-the-duration-on-an-activity"></a>アクティビティの期間を設定するには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3. 型**bm セット-activitywindow-アクティビティ:\<アクティビティ名\>- TimeLength:\<整数\>- TimeUnit: 月&#124;日&#124;時間&#124;分**します。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [アクティビティ ウィンドウの期間を取得する方法](../core/how-to-get-the-duration-on-an-activity-window.md)