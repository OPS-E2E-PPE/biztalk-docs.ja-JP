---
title: 追跡サービス インスタンスを検索する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b6337df9-8c2e-4d4a-a64b-cc040f83bd91
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1ff8801c272859e6a138fcb1e4e618226de10a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383978"
---
# <a name="how-to-search-for-tracked-service-instances"></a>追跡サービス インスタンスを検索する方法
使用することができます、**クエリ** タブで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールのすべての追跡サービス インスタンスを検索します。 サービス インスタンスを検索するには、サービス クラス、ホスト名、エラー コード、およびサービス インスタンスの状態の有効期間、名、またはインスタンス ID の開始および終了時刻、アセンブリのバージョンと名前で検索することができます。  

## <a name="prerequisites"></a>前提条件  
 この手順を実行する必要がありますがログオンしてのメンバーとして、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Operators グループ。  

### <a name="to-search-for-tracked-service-instances"></a>追跡サービス インスタンスを検索するには  

1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]します。  

2. コンソール ツリーで、展開**BizTalk Server 管理**、し、[BizTalk グループ] をクリックします。  

3. 詳細ウィンドウでをクリックして、**新しいクエリ**タブ。  

4. **クエリ式**グループに、**値**列で、**追跡サービス インスタンス**ドロップダウン リスト ボックスから。  

5. **フィールド名**列のアスタリスクの横にある空のドロップダウン リスト ボックスで、(* *\\* * *)、次の 1 つ以上選択します。  


   |          アイテム           |                     説明                      |
   |-------------------------|------------------------------------------------------|
   |    **アセンブリ名**    |    サービス インスタンスのアセンブリの名前。    |
   |  **アセンブリのバージョン**   |           サービス インスタンスのバージョンです。           |
   |      **[終了時刻]**       |          サービス インスタンスの終了時刻。           |
   |     **エラー コード**      | サービス インスタンスに関連付けられたエラー コード。 |
   |      **Host Name**      |        サービス インスタンスのホスト名。        |
   |   **最大一致数**   |          表示する一致の数。           |
   |    **サービス クラス**    |          サービス インスタンスのクラスです。          |
   | **サービス インスタンス ID** |               サービス インスタンス id。               |
   |    **[サービス名]**     |          サービス インスタンスの名前。           |
   |     **Start Time**      |       サービス インスタンスの開始時刻。        |
   |        **State**        |          サービス インスタンスの状態。          |


6. 完了、**値**で行った選択の適切な列、**フィールド名**列。  

7. 適切なクエリを実行して行を追加、**フィールド名**、**演算子**、および**値**列、およびクリック**実行クエリ**します。  

## <a name="see-also"></a>参照  
 [管理コンソールの [クエリ] タブの使用](../core/using-the-administration-console-query-tab.md)