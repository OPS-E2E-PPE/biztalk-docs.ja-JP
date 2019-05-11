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
ms.openlocfilehash: 9e5e712f0ec845c4f895833908954711cdce0698
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334904"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを再開する方法
「中断された再開可能な」と記載されているオーケストレーション インスタンスを中断した場合、クエリ結果ペインまたはプレビュー ペインからオーケストレーション インスタンスを再開しようとすることができます。 オーケストレーション インスタンスの再開と中断状態になり、オーケストレーション インスタンスの原因となった、基になる問題が修正済みの場合のみ成功します。  
  
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
  
7. クエリ結果リストで、再開、およびクリックするオーケストレーション インスタンスを右クリックして**インスタンスの再開**または**インスタンスの再開**します。 これにより、再開するインスタンスを選択することができます。  
  
    [サービス インスタンスの状態](../core/service-instance-states.md)詳細については、中断状態にします。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)
