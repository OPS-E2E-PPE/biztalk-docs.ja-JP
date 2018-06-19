---
title: 中断、再開、およびオーケストレーションのインスタンスを終了する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], resuming
- orchestrations, terminating
- managing [orchestrations], suspending
- orchestrations, resuming
- orchestrations, suspending
- managing [orchestrations], terminating
ms.assetid: 7b373dad-57d5-4696-9b29-a6c351d44fa8
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9528ac0e810a3d4e203733ab1cc5b041d3d61d31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256770"
---
# <a name="how-to-suspend-resume-and-terminate-orchestration-instances"></a>オーケストレーション インスタンスを中断、再開、および終了する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、実行中の 1 つ以上のオーケストレーションのサービス インスタンスを中断、再開、および終了する方法について説明します。 サービスのインスタンスとは、後続の処理や追跡を目的に BizTalk Server が処理しているオーケストレーションのインスタンス、または、メッセージ ボックスにシリアル化されたオーケストレーションのインスタンスを指します。  
  
 以下に、これら 3 つの操作の効果について説明します。  
  
-   **中断します。** サービス インスタンスを一時停止します。 インプロセス メッセージは最後まで実行されます。 メッセージは依然として回送されますが、処理されません。  
  
-   **再開します。** 中断したインスタンスの処理を再開します。  
  
> [!NOTE]
>  ブレークポイント状態のインスタンスは再開できません。 このようなインスタンスを再開すると、"保留中" という状態が表示されることがあります。ただし、このインスタンスは最終的に失敗します。  
  
-   **終了します。** メッセージ処理をすべて終了します。 サービス インスタンスは、BizTalk Server データベースから削除されます。 サービス インスタンスが処理しているメッセージも削除されます。ただし、終了しないサービス インスタンスによって参照されているメッセージは削除されません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-view-start-stop-or-terminate-an-instance-of-an-orchestration"></a>オーケストレーションのインスタンスを開始、停止、または終了するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  [グループ ハブ] ページを表示する BizTalk グループを選択します。  
  
3.  **進行中の作業**をクリックして**サービス インスタンスを実行している**です。  
  
     ページ下部のクエリ結果パネルに、オーケストレーションのすべてのインスタンスが表示されます。  
  
4.  オーケストレーションの別のインスタンスを表示して、クエリを絞り込んでするには、下にあるボックスをクリックして**値**の**Search For**フィールドで、表示、およびをクリックするインスタンスの種類を選択**クエリの実行**. クエリの作成の詳細については、「関連項目」で検索に関するトピックを選んで参照してください。  
  
5.  をクリックして、インスタンスを右クリックして**Suspend**、**再開**、または**Terminate**です。 この機能を使用すると、再開するインスタンスを選択できます。  
  
    > [!NOTE]
    >  複数のインスタンスに対して操作を実行するには、CTRL キーを押しながら目的のインスタンスをクリックします。 インスタンスを右クリックし、をクリックし、 **Suspend**、**再開**、または**Terminate**です。  
  
     [サービス インスタンスの状態](../core/service-instance-states.md)中断状態について詳しく説明します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md)   
 [中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md)