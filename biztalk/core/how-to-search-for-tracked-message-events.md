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
ms.openlocfilehash: fabfa18a4dda37d1d2e59361d74b4ecc147a1703
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334793"
---
# <a name="how-to-search-for-tracked-message-events"></a>追跡メッセージ イベントを検索する方法
使用することができます、**新しいクエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡メッセージ イベントの管理コンソールを検索します。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのメッセージ本文とメッセージ プロパティの追跡を有効にすることができます。 クエリ結果ペインには、スキーマ情報、イベントの種類、サービス インスタンス ID に、生成されたメッセージのすべての昇格させたプロパティなど、メッセージ イベントに関する情報を表示できます。  

> [!NOTE]
>  実際のメッセージ本文を表示するために呼び出すことができます、**メッセージの詳細**コンテキスト メニューのおよび移動メッセージ部分 タブをクリックまたはメッセージを保存、結果の一覧から呼び出すことによって表示**ファイルに保存**から、コンテキスト メニュー。  

## <a name="prerequisites"></a>前提条件  
 この手順を実行する必要がありますがログオンしてのメンバーとして、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループ。  

### <a name="to-search-for-tracked-message-items"></a>追跡メッセージの項目を検索するには  

1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。  

2. コンソール ツリーで、展開**BizTalk Server 管理**、し、[BizTalk グループ] をクリックします。  

3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  

4. **クエリ式**グループに、**値**列で、**追跡メッセージ イベント**ドロップダウン リスト ボックスから。  

5. **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(* *\\* * *)、次の 1 つ以上選択します。  


   |                        アイテム                         |                                              説明                                               |
   |-----------------------------------------------------|--------------------------------------------------------------------------------------------------------|
   |                  **作成時刻**                  |                                   メッセージが作成された時刻。                                    |
   |                   **イベントの種類**                    |                                    追跡対象のイベントの種類。                                    |
   |                 **最大一致数**                 |                                   表示する一致の数。                                    |
   |                      **パーティ**                      |                                メッセージを送信した組織です。                                 |
   |                      **[ポート]**                       |                                 メッセージの処理に使用されるポート。                                  |
   |                   **スキーマ名**                   |                                メッセージで使用されるスキーマの名前です。                                 |
   |               **サービス インスタンス ID**               |                             メッセージで使用するサービス インスタンスの ID。                              |
   |                       **URI**                       |                                     メッセージで使用する URI。                                      |
   | **\<追跡対象プロパティのスキーマ名を選択します。\>** | スキーマを選択するときにそのスキーマで昇格させたプロパティは、クエリで使用可能なです。 |


6. 完了、**値**で行った選択の適切な列、**フィールド名**列。  

7. 適切なクエリを実行して行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。  

## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)