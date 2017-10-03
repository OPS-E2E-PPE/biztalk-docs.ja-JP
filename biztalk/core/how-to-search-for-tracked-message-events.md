---
title: "追跡メッセージ イベントを検索する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3d4c573b864d16362c1b12b1e293e85f139cad4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-search-for-tracked-message-events"></a>追跡メッセージ イベントを検索する方法
使用することができます、**新しいクエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡メッセージ イベントの管理コンソールを検索します。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、メッセージ本文とメッセージ プロパティの追跡を有効にすることができます。 クエリ結果ペインで、メッセージ イベントに関する情報を表示できます。表示内容には、スキーマ情報、イベントの種類、サービス インスタンス ID、および生成されたメッセージの昇格させたすべてのプロパティが含まれます。  
  
> [!NOTE]
>  実際のメッセージ本文を表示するために呼び出すことができます、**メッセージの詳細**コンテキスト メニューおよび移動"メッセージ部分 タブをクリックするか、またはメッセージを保存、結果の一覧から呼び出すことによって表示**をファイルに保存**から、コンテキスト メニュー。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-search-for-tracked-message-items"></a>追跡対象のメッセージ項目を検索するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、し、BizTalk グループ をクリックします。  
  
3.  詳細ウィンドウで、をクリックして、**新しいクエリ**タブです。  
  
4.  **クエリ式**グループにおいて、**値**列で、選択**追跡メッセージ イベント**ドロップダウン リスト ボックスからです。  
  
5.  **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。  
  
    |アイテム|Description|  
    |----------|-----------------|  
    |**作成日時**|メッセージが作成された時刻。|  
    |**イベントの種類**|追跡対象のイベントの種類。|  
    |**最大一致数**|一致項目の表示数を指定します。|  
    |**パーティ**|メッセージを送信した組織。|  
    |**[ポート]**|メッセージの処理に使用されるポート。|  
    |**スキーマ名**|メッセージで使用されているスキーマの名前。|  
    |**サービス インスタンス ID**|メッセージに使用されているサービス インスタンス ID。|  
    |**URI**|メッセージに使用されている URI。|  
    |**\<追跡対象のプロパティのスキーマ名を選択 >**|スキーマを選択すると、そのスキーマ内の任意の昇格させたプロパティをクエリで使用できます。|  
  
6.  完了、**値**で行う選択範囲の適切な列、**フィールド名**列です。  
  
7.  実行して適切なクエリに行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**です。  
  
## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブを使用します。](../core/using-the-administration-console-query-tab.md)