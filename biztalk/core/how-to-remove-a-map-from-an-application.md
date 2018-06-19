---
title: アプリケーションからマップを削除する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, maps
- deleting, maps
- managing [maps], deleting
- managing [maps], applications
ms.assetid: 27d9bb08-36f0-46ff-ae9a-2247be6e3f96
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8b264809306e2cda40cc44be1287b6c2426fb43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254634"
---
# <a name="how-to-remove-a-map-from-an-application"></a>マップをアプリケーションから削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アプリケーションからマップを削除する方法について説明します。 マップの新しいバージョンを展開した後で、マップを削除する場合があります。 詳細とアプリケーションのアイテムを更新するための重要な考慮事項は、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)です。  
  
 マップを削除すると、次の処理が行われます。  
  
-   マップが BizTalk 管理データベースから削除されます。  
  
-   マップを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。  
  
-   BizTalk アセンブリが削除されると、アセンブリに含まれるアイテムもすべて BizTalk 管理データベースから削除されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-remove-a-map"></a>マップを削除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**、削除するには、マップが含まれる BizTalk グループを展開し、マップを含むアプリケーションを展開します。  
  
3.  クリックして、**マップ**フォルダーは、マップを右クリックし、をクリックして**削除**です。  
  
> [!NOTE]
>  複数のマップを削除するには、shift キーを押しながら各マップ解除し、マップの 1 つを右クリックし、をクリックをクリックし、**削除**です。  
  
## <a name="see-also"></a>参照  
 [マップを管理します。](../core/managing-maps.md)   
 [アプリケーションから BizTalk アセンブリを削除する方法](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)   
 [BizTalk アプリケーションを展開解除](../core/undeploying-biztalk-applications.md)