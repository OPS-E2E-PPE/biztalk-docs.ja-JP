---
title: アラートを無効にする方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- alerts, disabling
- managing [BAM definitions], disabling alerts
- Disable-Alerts command [BAM]
ms.assetid: c5938bc2-1043-4633-8cad-02caf442f2e8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4279030b9c3bcc7913bf64cc870b0d82d618dff8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969264"
---
# <a name="how-to-disable-alerts"></a>警告を無効にする方法
管理者を使用して、**無効にするアラート**のすべての指定されたビューにアラートを無効にするコマンド。  
  
### <a name="to-disable-an-alert"></a>警告を無効にするには  
  
1.  次のように、コマンド プロンプトを開きます: をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3.  型**bm 無効にするアラートの表示:\<ビュー名\>** です。  
  
    > [!NOTE]
    >  BAM 構成を XML としてエクスポートした場合は、警告に関連した XML を変更しないでください。 警告に関連した XML を変更し、その変更を配置した場合、bm.exe によって変更が検出され、BAM 警告が有効になります。  
  
4.  **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [アラートを有効にする方法](../core/how-to-enable-alerts.md)