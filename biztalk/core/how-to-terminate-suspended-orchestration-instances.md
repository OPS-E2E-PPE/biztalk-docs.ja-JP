---
title: 中断したオーケストレーション インスタンスを終了する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37de5e1153e9d361b76900ca206351e8b9549dc3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991971"
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを終了する方法
中断したオーケストレーション インスタンスまたはポートは、BizTalk Server 管理コンソールのクエリ結果ペインまたはプレビュー ペインから終了できます。  
  
> [!NOTE]
>  順次配送送信ポートの各インスタンスは、関連付けられているいくつかのメッセージがあります。 誤終了やデータ損失を防ぐために、インスタンスを終了する前にこのような関連付けをすべて確認してください。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-terminate-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを終了するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。  
  
3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  
  
4. **クエリ式**グループに、**値**列で、**中断サービス インスタンスの**ドロップダウン リスト ボックスから。  
  
5. 次のいずれかの操作を行います。  
  
   - 1 つのインスタンスを終了する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択、**のサービス名</em>* フィルターし、**値**列で、サービス名を指定します。  
  
   - インスタンスをまとめてを終了する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択します **でのグループの結果</em>* し、**値**列で、サービス名を指定します。  
  
6. クリックして**クエリを実行**します。  
  
7. クエリ結果リストで、オーケストレーション インスタンスまたはグループのインスタンスを終了し、をクリックするを右クリックして**インスタンスの終了**または**インスタンスを終了**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)