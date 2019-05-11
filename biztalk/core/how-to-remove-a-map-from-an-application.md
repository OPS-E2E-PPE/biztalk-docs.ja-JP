---
title: アプリケーションからマップを削除する方法 |Microsoft Docs
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
ms.openlocfilehash: 07bfff864b35869c15922d0a907aa7bb30bc6912
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384403"
---
# <a name="how-to-remove-a-map-from-an-application"></a>マップをアプリケーションから削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、BizTalk アプリケーションからマップを削除する方法について説明します。 マップの新しいバージョンを展開した後で、マップを削除する場合があります。 詳細とアプリケーションのアイテムを更新するための重要な考慮事項は、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)します。  
  
 マップを削除すると、次の処理が行われます。  
  
-   マップが BizTalk 管理データベースから削除されます。  
  
-   マップを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。  
  
-   BizTalk アセンブリが削除されると、アセンブリに含まれるアイテムもすべて BizTalk 管理データベースから削除されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-remove-a-map"></a>マップを削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**、削除するには、マップが含まれる BizTalk グループを展開し、マップを含むアプリケーションを展開します。  
  
3. をクリックして、**マップ**フォルダーは、マップを右クリックし、順にクリックします**削除**します。  
  
> [!NOTE]
>  複数のマップを削除するには、shift キーを押しながら、削除をマップの 1 つを右クリックしてをクリックし、各マップをクリックします。**削除**します。  
  
## <a name="see-also"></a>参照  
 [マップの管理](../core/managing-maps.md)   
 [アプリケーションから BizTalk アセンブリを削除する方法](../core/how-to-remove-a-biztalk-assembly-from-an-application.md)   
 [BizTalk アプリケーションの展開解除](../core/undeploying-biztalk-applications.md)