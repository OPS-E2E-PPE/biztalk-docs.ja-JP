---
title: アラートを無効にする方法 |Microsoft Docs
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
ms.openlocfilehash: c9666c6db97a181a3ff4c3ada204fe11b2b99c8a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385193"
---
# <a name="how-to-disable-alerts"></a>警告を無効にする方法
管理者を使用して、**無効にするアラート**コマンドは、指定されたビューにアラートをすべて無効にします。  
  
### <a name="to-disable-an-alert"></a>アラートを無効にするには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3. 型**bm の無効にするアラートの表示:\<ビュー名\>** します。  
  
   > [!NOTE]
   >  BAM 構成を XML としてエクスポートしている場合は、アラートに関連する XML を変更しないでください。 アラートに関連する XML を変更し、変更を配置する場合、bm.exe は変更が検出され、BAM 警告を有効にします。  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [アラートを有効にする方法](../core/how-to-enable-alerts.md)