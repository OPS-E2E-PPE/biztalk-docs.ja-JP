---
title: 監視 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7effa38f-f9f2-40b7-8d8b-fa13cf94aa4f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8c7d6e8870d435163c83c053f981d42bad1858d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65249630"
---
# <a name="monitoring"></a>監視
既定では、すべての BizTalk Server の監視とタスクを使用して、既定のアクション アカウント実行プロファイルで BizTalk Server 監視アカウントのターゲットの特定の実行アカウントが定義されていないがある場合。 実行アカウントを BizTalk Server の監視のために必要なアクセス許可の最小セットで構成するには、次のアクセス許可が必要です。  
  
-   アカウントは、監視対象のコンピューターのビルトイン Administrators グループとパフォーマンス モニター ユーザー グループのメンバーである必要があります。  
  
-   アカウントは、SQL インスタンスまたはデータベースとジョブ監視されている BizTalk グループをホストしているインスタンス内で SysAdmin ロールのメンバーである必要があります。  
  
-   BizTalk Server を監視するため、アカウントは BizTalk Operators グループの一部である必要があります。  
  
-   SCOM コンソールからタスクを実行するため、アカウントは、BizTalk Application Users グループの一部をある必要があります。  
  
-   管理タスクを実行するには、アカウントは、BizTalk 管理者グループの一部をある必要があります。