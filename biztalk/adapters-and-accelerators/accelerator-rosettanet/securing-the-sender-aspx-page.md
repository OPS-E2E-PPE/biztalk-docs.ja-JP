---
title: 送信者の ASPX ページをセキュリティで保護する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ASPX pages, protocol rules
- security, ASPX pages
- RNIFSend.aspx
- ASPX pages, security
- protocol rules [ASPX pages]
ms.assetid: 8214e3f5-a8e9-4d71-957d-ed0852035030
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0a7cf59ab1f00edeb8030681045aa6d2b512e83c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281854"
---
# <a name="securing-the-sender-aspx-page"></a>送信者の ASPX ページをセキュリティで保護します。
このトピックでは、権限のない使用から RNIFSend.aspx ページを保護する方法について説明します。 使用できる 2 つの手順があります。  
  
-   インターネット インフォメーション サービス (IIS) マネージャーでは、承認されていないサーバーが使用しているない RNIFSend.aspx ページ、ネットワークからの承認されていないメッセージを送信するかどうかを確認する RNIFSend.aspx をセキュリティで保護します。  
  
-   発信 HTTP 要求のプロトコル ルールを作成するのにには、Microsoft Internet Security and Acceleration (ISA) Server を使用します。  
  
### <a name="to-secure-rnifsendaspx"></a>RNIFSend.aspx をセキュリティで保護するには  
  
1.  RNIF メッセージの送信に使用する Web サーバーで次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックし、  **。インターネット インフォメーション サービス (IIS) マネージャー**します。  
  
2.  IIS マネージャーで、ローカル コンピューターのノードを展開し、 **Websites**、順に展開**既定の Web サイト**します。  
  
3.  クリックして**BTARNApp**、右側のウィンドウで右クリック**RNIFSend.aspx**します。  
  
4.  **[プロパティ]** をクリックします。 **ファイル セキュリティ**] タブで、 **IP アドレスとドメイン名の制限**セクションで、[**編集**します。  
  
5.  [IP アドレスとドメイン名の制限] ダイアログ ボックスで、**拒否**、順にクリックします**追加**します。  
  
6.  **アクセスを許可する** ダイアログ ボックスで、送信操作を実行するすべての BizTalk Server を追加します。 1 台のサーバーを追加する場合はクリックして**1 台のコンピューター**します。 **IP アドレス**ボックスで、コンピューターの IP アドレスを入力し、クリックして**OK**します。  
  
7.  サーバーのグループを追加する場合はクリックして**のコンピューターのグループ**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ネットワーク ID**|使用するネットワークを入力します。|  
    |**サブネット マスク**|使用するサブネット マスクを入力します。|  
  
8.  **[OK]** をクリックします。  
  
    > [!NOTE]
    >  場合のみこのコンピューターを追加する必要があります、別のインスタンスで実行されている別のホストにすべての送信操作が分割されます。 アクセスを拒否できます他のすべてのユーザー。  
  
9. をクリックして**OK**、順にクリックします**OK**もう一度です。  
  
### <a name="to-create-a-protocol-rule-of-outgoing-http-requests"></a>発信 HTTP 要求のプロトコル ルールを作成するには  
  
1.  ISA 管理で次のようにクリックします。**アクセス ポリシー**、 をクリックし、**プロトコル ルール**します。  
  
2.  という名前の新しいプロトコル ルールを作成**HTTP** TCP プロトコルを使用します。  
  
3.  プロトコル ルールの新しい HTTP のプロパティ ページで、**適用先** タブで **以下で指定したクライアント アドレス セットに適用されます**します。 クライアント ページにアクセスする Ip のみを入力します。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、セキュリティの管理](manage-configuration-certificates-databases-security.md)