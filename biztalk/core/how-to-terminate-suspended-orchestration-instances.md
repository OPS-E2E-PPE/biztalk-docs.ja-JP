---
title: 中断したオーケストレーション インスタンスを終了する方法 |Microsoft ドキュメント
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
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc0160be5aeeef43b9595953893b4ea1af82c62
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを終了する方法
中断したオーケストレーション インスタンスまたはポートは、BizTalk Server 管理コンソールのクエリ結果ペインまたはプレビュー ペインから終了できます。  
  
> [!NOTE]
>  順次配送送信ポートの各インスタンスは、関連付けられているいくつかのメッセージがあります。 誤終了やデータ損失を防ぐために、インスタンスを終了する前にこのような関連付けをすべて確認してください。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-terminate-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを終了するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] を展開し、[BizTalk グループ] をクリックします。  
  
3.  詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。  
  
4.  **クエリ式** グループの **値** 列で、選択 **サービス インスタンスの中断されたインスタンス** ドロップダウン リスト ボックスからです。  
  
5.  次のいずれかの操作を行います。  
  
    -   単一のインスタンスを終了する、 **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***) を選択、 **サービス名** フィルターし、次に、 **値**  列で、サービス名を指定します。  
  
    -   インスタンスをまとめてを終了する、 **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、[ **結果をグループ化** し、次に、 **値** ] 列で、サービス名を指定します。  
  
6.  クリックして **クエリを実行**します。  
  
7.  クエリ結果の一覧で、オーケストレーション インスタンスまたはクリックして、終了するインスタンスのグループを右クリックして **インスタンスの終了** または **インスタンスを終了**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)