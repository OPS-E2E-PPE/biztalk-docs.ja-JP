---
title: 発行し、シングル サインオン チケットを引き換える |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a0323a6-cc31-460d-b64d-b4d8142c3855
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04399b37fb977179afd668ec4aacc7e8c6aa5b7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329712"
---
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a>発行し、シングル サインオン チケットを引き換える
ユーザーと関連アプリケーションをリンクした後は、通信を維持しながら、セキュリティを確保しやすくチケットを発行できます。 シングル サインオン チケット発行の他のチケット テクノロジと同じように動作します。 のメッセージを送信する前に文字列としてのメッセージにシングル サインオン チケットを追加します。 サーバーはメッセージを受け取る、チケットをデコードし、適切な情報を使用しています。  
  
### <a name="to-issue-a-single-sign-on-ticket"></a>シングル サインオン チケットを発行するには  
  
1.  私の呼び出しで新しいチケット オブジェクトを作成`SSOTicket`です。  
  
2.  私の呼び出しで、チケットを発行`SSOTicket.IssueTicket`します。  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a>シングル サインオン チケットを引き換える  
  
1.  私の呼び出しで新しいチケット オブジェクトを作成`SSOTicket`です。  
  
2.  私の呼び出しでチケットを引き換える`SSOTicket.RedeemTicket`します。  
  
## <a name="see-also"></a>参照  
 [Enterprise Single Sign-On によるプログラミング](../core/programming-with-enterprise-single-sign-on.md)