---
title: アラートを有効にする方法 |Microsoft Docs
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
ms.openlocfilehash: 75242921113152b45c17f139c24a4afc87ac7451
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338002"
---
# <a name="how-to-enable-alerts"></a>警告を有効にする方法
管理者を使用して、**有効にするアラート**コマンドを指定されたビューにアラートをすべて有効にします。  
  
### <a name="to-enable-an-alert"></a>アラートを有効にするには  
  
1. 次のように、コマンド プロンプトを開きます。をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリックします**OK**。  
  
2. コマンド プロンプトで「[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking」と入力して、追跡フォルダーに移動し、 **Enter**キーを押します。  
  
3. 型**bm 有効にするアラートの表示:\<ビュー名\>** します。  
  
   > [!NOTE]
   >  BAM 構成を XML としてエクスポートしている場合は、アラートに関連する XML を変更しないでください。 アラートに関連する XML を変更し、変更を配置する場合、bm.exe は変更が検出され、BAM 警告を有効にします。  
  
4. **Enter**キーを押します。  
  
## <a name="see-also"></a>参照  
 [BAM 動的インフラストラクチャの管理](../core/managing-the-bam-dynamic-infrastructure.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [ここにリンクの説明を入力する](../core/how-to-disable-alerts.md)