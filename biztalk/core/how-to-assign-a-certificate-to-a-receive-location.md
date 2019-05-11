---
title: 証明書を割り当てる方法、受信場所 |Microsoft Docs
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
ms.assetid: 54ae300e-62c5-480f-a9b7-e5c3457a0f80
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d02cf6c22de920b166fcbe1e0b238b02b5bf2398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342739"
---
# <a name="how-to-assign-a-certificate-to-a-receive-location"></a>証明書を割り当てる方法、受信場所
このトピックでは、BizTalk Server 管理コンソールを使用して受信場所にセキュリティ証明書を割り当てる方法について説明します。 この手順を実行する双方向の受信場所のみです。 証明書は、BizTalk Server を実行しているコンピューターの他のユーザー証明書ストアに存在する必要がありますまたはこれに関連付けられているメッセージの受信場所は処理されず、エラー ログに記録されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-assign-a-certificate-to-a-receive-location"></a>受信場所に証明書を割り当てる  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループと受信場所に証明書を割り当てる BizTalk アプリケーションを展開します。  
  
3. 展開**受信場所**は、受信場所を右クリックし、[**プロパティ**、] をクリックし、**証明書**します。  
  
4. ローカル コンピューターの証明書が存在する場合にクリックします**参照**、参照を割り当てるには、この証明書を受信場所とクリック **[ok]** します。 それ以外の場合、この手順をスキップします。  
  
   > [!NOTE]
   >  リモート コンピューターからこの操作を実行する場合は、BizTalk Server を実行しているコンピューターでは、ローカル コンピューター上だけでなく、証明書が存在することを確認します。 それ以外の場合、受信場所はメッセージを処理できません。  
  
5. かどうか、証明書がありません、ローカル コンピューター上で、**拇印**ボックスに入力し、証明書の拇印を貼り付けますまたはクリックして**OK**。 証明書の拇印は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進形式を持ちます。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)