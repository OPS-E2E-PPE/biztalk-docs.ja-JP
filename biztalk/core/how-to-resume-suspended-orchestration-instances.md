---
title: 中断したオーケストレーション インスタンスを再開する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, resuming [HAT]
- HAT, resuming orchestrations
- HAT, resuming pipelines
- orchestrations, resuming
- resuming, pipelines
- resuming, orchestrations
- HAT, debug mode
ms.assetid: da133183-68d9-48d1-9601-8f6d4d5b8898
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f3243173f454d560515d1c3cbb9bef749fc17d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991171"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを再開する方法
"中断 (再開可能)" とマークされているオーケストレーション インスタンスを中断した場合は、クエリ結果ペインまたはプレビュー ペインからオーケストレーション インスタンスの再開を試行できます。 ただし、オーケストレーション インスタンスを正常に再開できるのは、中断の原因となった問題が修正済みの場合のみです。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-resume-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを再開するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、し、[BizTalk グループ] をクリックします。  
  
3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  
  
4. **クエリ式**グループに、**値**列で、**中断サービス インスタンスの**ドロップダウン リスト ボックスから。  
  
5. 次のいずれかの操作を行います。  
  
   - 1 つのインスタンスを再開する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択、**のサービス名</em>* フィルターし、**値**列で、サービス名を指定します。  
  
   - インスタンスをまとめてを再開する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択します **でのグループの結果</em>* し、**値**列で、サービス名を指定します。  
  
6. クリックして**クエリを実行**します。  
  
7. クエリ結果リストで、再開、およびクリックするオーケストレーション インスタンスを右クリックして**インスタンスの再開**または**インスタンスの再開**します。 これにより、再開するインスタンスを選択できます。  
  
    [サービス インスタンスの状態](../core/service-instance-states.md)詳細については、中断状態にします。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)
