---
title: オーケストレーションを参加させる方法 |Microsoft Docs
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
ms.openlocfilehash: 203f8a61c439230b692577c8674b12e35944c24f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966291"
---
# <a name="how-to-enlist-an-orchestration"></a>オーケストレーションを参加させる方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションをホストに参加させる方法について説明します。 オーケストレーションは参加させて初めて開始できるようになります。  
  
 オーケストレーションを参加させる際は、次の点に注意してください。  
  
-   **参加させる前に、オーケストレーションをバインドする必要があります。** オーケストレーションのバインドを構成する方法の詳細については、次を参照してください。[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)します。  
  
-   **サブスクリプションは自動的に作成されます。** オーケストレーションの参加プロセスを経て、必要なサブスクリプションがメッセージ ボックス データベースに作成されます。  
  
-   **アプリケーションをインストールする必要があります。** オーケストレーションを実行するすべてのコンピューターに、そのオーケストレーションが含まれているアプリケーションをインストールする必要があります。 詳細については、次を参照してください。 [BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。  
  
-   **呼び出し元のオーケストレーションは、呼び出し先オーケストレーションと同じホストにバインドする必要があります。** 呼び出し元オーケストレーションは、呼び出し先オーケストレーションと同じホストにバインドする必要があります。  
  
-   **依存オーケストレーションを登録する必要があります。** オーケストレーションを参加させるとき、依存オーケストレーションがあれば、それらも一緒に参加させないと、依存オーケストレーションにサブスクリプションが割り当てられません。 依存オーケストレーションにサブスクリプションがないと、メッセージに対応するサブスクリプションが存在しないため、メッセージが削除または保留される可能性があります。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にオーケストレーションを参加させてその機能をテストするには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-enlist-an-orchestration"></a>オーケストレーションを参加させるには  
  
1. クリックして**開始**、 をクリックして**プログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、参加させるオーケストレーションを含むアプリケーションを展開します。  
  
3. クリックして**オーケストレーション**をクリックして、参加させ、オーケストレーションを右クリックして**参加**します。  
  
   > [!NOTE]
   >  一度に複数のオーケストレーションを参加させるし、shift キーを押しながら各オーケストレーションを参加させることを選択、オーケストレーションを右クリックし、**参加**します。  
  
    オーケストレーションが登録され、適切なサブスクリプションが作成されます。 オーケストレーションは停止状態になります。 受信メッセージの処理を開始するにする必要があります明示的に開始するオーケストレーションをそれを右クリックして**開始**します。 詳細については、次を参照してください。[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md)します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションを参加解除する方法](../core/how-to-unenlist-an-orchestration.md)