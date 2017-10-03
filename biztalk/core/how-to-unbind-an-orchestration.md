---
title: "オーケストレーションをバインド解除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3a7c421d-e0cb-4b23-b472-e501056d6329
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce49c3e74846fac5943bda522d11218410f428ee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unbind-an-orchestration"></a>オーケストレーションをバインド解除します。

## <a name="overview"></a>概要
ここでは、BizTalk Server 管理コンソールを使用して、各種のバインド (受信ポート、送信ポート、ホスト) をオーケストレーションから削除する方法について説明します。  
  
> [!NOTE]
>  アプリケーション開発者がオーケストレーションのバインドを削除するには、このトピックの手順を実行します。 また、Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="remove-bindings-from-an-orchestration"></a>オーケストレーションからバインドを削除します。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、しを削除するオーケストレーションを含むアプリケーション展開バインド  
  
3.  をクリックして**オーケストレーション**、オーケストレーションを右クリックし、をクリックして**プロパティ**、順にクリック**バインド**左側のウィンドウでします。  
  
4.  ホストのバインドを削除する、**ホスト**一覧で、 **\<なし >**です。  
  
5.  削除する下にあるドロップダウン リストからの受信ポートのバインド、**受信ポート**をクリックして**\<なし >**です。  
  
6.  下にあるドロップダウン リストから送信ポートのバインドを削除する**送信ポート/送信ポート グループ**をクリックして**\<なし >**です。  
  
7.  バインド バインドを削除したらをクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)   
 [展開して、BizTalk アプリケーションの管理](../core/deploying-and-managing-biztalk-applications.md)