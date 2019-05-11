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
ms.openlocfilehash: 5e59442920c83b55e79692716ef5f5a447efd716
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333835"
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを終了する方法
すべて中断したオーケストレーション インスタンスまたはクエリ結果ペインまたはプレビュー ペインで、BizTalk Server 管理コンソールからのポートを終了することができます。  
  
> [!NOTE]
>  順次配送送信ポートの各インスタンスは、関連付けられているいくつかのメッセージがあります。 誤終了やデータの損失を防ぐためには、必ず、インスタンスを終了する前にこのようなすべての関連付けを確認ください。  
  
## <a name="prerequisites"></a>前提条件  
 この手順を実行する BizTalk Server Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-terminate-suspended-orchestration-instances"></a>中断したオーケストレーション インスタンスを終了するには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、し、[BizTalk グループ] をクリックします。  
  
3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  
  
4. **クエリ式**グループに、**値**列で、**中断サービス インスタンスの**ドロップダウン リスト ボックスから。  
  
5. 次のいずれかの操作を行います。  
  
   - 1 つのインスタンスを終了する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択、**のサービス名</em>* フィルターし、**値**列で、サービス名を指定します。  
  
   - インスタンスをまとめてを終了する、**フィールド名**アスタリスクの横にある空のドロップダウン リスト ボックス内の列 (**\\**<em>) を選択します **でのグループの結果</em>* し、**値**列で、サービス名を指定します。  
  
6. クリックして**クエリを実行**します。  
  
7. クエリ結果リストで、オーケストレーション インスタンスまたはグループのインスタンスを終了し、をクリックするを右クリックして**インスタンスの終了**または**インスタンスを終了**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)