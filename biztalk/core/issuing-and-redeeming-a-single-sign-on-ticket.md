---
title: "発行して、シングル サインオン チケットを引き換える |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a0323a6-cc31-460d-b64d-b4d8142c3855
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9988eedb545b3b1a348a5de6275b176abe2be7e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a>発行して、シングル サインオン チケットを引き換える
ユーザーと関連アプリケーションとをリンクした後で、チケットを発行して、通信を維持する間のセキュリティを確保できます。 他のチケット テクノロジと同じようにシングル サインオン チケット発行の動作:、メッセージを送信する前に追加する必要がシングル サインオン チケットを文字列としてメッセージにします。 サーバーはメッセージを受け取ると、チケットをデコードし、情報を適宜使用します。  
  
### <a name="to-issue-a-single-sign-on-ticket"></a>シングル サインオン チケットを発行するには  
  
1.  新しいチケット オブジェクトを I`SSOTicket` の呼び出しによって作成します。  
  
2.  I`SSOTicket.IssueTicket` の呼び出しによって、チケットを発行します。  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a>シングル サインオン チケットを引き換えるには  
  
1.  新しいチケット オブジェクトを I`SSOTicket` の呼び出しによって作成します。  
  
2.  I`SSOTicket.RedeemTicket` の呼び出しによって、チケットを引き換えます。  
  
## <a name="see-also"></a>参照  
 [エンタープライズ シングル サインオンを使用したプログラミング](../core/programming-with-enterprise-single-sign-on.md)