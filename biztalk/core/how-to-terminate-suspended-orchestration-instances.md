---
title: "中断したオーケストレーション インスタンスを終了する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc0160be5aeeef43b9595953893b4ea1af82c62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを終了する方法
中断したオーケストレーション インスタンスまたはポートは、BizTalk Server 管理コンソールのクエリ結果ペインまたはプレビュー ペインから終了できます。  
  
> [!NOTE]
>  順次配送の送信ポートの各インスタンスは、関連付けられているいくつかのメッセージがあります。 誤終了やデータ損失を防ぐために、インスタンスを終了する前にこのような関連付けをすべて確認してください。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-terminate-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを終了するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。  
  
3.  詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。  
  
4.  **クエリ式**グループにおいて、**値**列で、選択**中断サービス インスタンスの**ドロップダウン リスト ボックスからです。  
  
5.  次のいずれかの操作を行います。  
  
    -   1 つのインスタンスを終了する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\***) を選択、**サービス名**フィルター**値**列で、サービス名を指定します。  
  
    -   インスタンスをまとめてを終了する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\***) を選択**結果をグループ化**し、**値**列で、サービス名を指定します。  
  
6.  をクリックして**クエリを実行**です。  
  
7.  クエリ結果リストで、オーケストレーション インスタンスまたはグループのインスタンスを終了して、をクリックするを右クリックして**インスタンスの終了**または**インスタンスを終了**です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)