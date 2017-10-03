---
title: "中断したオーケストレーション インスタンスを再開する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6696547ce3e918dc8d84b7cfcb4f24e31c8b70a0
ms.sourcegitcommit: 5355a25d120d094778fb8f68ea14cab55c68d292
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2017
---
# <a name="how-to-resume-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを再開する方法
"中断 (再開可能)" とマークされているオーケストレーション インスタンスを中断した場合は、クエリ結果ペインまたはプレビュー ペインからオーケストレーション インスタンスの再開を試行できます。 ただし、オーケストレーション インスタンスを正常に再開できるのは、中断の原因となった問題が修正済みの場合のみです。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-resume-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを再開するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、し、BizTalk グループ をクリックします。  
  
3.  詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。  
  
4.  **クエリ式**グループにおいて、**値**列で、選択**中断サービス インスタンスの**ドロップダウン リスト ボックスからです。  
  
5.  次のいずれかの操作を行います。  
  
    -   1 つのインスタンスを再開する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\***) を選択、**サービス名**フィルターと次に、**値**列で、サービス名を指定します。  
  
    -   インスタンスをまとめてを再開する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\***) を選択**結果をグループ化**し、**値**列で、サービス名を指定します。  
  
6.  をクリックして**クエリを実行**です。  
  
7.  クエリ結果リストで、再開、およびをクリックするオーケストレーション インスタンスを右クリックして**インスタンスの再開**または**インスタンスの再開**です。 これにより、再開するインスタンスを選択できます。  
  
     [サービス インスタンスの状態](../core/service-instance-states.md)について、中断状態にします。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)
