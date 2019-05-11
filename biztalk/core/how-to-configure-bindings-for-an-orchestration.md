---
title: オーケストレーションのバインドの構成 |Microsoft Docs
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
ms.openlocfilehash: 6de8d8626dbe0ad110e46d399c32f2dc9ba8a321
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386309"
---
# <a name="how-to-configure-bindings-for-an-orchestration"></a>オーケストレーションのバインドを構成する方法

## <a name="overview"></a>概要
このトピックでは、BizTalk Server 管理コンソールを使用して、オーケストレーションのバインドを構成する方法について説明します。 この作業には、オーケストレーションをホストにバインドしたり、オーケストレーションに定義されている論理ポートを、ステージング環境や実稼働環境の物理ポートにバインドしたりする作業が含まれます。 オーケストレーションのバインドが済んでいる場合は、この手順を使ってバインドを変更することができます。  
  
 バインドの構成後、オーケストレーションを参加させることによって、メッセージの処理を開始できます。 これらのタスクを実行する方法の詳細については、次を参照してください。[オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)と[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md)します。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にオーケストレーションのバインドを構成してその機能をテストするには、このトピックの手順を実行します。 また、Microsoft Windows Management Instrumentation (WMI) のオブジェクト モデルを使用して、管理タスクを自動化するスクリプトを作成および実行できます。 WMI の使用方法の詳細については、次を参照してください。、 **WMI クラスの参照**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
## <a name="configure-bindings-for-an-orchestration"></a>オーケストレーションのバインドを構成します。  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**展開し、BizTalk グループを展開し、**アプリケーション**、順に展開する対象のオーケストレーションを含むアプリケーションバインドを構成します。  
  
3. クリックして**オーケストレーション**をクリックして、バインドを構成するオーケストレーションを右クリックして**プロパティ**します。  
  
4. をクリックして、**バインド** タブとの間、**ホスト**一覧でオーケストレーションを参加させるホストを選択します。  
  
5. ドロップダウン リストからの一覧で、**受信ポート**列、各受信論理ポートの横にある論理ポートをバインドする受信ポートを選択します。  
  
6. ドロップダウン リストから、**送信ポート/送信ポート グループ**各受信論理ポートの横の列をクリックして、論理ポートをバインドする送信ポートを選択する**OK**します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーションの管理](../core/managing-orchestrations.md)   
 [オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)   
 [BizTalk アプリケーション展開、管理](../core/deploying-and-managing-biztalk-applications.md)