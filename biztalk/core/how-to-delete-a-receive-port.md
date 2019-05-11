---
title: 削除する方法、受信ポート |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], deleting
- deleting, receive ports
- receive ports, deleting
ms.assetid: 69cd86f7-e3cc-4a50-8d15-5f978c94a6be
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a548620bb78aa0d2daf5a360ab1f0e1be8878760
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338665"
---
# <a name="how-to-delete-a-receive-port"></a>受信ポートを削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信ポートを BizTalk アプリケーションから削除する方法について説明します。 受信ポートを BizTalk アプリケーションから削除すると、そのグループの BizTalk 管理データベースからも受信ポートが削除され、およびこの受信ポートに含まれているすべての受信場所が削除されます。  
  
 受信ポートがオーケストレーションにバインドされていると、この操作は正常に行われません。 受信ポートのバインドを削除する方法の詳細については、次を参照してください。[オーケストレーションをバインド解除する方法](../core/how-to-unbind-an-orchestration.md)します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-delete-a-receive-port"></a>受信ポートを削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、展開[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]展開し、BizTalk グループを展開し、**アプリケーション**、し、削除する受信ポートを含むアプリケーションを展開します。  
  
3. クリックして**受信ポート**受信ポートを右クリックし、クリックして**削除**します。  
  
## <a name="see-also"></a>参照  
 [受信ポートの管理](../core/managing-receive-ports.md)