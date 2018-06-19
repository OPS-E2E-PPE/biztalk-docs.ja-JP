---
title: オーケストレーションを参加させる方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], enlisting
- orchestrations, enlisting
- enlisting, orchestrations
ms.assetid: b21a398b-8c9a-42ae-aac0-de35dbfd8176
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f58cb697e270052f8f42229997b1125e808816b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255842"
---
# <a name="how-to-enlist-an-orchestration"></a>オーケストレーションを参加させる方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションをホストに参加させる方法について説明します。 オーケストレーションは参加させて初めて開始できるようになります。  
  
 オーケストレーションを参加させる際は、次の点に注意してください。  
  
-   **参加させる前に、オーケストレーションをバインドする必要があります。** オーケストレーションのバインドの構成方法の詳細については、次を参照してください。[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)です。  
  
-   **サブスクリプションは自動的に作成されます。** オーケストレーションの参加プロセスを経て、必要なサブスクリプションがメッセージ ボックス データベースに作成されます。  
  
-   **アプリケーションをインストールする必要があります。** オーケストレーションを実行するすべてのコンピューターに、そのオーケストレーションが含まれているアプリケーションをインストールする必要があります。 詳細については、次を参照してください。[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。  
  
-   **呼び出し元のオーケストレーションは、呼び出し先オーケストレーションと同じホストにバインドする必要があります。** 呼び出し元オーケストレーションは、呼び出し先オーケストレーションと同じホストにバインドする必要があります。  
  
-   **依存オーケストレーションを登録する必要があります。** オーケストレーションを参加させるとき、依存オーケストレーションがあれば、それらも一緒に参加させないと、依存オーケストレーションにサブスクリプションが割り当てられません。 依存オーケストレーションにサブスクリプションがないと、メッセージに対応するサブスクリプションが存在しないため、メッセージが削除または保留される可能性があります。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にオーケストレーションを参加させてその機能をテストするには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-enlist-an-orchestration"></a>オーケストレーションを参加させるには  
  
1.  をクリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、参加させるオーケストレーションを含むアプリケーションを展開します。  
  
3.  をクリックして**オーケストレーション**、参加させ、をクリックしてオーケストレーションを右クリックして**Enlist**です。  
  
    > [!NOTE]
    >  一度に複数のオーケストレーションを参加させる、shift キーを押しながら、参加させる各オーケストレーションを選択する、オーケストレーションを右クリックし、をクリックして**Enlist**です。  
  
     オーケストレーションが登録され、適切なサブスクリプションが作成されます。 オーケストレーションは停止状態になります。 受信メッセージの処理を開始する必要があります明示的にオーケストレーションを開始しを右クリックし**開始**です。 詳細については、次を参照してください。[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md)です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションを参加解除する方法](../core/how-to-unenlist-an-orchestration.md)