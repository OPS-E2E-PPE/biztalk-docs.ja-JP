---
title: BizTalk アセンブリの依存関係を表示する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 99fbc09a5adb59691a4914a8ddc341c8034c8bb8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22256434"
---
# <a name="how-to-view-the-dependencies-for-a-biztalk-assembly"></a>BizTalk アセンブリの依存関係を表示する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アセンブリに依存関係を持つアイテムの一覧を表示する方法について説明します。 依存関係とアプリケーションの展開への影響に関する背景情報については、次を参照してください。[の依存関係とアプリケーションの配置](../core/dependencies-and-application-deployment.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループまたは BizTalk Operators グループのメンバー アカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-view-the-dependencies-of-a-biztalk-assembly"></a>BizTalk アセンブリの依存関係を表示するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、依存関係を表示する BizTalk アセンブリが含まれる BizTalk グループ、BizTalk アセンブリが含まれるアプリケーションの順に展開します。  
  
3.  クリックして、**リソース**フォルダーは、BizTalk アセンブリを右クリックし、をクリックして**変更**です。  
  
4.  クリックして、**の依存関係**タブです。  
  
     この BizTalk アセンブリに依存関係を持つアイテムの名前と状態が一覧に表示されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk アセンブリの管理](../core/managing-biztalk-assemblies.md)