---
title: 追跡対象サービス インスタンスを検索する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08e5a7fa563e175d6a1d784e546bd399e20d3c21
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-search-for-tracked-service-instances"></a>追跡対象サービス インスタンスを検索する方法
使用することができます、**クエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのすべての追跡対象サービス インスタンスを検索します。 サービス インスタンスを検索するには、アセンブリの名前とバージョン、有効期間の開始時刻と終了時刻、サービス クラスの名前またはインスタンス ID、ホスト名、エラー コード、サービス インスタンスの状態に基づいて検索できます。  
  
## <a name="prerequisites"></a>前提条件  
 ここで示す手順を実行するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループのメンバーとしてログオンする必要があります。  
  
### <a name="to-search-for-tracked-service-instances"></a>追跡対象サービス インスタンスを検索するには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**, 、し、BizTalk グループ をクリックします。  
  
3.  詳細ペインでクリックして、 **新しいクエリ**  タブをクリックします。  
  
4.  **クエリ式** グループの **値** 列で、選択 **追跡サービス インスタンス** ドロップダウン リスト ボックスからです。  
  
5.  **フィールド名** 列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(**\***)、次の 1 つ以上選択します。  
  
    |アイテム|Description|  
    |----------|-----------------|  
    |**アセンブリ名**|サービス インスタンスのアセンブリの名前。|  
    |**アセンブリのバージョン**|サービス インスタンスのバージョン。|  
    |**終了時刻**|サービス インスタンスの終了時刻。|  
    |**エラー コード**|サービス インスタンスに関連付けられているエラー コード。|  
    |**ホスト名**|サービス インスタンスのホスト名。|  
    |**最大一致数**|一致項目の表示数を指定します。|  
    |**サービス クラス**|サービス インスタンスのクラス。|  
    |**サービス インスタンス ID**|サービス インスタンス ID。|  
    |**サービス名**|サービス インスタンスの名前。|  
    |**開始時刻**|サービス インスタンスの開始時刻。|  
    |**状態**|サービス インスタンスの状態。|  
  
6.  完了、 **値** 列に適切な選択範囲にすると、 **フィールド名** 列です。  
  
7.  完了することで、必要に応じてクエリに行を追加、 **フィールド名**, 、**演算子**, 、および **値** 列、およびクリック **クエリの実行**します。  
  
## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)