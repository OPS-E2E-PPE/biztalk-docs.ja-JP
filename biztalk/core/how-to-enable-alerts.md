---
title: アラートを有効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enable-Alerts command [BAM]
- managing [BAM definitions], enabling alerts
- alerts, enabling
ms.assetid: 18f494b7-54fb-4aaf-89d1-7e3fe91f35c6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9986bea177471a236cab888f20d915292d540e5b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968824"
---
# <a name="how-to-enable-alerts"></a>警告を有効にする方法
管理者を使用して、**有効にするアラート**コマンドのすべての指定されたビューにアラートを有効にします。  
  
### <a name="to-enable-an-alert"></a>警告を有効にするには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3.  型**bm 有効にするアラートの表示:\<ビュー名\>** です。  
  
    > [!NOTE]
    >  BAM 構成を XML としてエクスポートした場合は、警告に関連した XML を変更しないでください。 警告に関連した XML を変更し、その変更を配置した場合、bm.exe によって変更が検出され、BAM 警告が有効になります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [ここにリンクの説明を入力する](../core/how-to-disable-alerts.md)