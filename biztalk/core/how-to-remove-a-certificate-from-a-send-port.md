---
title: "送信ポートから証明書を削除する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5193b1b6003660aac0e0b427da0f0a338b56d8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a>送信ポート グループから証明書を削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートからセキュリティ証明書を削除する方法について説明します。 この操作を実行すると、送信ポートではメッセージが暗号化されなくなり、メッセージはクリア テキストで送信されるようになります。 証明書を送信ポートから削除しても、証明書ストアからは削除されません。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にセキュリティ証明書を送信ポートから削除するには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a>送信ポートから証明書を削除するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートから証明書を削除する BizTalk アプリケーションを展開します。  
  
3.  展開**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**証明書**です。  
  
4.  をクリックして**削除証明書**、クリックして**[ok]**です。  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)