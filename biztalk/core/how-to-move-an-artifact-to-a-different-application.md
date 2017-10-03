---
title: "別のアプリケーションにアイテムを移動する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- artifacts, moving
- applications, artifacts
ms.assetid: 861e7782-0566-4478-a0bd-f8ced1ea6d56
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdc28eb92b09d459ba5f05439572f07e3f35411f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-move-an-artifact-to-a-different-application"></a>アイテムを別のアプリケーションに移動する方法
このトピックでは、BizTalk Server 管理コンソールの [アプリケーションに移動] コマンドを使用して、アプリケーションから BizTalk グループ内の別のアプリケーションにアイテムを移動する方法について説明します。 この操作は、あるアプリケーションに既に存在するアイテムを、同じ BizTalk グループの別のアプリケーションで使用する場合に実行します。  
  
 アイテムを移動する際は、次の点に注意してください。  
  
-   **アプリケーションは、同じグループ内でなければなりません。** [アプリケーションに移動] コマンドは、アイテムの移動元のアプリケーションと移動先のアプリケーションが、同じ BizTalk グループに存在する場合にのみ機能します。 異なるグループのアプリケーションにアイテムを移動する場合は、そのアイテムが現在存在するアプリケーションからエクスポートを行い、移動先のアプリケーションでインポートを行うか、そのアイテムを追加することで実行できます。 手順については、次を参照してください。[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)、[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)、および[成果物を追加または作成する方法](../core/how-to-create-or-add-an-artifact.md)です。 必要がありますし、手動でアイテムを削除する、元のアプリケーションから」の説明に従って[アプリケーションからアイテムを削除する方法](../core/how-to-remove-an-artifact-from-an-application.md)です。  
  
-   **アイテムの移動を依存しているか、それに依存するアイテムを移動できます。** 別のアプリケーションにアイテムを移動する場合は、移動するアイテムが依存するアイテムが含まれているアプリケーションを移動先のアプリケーションが参照している場合を除き、そのアイテムが依存するその他のアイテムも移動されます。 また、移動するアイテムに依存しているアイテムも、そのようなアイテムが含まれているアプリケーションが移動先のアプリケーションを参照している場合を除き、移動先のアプリケーションに移動されます。 アイテムを移動する際には、同時に移動されるその他のアイテムの一覧が表示されます。  
  
> [!NOTE]
>  同じアイテムを複数のアプリケーションで使用する場合、アイテムの種類によっては、そのアイテムを使用するアプリケーションから、そのアイテムが含まれているアプリケーションへの参照を作成する必要があります。 これは、特定の種類のアイテムが BizTalk グループ内で一意である必要があるためです。 詳細については、次を参照してください。[成果物をする必要がありますする内で一意のアプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)です。 参照を追加する方法の詳細については、次を参照してください。[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。 あるアプリケーションから別のアプリケーションへの参照を追加すると、これらのアプリケーション間に依存関係が作成されるため、展開方法に影響することに注意してください。 背景情報について、次を参照してください。[の依存関係とアプリケーションの配置](../core/dependencies-and-application-deployment.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-move-an-artifact-to-a-different-application"></a>アイテムを別のアプリケーションに移動するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]]、BizTalk グループ、アイテムの移動元のアプリケーションの順に展開します。  
  
3.  移動をアイテムを右クリックし、をクリックするアイテムが含まれるフォルダーをクリックして**アプリケーションに移動**です。  
  
4.  **送信先アプリケーション**ボックス、矢印をクリックし、成果物を移動するアプリケーションをクリックします。  
  
     **移動するアイテム**ボックスには、すべての依存関係アイテムも移動されると、移動するアイテムが表示されます。  
  
5.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)