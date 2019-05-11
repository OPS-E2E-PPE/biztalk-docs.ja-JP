---
title: オーケストレーションのバインド解除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae12bd07729aa473cdc52eabec7ad409d8fa0a1a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333864"
---
# <a name="unbind-an-orchestration"></a>オーケストレーションのバインド解除します。

## <a name="overview"></a>概要
ここでは、BizTalk Server 管理コンソールを使用して、各種のバインド (受信ポート、送信ポート、ホスト) をオーケストレーションから削除する方法について説明します。  
  
> [!NOTE]
>  アプリケーション開発者がオーケストレーションのバインドを削除するには、このトピックの手順を実行します。 また、Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="remove-bindings-from-an-orchestration"></a>オーケストレーションからバインドを削除します。  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、し、削除するオーケストレーションを含むアプリケーションを展開バインド  
  
3. をクリックして**オーケストレーション**は、オーケストレーションを右クリックし、**プロパティ**、順にクリックします**バインド**左側のウィンドウでします。  
  
4. ホストのバインドを削除する、**ホスト**一覧で、  **\<None\>** します。  
  
5. 削除する [ドロップダウン リストからの受信ポートのバインド、**受信ポート**、] をクリックして**\<なし\>**。  
  
6. 下のドロップダウン リストから送信ポートのバインドを削除する**送信ポート/送信ポート グループ**、 をクリックして **\<None\>** します。  
  
7. バインド バインドを削除したら、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)   
 [BizTalk アプリケーション展開、管理](../core/deploying-and-managing-biztalk-applications.md)