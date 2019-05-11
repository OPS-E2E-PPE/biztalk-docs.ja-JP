---
title: オーケストレーションを参加解除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, unenlisting
- enlisting, unenlisting
- managing [orchestrations], unenlisting
- unenlisting, orchestrations
ms.assetid: 038ed7bb-615c-4e4e-a5bb-79de2626de77
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a96f0ee3f3de6c4ee64f004366f3e82a923b38aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383676"
---
# <a name="how-to-unenlist-an-orchestration"></a>オーケストレーションを参加解除する方法
このトピックでは、BizTalk Server 管理コンソールを使用してオーケストレーションを参加解除する方法について説明します。 オーケストレーションを参加解除は、ホストから削除します。 これにより、オーケストレーションが不要になったメッセージを処理できるように、サブスクリプションを削除します。 バインドを編集する前に、オーケストレーションの参加を解除する必要があります。  
  
 オーケストレーションの参加を解除する前に」の説明に従って、実行中のインスタンスを終了する必要があります[中断、再開、およびオーケストレーション インスタンスを終了する方法](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)します。  
  
> [!NOTE]
>  アプリケーション開発者は、このトピックの手順を使用して、開発プロセス中にオーケストレーションを参加解除できます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-unenlist-an-orchestration"></a>オーケストレーションを参加解除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、参加解除するオーケストレーションを含むアプリケーションを展開します。  
  
3. クリックして**オーケストレーション**をクリックして参加を解除すると、オーケストレーションを右クリックして**参加解除**します。  
  
   > [!NOTE]
   >  一度に複数のオーケストレーションを参加解除し、shift キーを押しながら、参加を解除するには、各オーケストレーションを選択、オーケストレーションを右クリックし をクリックし、**参加解除**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)   
 [BizTalk アプリケーション展開、管理](../core/deploying-and-managing-biztalk-applications.md)