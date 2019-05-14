---
title: 中断、再開、およびオーケストレーションのインスタンスを終了する方法 |Microsoft Docs
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
ms.openlocfilehash: 7ede4f048f8dd95fe052774c3e3f621133ce8e99
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333873"
---
# <a name="how-to-suspend-resume-and-terminate-orchestration-instances"></a>中断、再開、およびオーケストレーションのインスタンスを終了する方法
このトピックでは、中断、再開、および 1 つまたは複数を終了する方法を説明します。 BizTalk Server 管理コンソールを使用して、オーケストレーションのサービス インスタンスを実行します。 サービス インスタンスは、インスタンスに後続の処理または追跡用のメッセージ ボックスの処理またはを BizTalk サーバーがあるオーケストレーションのシリアル化されました。  
  
 次に、これら 3 つの操作の効果について説明します。  
  
-   **中断します。** これには、サービス インスタンスが一時停止します。 メッセージの処理では、完了するまで実行します。 メッセージは、サービスのインスタンスにまだルーティングされますは処理されません。  
  
-   **再開します。** 中断されたインスタンスの処理を再開します。  
  
> [!NOTE]
>  ブレークポイントの状態からインスタンスを再開することはできません。 「保留中」の状態を表示するこのようなインスタンスを再開することがありますが、インスタンスが最終的に失敗します。  
  
-   **終了します。** これには、すべてのメッセージ処理が終了します。 サービス インスタンスは、BizTalk Server データベースから削除されます。 サービス インスタンスが処理されているメッセージも削除も終了しないサービス インスタンスによって参照されるすべてのメッセージを除く。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server Operators グループまたは BizTalk Server 管理者グループのメンバーとしてログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-view-start-stop-or-terminate-an-instance-of-an-orchestration"></a>表示するには開始を停止、またはオーケストレーションのインスタンスを終了  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. グループ ハブ ページを表示する BizTalk グループを選択します。  
  
3. [**進行中の作業**、] をクリックして**サービス インスタンスを実行している**します。  
  
    ページの下部に、クエリ結果 パネルには、オーケストレーションのすべてのインスタンスが表示されます。  
  
4. クエリを変更して、オーケストレーションの別のインスタンスを表示、下にあるボックスをクリックします**値**の、**検索の**フィールドで、表示する をクリックし、インスタンスの種類を選択します。**クエリの実行。**. クエリの作成に関する詳細については、参照の検索のトピックを参照してください。  
  
5. をクリックしてインスタンスを右クリックして**Suspend**、**再開**、または**Terminate**します。 この機能を再開するインスタンスを選択することができます。  
  
   > [!NOTE]
   >  複数のインスタンスで操作を実行するには、CTRL キーを押しながらし、目的のインスタンスをクリックします。 次にインスタンスを右クリックし、をクリックして**Suspend**、**再開**、または**Terminate**します。  
  
    [サービス インスタンスの状態](../core/service-instance-states.md)中断状態について詳しく説明します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [実行中のサービス インスタンスを検索する方法](../core/how-to-search-for-running-service-instances.md)   
 [中断されたサービス インスタンスを検索する方法](../core/how-to-search-for-suspended-service-instances.md)