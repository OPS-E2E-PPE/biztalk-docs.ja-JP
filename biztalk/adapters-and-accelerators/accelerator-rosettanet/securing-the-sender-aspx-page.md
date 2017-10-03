---
title: "送信者の ASPX ページをセキュリティで保護する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ASPX pages, protocol rules
- security, ASPX pages
- RNIFSend.aspx
- ASPX pages, security
- protocol rules [ASPX pages]
ms.assetid: 8214e3f5-a8e9-4d71-957d-ed0852035030
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0c5d5ec97d4d4aed862ffc1dbc0d75d0c0430d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="securing-the-sender-aspx-page"></a>送信者の ASPX ページをセキュリティで保護します。
ここでは、RNIFSend.aspx ページの不正使用を防止する方法について説明します。 次の 2 種類の手順を使用できます。  
  
-   インターネット インフォメーション サービス (IIS) マネージャーで RNIFSend.aspx をセキュリティ保護し、承認されていないサーバーが RNIFSend.aspx ページを使用して、認証されていないメッセージをネットワークから送信するのを防ぎます。  
  
-   Microsoft Internet Security and Acceleration (ISA) Server を使用して、発信 HTTP 要求のプロトコル ルールを作成します。  
  
### <a name="to-secure-rnifsendaspx"></a>RNIFSend.aspx をセキュリティ保護するには  
  
1.  RNIF メッセージの送信に使用する Web サーバーでをクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**です。  
  
2.  IIS マネージャーで、ローカル コンピューターのノードを展開し、 **Websites**、順に展開**既定の Web サイト**です。  
  
3.  をクリックして**BTARNApp**、右側のペインで右クリックし、 **RNIFSend.aspx**です。  
  
4.  **[プロパティ]**をクリックします。 **ファイル セキュリティ** タブの 、 **IP アドレスとドメイン名の制限**セクションで、**編集**です。  
  
5.  [IP アドレスとドメイン名の制限] ダイアログ ボックスで、**拒否**、順にクリック**追加**です。  
  
6.  **アクセス権の付与** ダイアログ ボックスで送信操作を実行するすべての BizTalk Server を追加します。 1 台のサーバーを追加する場合はクリックして**1 台のコンピューター**です。 **IP アドレス**ボックスに、コンピューターの IP アドレスを入力し、をクリックして**OK**です。  
  
7.  サーバーのグループを追加すると、クリックして**コンピューターのグループ**、し、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**ネットワーク ID**|使用するネットワークを入力します。|  
    |**サブネット マスク**|使用するサブネット マスクを入力します。|  
  
8.  **[OK]**をクリックします。  
  
    > [!NOTE]
    >  すべての送信操作が個々のインスタンスで実行されているそれぞれのホストに既に分離されている場合は、このコンピューターを追加するだけです。 他のすべてのアクセスを拒否できます。  
  
9. をクリックして**[ok]**、順にクリック**OK**もう一度です。  
  
### <a name="to-create-a-protocol-rule-of-outgoing-http-requests"></a>発信 HTTP 要求のプロトコル ルールを作成するには  
  
1.  ISA の管理 をクリックして**アクセス ポリシー**、クリックして**プロトコル ルール**です。  
  
2.  という名前の新しいプロトコル ルールを作成する**HTTP** TCP プロトコルを使用します。  
  
3.  プロトコル ルールの新しい HTTP のプロパティ ページで、**適用先** タブで **以下に指定されたクライアント アドレス セットに適用されます**です。 ページにアクセスする必要があるクライアント IP のみを入力します。  
  
## <a name="see-also"></a>参照  
 [構成、証明書、データベース、およびセキュリティを管理します。](manage-configuration-certificates-databases-security.md)