---
title: 追跡メッセージ イベントを検索する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18df4cf7-c307-4175-926c-9be9f30b29ed
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6a3597d0d68dbd79de6c23e7b6d4b222b9c8376
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-tracked-message-events"></a>追跡メッセージ イベントを検索する方法
使用することができます、**新しいクエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]追跡メッセージ イベントの管理コンソールを検索します。  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールから、メッセージ本文とメッセージ プロパティの追跡を有効にすることができます。 クエリ結果ペインで、メッセージ イベントに関する情報を表示できます。表示内容には、スキーマ情報、イベントの種類、サービス インスタンス ID、および生成されたメッセージの昇格させたすべてのプロパティが含まれます。  
  
> [!NOTE]
>  実際のメッセージ本文を表示するために呼び出すことができます、 **メッセージの詳細** コンテキスト メニューのおよび移動メッセージ部分 タブをクリックするか、またはメッセージを保存結果のリストから呼び出すことによって表示 **をファイルに保存** 、コンテキスト メニューからです。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-search-for-tracked-message-items"></a>追跡対象のメッセージ項目を検索するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**, 、し、BizTalk グループ をクリックします。  
  
3.  詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。  
  
4.  **クエリ式** グループの **値** 列で、選択 **追跡メッセージ イベント** ドロップダウン リスト ボックスからです。  
  
5.  **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。  
  
    |アイテム|Description|  
    |----------|-----------------|  
    |**作成日時**|メッセージが作成された時刻。|  
    |**イベントの種類**|追跡対象のイベントの種類。|  
    |**最大一致数**|一致項目の表示数を指定します。|  
    |**パーティ**|メッセージを送信した組織。|  
    |**ポート**|メッセージの処理に使用されるポート。|  
    |**スキーマ名**|メッセージで使用されているスキーマの名前。|  
    |**サービス インスタンス ID**|メッセージに使用されているサービス インスタンス ID。|  
    |**URI**|メッセージに使用されている URI。|  
    |**\<追跡対象のプロパティのスキーマ名を選択します。\>**|スキーマを選択すると、そのスキーマ内の任意の昇格させたプロパティをクエリで使用できます。|  
  
6.  完了、 **値** 列に適切な選択範囲にすると、 **フィールド名** 列です。  
  
7.  完了することで、必要に応じてクエリに行を追加、 **フィールド名**, 、**演算子**, 、および **値** 列、およびクリック **クエリの実行**します。  
  
## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)