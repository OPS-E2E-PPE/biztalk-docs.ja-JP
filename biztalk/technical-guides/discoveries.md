---
title: "検出 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5350c4b3-ecc5-487e-a75a-16af090ffa06
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 848bf4c2841462adecec749c1254eb9c273e1f31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="discoveries"></a>検出
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、一元的な管理および BizTalk Server 関連のアーティファクトのエクスペリエンスの監視を提供します。  
  
## <a name="discovery-of-artifacts"></a>成果物の検出  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、監視エージェントが 1 つのランタイム コンピューターから成果物を検出します。 既定では、管理パックでは、BizTalk グループに参加している最初のコンピューター上のアイテムを検出します。 ただし、任意のコンピューター上のアイテムが検出を計画する場合は、自動検出の設定を変更する上書き機能を使用する必要があります。 上書きを使用して、自動検出の設定を変更する、次を参照してください。[オプションの構成](../technical-guides/optional-configurations.md)です。  
  
 SCOM オペレーション コンソールから実行されるタスクと操作は、成果物が検出され、すべてのランタイム コンピューターで監視に固有です。 BizTalk Server 管理パックはすべてのタスクを表示するクリックして**タスク**Operations Manager 2007 R2 または 2012 オペレーション コンソールの [監視] ウィンドウでします。