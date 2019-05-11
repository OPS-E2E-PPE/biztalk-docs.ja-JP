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
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a><span data-ttu-id="6a9ab-102">発行し、シングル サインオン チケットを引き換える</span><span class="sxs-lookup"><span data-stu-id="6a9ab-102">Issuing and Redeeming a Single Sign-On Ticket</span></span>
<span data-ttu-id="6a9ab-103">ユーザーと関連アプリケーションをリンクした後は、通信を維持しながら、セキュリティを確保しやすくチケットを発行できます。</span><span class="sxs-lookup"><span data-stu-id="6a9ab-103">After you link a user and an affiliate application, you can issue tickets to help ensure security while maintaining communications.</span></span> <span data-ttu-id="6a9ab-104">シングル サインオン チケット発行の他のチケット テクノロジと同じように動作します。 のメッセージを送信する前に文字列としてのメッセージにシングル サインオン チケットを追加します。</span><span class="sxs-lookup"><span data-stu-id="6a9ab-104">Single Sign-On ticketing works just like other ticketing technologies: before sending the message off, you append the Single Sign-On ticket to the message as a string.</span></span> <span data-ttu-id="6a9ab-105">サーバーはメッセージを受け取る、チケットをデコードし、適切な情報を使用しています。</span><span class="sxs-lookup"><span data-stu-id="6a9ab-105">The server receives your message, decodes the ticket, and uses the information as appropriate.</span></span>  
  
### <a name="to-issue-a-single-sign-on-ticket"></a><span data-ttu-id="6a9ab-106">シングル サインオン チケットを発行するには</span><span class="sxs-lookup"><span data-stu-id="6a9ab-106">To issue a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="6a9ab-107">私の呼び出しで新しいチケット オブジェクトを作成`SSOTicket`です。</span><span class="sxs-lookup"><span data-stu-id="6a9ab-107">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="6a9ab-108">私の呼び出しで、チケットを発行`SSOTicket.IssueTicket`します。</span><span class="sxs-lookup"><span data-stu-id="6a9ab-108">Issue the ticket with a call to I`SSOTicket.IssueTicket`.</span></span>  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a><span data-ttu-id="6a9ab-109">シングル サインオン チケットを引き換える</span><span class="sxs-lookup"><span data-stu-id="6a9ab-109">To redeem a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="6a9ab-110">私の呼び出しで新しいチケット オブジェクトを作成`SSOTicket`です。</span><span class="sxs-lookup"><span data-stu-id="6a9ab-110">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="6a9ab-111">私の呼び出しでチケットを引き換える`SSOTicket.RedeemTicket`します。</span><span class="sxs-lookup"><span data-stu-id="6a9ab-111">Redeem the ticket with a call to I`SSOTicket.RedeemTicket`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a9ab-112">参照</span><span class="sxs-lookup"><span data-stu-id="6a9ab-112">See Also</span></span>  
 [<span data-ttu-id="6a9ab-113">Enterprise Single Sign-On によるプログラミング</span><span class="sxs-lookup"><span data-stu-id="6a9ab-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)