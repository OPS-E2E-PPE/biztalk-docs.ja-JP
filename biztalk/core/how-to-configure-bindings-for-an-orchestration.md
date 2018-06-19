---
title: オーケストレーションのバインドの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9724a3a0-c217-4f98-b6d9-21f788ce50ba
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adb695f9636327107887397372d5fc2dda74e4eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248922"
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a>オーケストレーションのバインドを構成する方法

## <a name="overview"></a>概要
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションのバインドを構成する方法について説明します。 この作業には、オーケストレーションをホストにバインドしたり、オーケストレーションに定義されている論理ポートを、ステージング環境や実稼働環境の物理ポートにバインドしたりする作業が含まれます。 オーケストレーションのバインドが済んでいる場合は、この手順を使ってバインドを変更することができます。  
  
 バインドの構成後、オーケストレーションを参加させることによって、メッセージの処理を開始できます。 これらのタスクの実行方法の詳細については、次を参照してください。[にオーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)と[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md)です。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にオーケストレーションのバインドを構成してその機能をテストするには、このトピックの手順を実行します。 また、Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用については、次を参照してください。、 **WMI クラス参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
## <a name="configure-bindings-for-an-orchestration"></a>オーケストレーションのバインドを構成します。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、BizTalk グループを展開し、**アプリケーション**、しをオーケストレーションを含むアプリケーション展開バインディングを構成します。  
  
3.  をクリックして**オーケストレーション**をクリックして、バインドを構成するオーケストレーションを右クリックして**プロパティ**です。  
  
4.  クリックして、**バインド** タブとの間、**ホスト**一覧で、オーケストレーションを参加させるホストを選択します。  
  
5.  ドロップダウン リストからの一覧で、**受信ポート**各受信論理ポートの横の列が、論理ポートをバインドする受信ポートを選択します。  
  
6.  ドロップダウン リストから、**送信ポート/送信ポート グループ**各受信論理ポートの横の列をクリックして、論理ポートをバインドする送信ポートの選択**OK**です。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)   
 [展開して、BizTalk アプリケーションの管理](../core/deploying-and-managing-biztalk-applications.md)