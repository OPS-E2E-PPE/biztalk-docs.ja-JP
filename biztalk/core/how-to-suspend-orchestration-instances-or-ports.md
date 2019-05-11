---
title: オーケストレーションのインスタンスまたはポートを停止する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, suspending
- instances, suspending
- suspending
- HAT, suspending orchestrations
- HAT, suspending pipelines
- suspending, ports
- suspending, orchestrations
- orchestrations, suspending
- HAT, suspending ports
- suspending, instances
- ports, suspending
ms.assetid: cacc7e58-7d3e-4d6b-adb0-618fdc4f0d89
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6203a0ad7cdcafc570e692d1a5345c86b23cdf91
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383746"
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a>オーケストレーションのインスタンスまたはポートを中断する方法
BizTalk Server 管理コンソールでオーケストレーションのインスタンスまたはクエリ結果の一覧からポートを中断することができます。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a>オーケストレーションのインスタンスまたはポートを中断するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、し、[BizTalk グループ] をクリックします。  
  
3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  
  
4. **クエリ式**グループに、**値**列で、**サービス インスタンスを実行している**ドロップダウン リスト ボックスから。  
  
5. 次のいずれかの操作を行います。  
  
   - 1 つのインスタンスを中断する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択、**のサービス名</em>* フィルターし、**値**列で、サービス名を指定します。  
  
   - インスタンスをまとめてを中断する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択します **でのグループの結果</em>* し、**値**列で、サービス名を指定します。  
  
6. クリックして**クエリを実行**します。  
  
7. クエリ結果の一覧で、中断、 をクリックして、アクティブなオーケストレーションまたはポートを右クリックして**インスタンスの中断**または**インスタンスの中断**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)