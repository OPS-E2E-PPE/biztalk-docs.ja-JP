---
title: 送信ポートに証明書を割り当てる方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, assigning
- managing [send ports], certificates
- assigning certificates
- certificates, send ports
ms.assetid: ba9e9c8b-f5b6-4fee-9e89-31b0f1df6ed4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eb9fbc2cc7237f1e5cf9343f7ae8537b7ea8218a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387207"
---
# <a name="how-to-assign-a-certificate-to-a-send-port"></a>送信ポートに証明書を割り当てる方法
このトピックでは、BizTalk Server 管理コンソールを使用して送信ポートにセキュリティ証明書を割り当てる方法について説明します。 証明書は、BizTalk Server を実行しているコンピューターの他のユーザー証明書ストアに存在する必要があります、この送信ポートに関連付けられているメッセージは処理されずやエラーをログに記録されます。  
  
> [!NOTE]
>  アプリケーション開発者割り当てることができますセキュリティ証明書を送信ポートに開発プロセス中にこのトピックの手順を使用しています。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントでログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)します。  
  
### <a name="to-assign-a-certificate-to-a-send-port"></a>送信ポートに証明書を割り当てる  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリックします**BizTalk Server 管理**します。  
  
2. コンソール ツリーで、BizTalk グループと送信ポートに証明書を割り当てる BizTalk アプリケーションを展開します。  
  
3. 展開**送信ポート**は、送信ポートを右クリックし、[**プロパティ**、] をクリックし、**証明書**します。  
  
4. ローカル コンピューターの証明書が存在する場合にクリックします**参照**、この送信ポートに割り当てるし をクリックしたい証明書を参照**OK**します。 それ以外の場合、この手順をスキップします。  
  
   > [!NOTE]
   >  ローカル コンピューターの証明書が存在する場合でも、送信ポートがメッセージを処理できる前に、異なる場合、BizTalk Server を実行するコンピューターにする必要がありますも存在します。  
  
5. かどうか、証明書がありません、ローカル コンピューター上で、**拇印**ボックスに入力し、証明書の拇印を貼り付けますまたはクリックして**OK**。 証明書の拇印は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH、H は 16 進形式を持ちます。  
  
## <a name="see-also"></a>参照  
 [送信ポートの作成および構成](../core/creating-and-configuring-send-ports.md)