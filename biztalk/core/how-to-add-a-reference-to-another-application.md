---
title: "別のアプリケーションへの参照を追加する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: applications, referencing
ms.assetid: 6a177560-ee1f-403a-a68a-ade409a39a35
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25668e7cfcb7d810d999c01eef28e5116b46c298
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-reference-to-another-application"></a>他のアプリケーションへの参照を追加する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、1 つのアプリケーションから別のアプリケーションへの参照を追加する方法について説明します。 」の説明に従って、インポート ウィザードを使用して、アプリケーションをインポートするときに、他のアプリケーションへの参照を追加することも[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。  
  
 同じ BizTalk グループの別のアプリケーション内に既に存在するアイテムを、現在のアプリケーションで使用する場合は、参照を追加します。 これは、ほとんどの種類のアイテムが BizTalk グループ内で一意である必要があるためです。 現在のアプリケーションに重複するアイテムを追加するのではなく、既にこのアイテムを含んでいる他のアプリケーションへの参照を追加します。 詳細については、次を参照してください。[成果物をする必要がありますする内で一意のアプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)です。  
  
 仮想ディレクトリを使用する場合、または別のアプリケーションに既に存在する証明書を使用する場合は、参照を追加する必要はありません。 さらに、これらの場合は循環参照が作成される可能性があるため、参照を追加しないようにすることをお勧めします。  
  
 依存関係のあるアプリケーションをインポートする場合は、参照もインポートできます。 別のアプリケーションへの参照を追加すると、両方のアプリケーションの展開方法に影響することに注意してください。 詳細については、次を参照してください。[の依存関係とアプリケーションの配置](../core/dependencies-and-application-deployment.md)です。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-add-a-reference-to-another-application"></a>別のアプリケーションへの参照を追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、[[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]] を展開し、参照を作成するアプリケーションを右クリックします。 これは、別のアプリケーションに含まれているアイテムを使用するアプリケーションです。  
  
3.  指す**追加** をクリックし、**参照**です。  
  
4.  **アプリケーション**、クリックして (成果物またはを使用するアイテムを含むアプリケーション) の参照を追加するアプリケーションのチェック ボックスをオン**OK**です。  
  
     参照が現在のアプリケーションに追加されます。 コンソール ツリーで、このアプリケーションから参照したアプリケーションに、他の 1 つ以上のアプリケーションから参照されていることを示す手の形のアイコンが追加されます。  
  
     ![共有アプリケーション アイコン](../core/media/sharedapplicationicon.gif "SharedApplicationIcon")  
  
## <a name="see-also"></a>参照  
 [作成して、BizTalk アプリケーションの変更](../core/creating-and-modifying-biztalk-applications.md)