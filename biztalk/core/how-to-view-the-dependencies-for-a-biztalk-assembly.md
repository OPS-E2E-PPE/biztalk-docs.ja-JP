---
title: BizTalk アセンブリの依存関係を表示する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- viewing, dependencies
- assemblies, dependencies
- managing [assemblies], dependencies
- assemblies, viewing
- viewing, assemblies
- managing [assemblies], viewing
ms.assetid: 872abc99-8248-4397-9fcb-24a0ba6f4757
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 592d85210fc08835229cea3990c150680aed56bc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383123"
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a>BizTalk アセンブリの依存関係を表示する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アセンブリに依存関係を持つアイテムの一覧を表示する方法について説明します。 依存関係とアプリケーションの配置への影響についての背景については、次を参照してください。[依存関係とアプリケーションの展開](../core/dependencies-and-application-deployment.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Operators グループのメンバー アカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a>BizTalk アセンブリの依存関係を表示するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、依存関係を表示する BizTalk アセンブリが含まれる BizTalk グループ、BizTalk アセンブリが含まれるアプリケーションの順に展開します。  
  
3. をクリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、順にクリックします**変更**します。  
  
4. をクリックして、**依存関係**タブ。  
  
    この BizTalk アセンブリに依存関係を持つアイテムの名前と状態が一覧に表示されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)