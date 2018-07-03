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
ms.openlocfilehash: 094b49aba2e55e20ad32304f5b700126a2322d75
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995315"
---
# <a name="how-to-assign-a-certificate-to-a-receive-location"></a>受信場所に証明書を割り当てる方法
このトピックでは、BizTalk Server 管理コンソールを使用して、受信場所にセキュリティ証明書を割り当てる方法について説明します。 この手順は、双方向の受信場所に対してのみ実行できます。 証明書は、BizTalk Server が実行されているコンピューターの "その他のユーザー" 証明書ストアに格納しておく必要があります。それ以外の場合、この受信場所に関連付けられているメッセージは処理されずにエラーが記録されます。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-assign-a-certificate-to-a-receive-location"></a>受信場所に証明書を割り当てるには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループを展開し、受信場所に証明書を割り当てる BizTalk アプリケーションを展開します。  
  
3. 展開**受信場所**は、受信場所を右クリックし、[**プロパティ**、] をクリックし、**証明書**します。  
  
4. ローカル コンピューターの証明書が存在する場合にクリックします**参照**、参照を割り当てるには、この証明書を受信場所とクリック **[ok]** します。 それ以外の場合は、この手順を省略して次の手順に進みます。  
  
   > [!NOTE]
   >  リモート コンピューターからこの操作を実行する場合は、ローカル コンピューターだけではなく、BizTalk Server を実行するコンピューターにも証明書が存在することを確認してください。 そうでない場合、受信場所はメッセージを処理できません。  
  
5. かどうか、証明書がありません、ローカル コンピューター上で、**拇印**ボックスに入力し、証明書の拇印を貼り付けますまたはクリックして**OK**。 証明書の拇印の形式は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH です。H は 16 進数です。  
  
## <a name="see-also"></a>参照  
 [受信場所の管理](../core/managing-receive-locations.md)