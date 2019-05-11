---
title: 検出 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5350c4b3-ecc5-487e-a75a-16af090ffa06
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48eb4faf03dddb50122011a20349578ef6ab64c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305695"
---
# <a name="discoveries"></a>検出
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]一元的な管理と BizTalk Server に関連する成果物のエクスペリエンスの監視管理パックを提供します。  
  
## <a name="discovery-of-artifacts"></a>成果物の検出  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理パックは、監視エージェントが 1 つのランタイム コンピューターから成果物を検出します。 既定では、管理パックは、BizTalk グループに参加している最初のコンピューター上のアイテムを検出します。 ただし、任意のコンピューター上のアイテムを検出する場合は、自動検出の設定を変更する上書き機能を使用する必要があります。 自動検出の設定を変更する上書きを使用して、次を参照してください。[オプションの構成](../technical-guides/optional-configurations.md)します。  
  
 アクションと SCOM のオペレーション コンソールから実行されるタスク、成果物が探索され、ランタイムのすべてのマシンの監視に固有です。 BizTalk Server 管理パックは、すべてのタスクを表示するには、次のようにクリックします。**タスク**  /2012 R2 の Operations Manager 2007 オペレーション コンソールの [監視] ウィンドウでします。