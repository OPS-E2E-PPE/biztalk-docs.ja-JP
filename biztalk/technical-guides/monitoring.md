---
title: "監視 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7effa38f-f9f2-40b7-8d8b-fa13cf94aa4f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c45bb70e3f92f4c85def07add4390a0451cb87
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring"></a>監視
既定では、すべての BizTalk Server の監視およびタスクを使用して既定のアクション アカウントが、実行プロファイルで、BizTalk Server 監視アカウントのターゲットの特定の実行アカウントが定義されていない場合。 実行アカウントを BizTalk Server を監視するために必要なアクセス許可の最小セットを構成するのには、次のアクセス許可が必要です。  
  
-   アカウントは、監視対象のコンピューターの組み込みの Administrators グループとパフォーマンス モニターのユーザー グループのメンバーである必要があります。  
  
-   アカウントは、SQL インスタンスまたはデータベースとジョブが監視されている BizTalk グループをホストしているインスタンス内の SysAdmin ロールのメンバーである必要があります。  
  
-   BizTalk Server が監視するため、アカウントは、BizTalk Operators グループの一部をする必要があります。  
  
-   を、SCOM コンソールのタスクを実行するため、アカウントは、BizTalk Application Users グループの一部をする必要があります。  
  
-   管理タスクを実行するため、アカウントは、BizTalk 管理者グループの一部にする必要があります。