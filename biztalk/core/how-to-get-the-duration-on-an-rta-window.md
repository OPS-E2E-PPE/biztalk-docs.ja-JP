---
title: 期間が RTA ウィンドウを取得する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [BAM], aggregations
- aggregations [BAM], time intervals
- managing [BAM], time intervals
- Get-RTAWindow command [BAM]
ms.assetid: 4e7ad0fd-e7ed-47f7-9435-ef01bbe17afa
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4b69ccb37e1104f78515e2974fc9ff791b45c39
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385019"
---
# <a name="how-to-get-the-duration-on-an-rta-window"></a>期間が RTA ウィンドウを取得する方法
管理者を使用して、 **rtawindow プロパティの get**コマンドを指定されたリアルタイム集計 (RTA) の実行時間を取得します。 コマンドは、期間と期間の測定単位の長さを返します。  
  
### <a name="to-get-the-duration-on-an-aggregation"></a>集計の期間を取得するには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. フォルダーに移動[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]追跡します。  
  
3. 型**bm get-rtawindow プロパティの表示:\<ビュー名\>-アクティビティ:\<アクティビティ名\>Rta:\<RTA 名\>**。  
  
   > [!NOTE]
   >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [RTA ウィンドウの期間を設定する方法](../core/how-to-set-the-duration-on-an-rta-window.md)