---
title: オーケストレーションを参加解除する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: c55f0f7daee927e90e514cb7b566b058cee8044a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255882"
---
# <a name="how-to-unenlist-an-orchestration"></a>オーケストレーションを参加解除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションを参加解除する方法について説明します。 オーケストレーションを参加解除は、ホストから削除します。 このオーケストレーションによってメッセージが処理されないように、サブスクリプションも削除されます。 バインドを編集するには、事前にオーケストレーションを参加解除しておく必要があります。  
  
 オーケストレーションの参加を解除する前に」の説明に従って、実行中のインスタンスを終了する必要が[中断、再開、およびオーケストレーション インスタンスを終了する方法](../core/how-to-suspend-resume-and-terminate-orchestration-instances.md)です。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にオーケストレーションを参加解除するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-unenlist-an-orchestration"></a>オーケストレーションを参加解除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、し、参加解除するオーケストレーションを含むアプリケーションを展開します。  
  
3.  をクリックして**オーケストレーション**、参加解除、およびをクリックするオーケストレーションを右クリックして**参加解除**です。  
  
    > [!NOTE]
    >  一度に複数のオーケストレーションの参加を解除し、shift キーを押しながら各オーケストレーションを参加解除するを選択、オーケストレーションを右クリックし、をクリックして**参加解除**です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)   
 [展開して、BizTalk アプリケーションの管理](../core/deploying-and-managing-biztalk-applications.md)