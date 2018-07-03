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
ms.openlocfilehash: 7504551d6cc97f108d6cdee695f241ee983994a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993515"
---
# <a name="how-to-unenlist-an-orchestration"></a>オーケストレーションを参加解除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションを参加解除する方法について説明します。 オーケストレーションを参加解除は、ホストから削除します。 このオーケストレーションによってメッセージが処理されないように、サブスクリプションも削除されます。 バインドを編集するには、事前にオーケストレーションを参加解除しておく必要があります。  
  
 オーケストレーションの参加を解除する前に」の説明に従って、実行中のインスタンスを終了する必要があります[中断、再開、およびオーケストレーション インスタンスを終了する方法](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)します。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にオーケストレーションを参加解除するには、このトピックの手順を実行します。  
  
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