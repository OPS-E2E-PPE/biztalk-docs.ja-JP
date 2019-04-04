---
title: アプリケーションからスキーマを削除する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, schemas
- applications, schemas
- schemas, deleting
- managing [schemas], deleting
- managing [schemas], applications
- schemas, applications
ms.assetid: 17dd5869-b56c-4166-9f02-03e04e691eda
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0693d94736c4ef3d8ad5ee561ed6b42650c90ab3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985435"
---
# <a name="how-to-remove-a-schema-from-an-application"></a>スキーマをアプリケーションから削除する方法
ここでは、BizTalk Server 管理コンソールを使用して、スキーマをアプリケーションから削除する方法について説明します。 この手順では、グループの BizTalk 管理データベースからもスキーマを削除します。 スキーマの新しいバージョンを展開した後にスキーマを削除する場合があります。 詳細とアプリケーションのアイテムを更新するための重要な考慮事項は、[BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)を参照してください。  
  
 スキーマを削除し、同じルート名前空間を持つスキーマの前のバージョンがアプリケーションに存在する場合は、前のバージョンがアクティブになります。  
  
 スキーマを削除すると、次の処理が行われます。  
  
-   スキーマが BizTalk 管理データベースから削除されます。  
  
-   スキーマを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。  
  
-   BizTalk アセンブリが削除されると、アセンブリに含まれるアイテムもすべて BizTalk 管理データベースから削除されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-remove-a-schema"></a>スキーマを削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開**BizTalk Server 管理**スキーマが含まれる BizTalk グループを削除して、スキーマを含むアプリケーションを展開します。  
  
3. クリックして**スキーマ**、スキーマを右クリックし、クリックして**削除**します。  
  
## <a name="see-also"></a>参照  
 [スキーマの管理](../core/managing-schemas.md)