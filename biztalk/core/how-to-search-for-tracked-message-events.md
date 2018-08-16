---
title: 追跡メッセージ イベントを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a49ae9793c38746d965c75dc9da902cfe6b6da3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989291"
---
# <a name="how-to-search-for-tracked-message-events"></a>追跡メッセージ イベントを検索する方法
使用することができます、**新しいクエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡メッセージ イベントの管理コンソールを検索します。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、メッセージ本文とメッセージ プロパティの追跡を有効にすることができます。 クエリ結果ペインで、メッセージ イベントに関する情報を表示できます。表示内容には、スキーマ情報、イベントの種類、サービス インスタンス ID、および生成されたメッセージの昇格させたすべてのプロパティが含まれます。  

> [!NOTE]
>  実際のメッセージ本文を表示するために呼び出すことができます、**メッセージの詳細**コンテキスト メニューのおよび移動メッセージ部分 タブをクリックまたはメッセージを保存、結果の一覧から呼び出すことによって表示**ファイルに保存**から、コンテキスト メニュー。  

## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンする必要があります。  

### <a name="to-search-for-tracked-message-items"></a>追跡対象のメッセージ項目を検索するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。  

2. コンソール ツリーで、展開**BizTalk Server 管理**、し、[BizTalk グループ] をクリックします。  

3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  

4. **クエリ式**グループに、**値**列で、**追跡メッセージ イベント**ドロップダウン リスト ボックスから。  

5. **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(* *\\* * *)、次の 1 つ以上選択します。  


   |                        アイテム                         |                                              説明                                               |
   |-----------------------------------------------------|--------------------------------------------------------------------------------------------------------|
   |                  **作成時刻**                  |                                   メッセージが作成された時刻。                                    |
   |                   **イベントの種類**                    |                                    追跡対象のイベントの種類。                                    |
   |                 **最大一致数**                 |                                   一致項目の表示数を指定します。                                    |
   |                      **パーティ**                      |                                メッセージを送信した組織。                                 |
   |                      **[ポート]**                       |                                 メッセージの処理に使用されるポート。                                  |
   |                   **スキーマ名**                   |                                メッセージで使用されているスキーマの名前。                                 |
   |               **サービス インスタンス ID**               |                             メッセージに使用されているサービス インスタンス ID。                              |
   |                       **URI**                       |                                     メッセージに使用されている URI。                                      |
   | **\<追跡対象プロパティのスキーマ名を選択します。\>** | スキーマを選択すると、そのスキーマ内の任意の昇格させたプロパティをクエリで使用できます。 |


6. 完了、**値**で行った選択の適切な列、**フィールド名**列。  

7. 適切なクエリを実行して行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。  

## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)