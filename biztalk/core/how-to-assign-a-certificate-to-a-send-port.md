---
title: "送信ポートに証明書を割り当てる方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, assigning
- managing [send ports], certificates
- assigning certificates
- certificates, send ports
ms.assetid: ba9e9c8b-f5b6-4fee-9e89-31b0f1df6ed4
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec19c845c6b0cfb5d19bd7a961fe9ddfbcf2a3d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-a-certificate-to-a-send-port"></a>送信ポートに証明書を割り当てる方法
このトピックでは、BizTalk Server 管理コンソールを使用して、送信ポートにセキュリティ証明書を割り当てる方法について説明します。 証明書は、BizTalk Server が実行されているコンピューターの "その他のユーザー" 証明書ストアに格納しておく必要があります。それ以外の場合、この送信ポートに関連付けられているメッセージは処理されずにエラーが記録されます。  
  
> [!NOTE]
>  アプリケーション開発者が開発プロセス中にセキュリティ証明書を送信ポートに割り当てるには、このトピックの手順を実行します。  
  
## <a name="prerequisites"></a>前提条件  
 このトピックの手順を実行するには、BizTalk Server 管理者グループのメンバーであるアカウントを使用してログオンする必要があります。 詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)です。  
  
### <a name="to-assign-a-certificate-to-a-send-port"></a>送信ポートに証明書を割り当てるには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、順にクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ツリーで、BizTalk グループを展開し、送信ポートに証明書を割り当てる BizTalk アプリケーションを展開します。  
  
3.  展開**送信ポート**、送信ポートを右クリックし、をクリックして**プロパティ**、クリックして**証明書**です。  
  
4.  証明書がローカル コンピューターに存在する場合にクリックして**参照**、この送信ポートに割り当てるし、をクリックする証明書を参照**OK**です。 それ以外の場合は、この手順を省略して次の手順に進みます。  
  
    > [!NOTE]
    >  証明書がローカル コンピューターに存在する場合でも、BizTalk Server の実行されているコンピューターが別にある場合は、そのコンピューターにも証明書が存在している必要があります。BizTalk Server の実行されているコンピューターに証明書がないと、送信ポートがメッセージを処理できません。  
  
5.  かどうか、証明書が、ローカル コンピューター上にありません、**拇印**ボックスに入力し、証明書の拇印を貼り付け、またはをクリックして**OK**です。 証明書の拇印の形式は、HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH です。H は 16 進数です。  
  
## <a name="see-also"></a>参照  
 [作成して、送信ポートの構成](../core/creating-and-configuring-send-ports.md)