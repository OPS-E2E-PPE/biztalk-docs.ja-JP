---
title: アプリケーションからスキーマを削除する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 6535764af00156325c006388a88803207329e5fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254650"
---
# <a name="how-to-remove-a-schema-from-an-application"></a>スキーマをアプリケーションから削除する方法
ここでは、BizTalk Server 管理コンソールを使用して、スキーマをアプリケーションから削除する方法について説明します。 この手順では、グループの BizTalk 管理データベースからもスキーマを削除します。 スキーマの新しいバージョンを展開した後にスキーマを削除する場合があります。 詳細とアプリケーションのアイテムを更新するための重要な考慮事項は、次を参照してください。 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)です。  
  
 スキーマを削除し、同じルート名前空間を持つスキーマの前のバージョンがアプリケーションに存在する場合は、前のバージョンがアクティブになります。  
  
 スキーマを削除すると、次の処理が行われます。  
  
-   スキーマが BizTalk 管理データベースから削除されます。  
  
-   スキーマを含む BizTalk アセンブリも BizTalk 管理データベースから削除されますが、ローカル ファイル システムまたはグローバル アセンブリ キャッシュ (GAC) 内に存在する場合、そのアセンブリは削除されません。  
  
-   BizTalk アセンブリが削除されると、アセンブリに含まれるアイテムもすべて BizTalk 管理データベースから削除されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-remove-a-schema"></a>スキーマを削除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで  **BizTalk Server 管理コンソール**スキーマを含む BizTalk グループを削除して、スキーマを含むアプリケーションを展開します。  
  
3.  をクリックして**スキーマ**、スキーマを右クリックし、クリックして**削除**です。  
  
## <a name="see-also"></a>参照  
 [スキーマの管理](../core/managing-schemas.md)