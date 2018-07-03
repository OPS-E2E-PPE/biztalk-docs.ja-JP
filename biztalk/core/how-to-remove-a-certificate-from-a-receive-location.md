---
title: 証明書を削除する方法、受信場所 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 717d41bf-4260-4df4-9d0a-07243bb9b12c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5af6db7dcbb9efb20846520db6b800f5c3226316
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991979"
---
# <a name="how-to-remove-a-certificate-from-a-receive-location"></a>受信場所から証明書を削除する方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所からセキュリティ証明書を削除する方法について説明します。 この操作を実行すると、受信場所ではメッセージが暗号化されなくなり、メッセージはクリア テキストで送信されるようになります。 証明書を受信場所から削除しても、証明書ストアからは削除されません。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-remove-a-certificate-from-a-receive-location"></a>受信場所から証明書を削除するには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、受信場所から証明書を削除する BizTalk アプリケーションを展開します。  
  
3. 展開**受信場所**は、受信場所を右クリックし、[**プロパティ**、] をクリックし、**証明書**します。  
  
4. クリックして**証明書の削除**、順にクリックします**OK**します。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)