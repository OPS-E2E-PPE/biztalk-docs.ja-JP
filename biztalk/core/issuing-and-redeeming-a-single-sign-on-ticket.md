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
# <a name="issuing-and-redeeming-a-single-sign-on-ticket"></a><span data-ttu-id="d961f-102">発行して、シングル サインオン チケットを引き換える</span><span class="sxs-lookup"><span data-stu-id="d961f-102">Issuing and Redeeming a Single Sign-On Ticket</span></span>
<span data-ttu-id="d961f-103">ユーザーと関連アプリケーションとをリンクした後で、チケットを発行して、通信を維持する間のセキュリティを確保できます。</span><span class="sxs-lookup"><span data-stu-id="d961f-103">After you link a user and an affiliate application, you can issue tickets to help ensure security while maintaining communications.</span></span> <span data-ttu-id="d961f-104">他のチケット テクノロジと同じようにシングル サインオン チケット発行の動作:、メッセージを送信する前に追加する必要がシングル サインオン チケットを文字列としてメッセージにします。</span><span class="sxs-lookup"><span data-stu-id="d961f-104">Single Sign-On ticketing works just like other ticketing technologies: before sending the message off, you append the Single Sign-On ticket to the message as a string.</span></span> <span data-ttu-id="d961f-105">サーバーはメッセージを受け取ると、チケットをデコードし、情報を適宜使用します。</span><span class="sxs-lookup"><span data-stu-id="d961f-105">The server receives your message, decodes the ticket, and uses the information as appropriate.</span></span>  
  
### <a name="to-issue-a-single-sign-on-ticket"></a><span data-ttu-id="d961f-106">シングル サインオン チケットを発行するには</span><span class="sxs-lookup"><span data-stu-id="d961f-106">To issue a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="d961f-107">新しいチケット オブジェクトを I`SSOTicket` の呼び出しによって作成します。</span><span class="sxs-lookup"><span data-stu-id="d961f-107">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="d961f-108">I`SSOTicket.IssueTicket` の呼び出しによって、チケットを発行します。</span><span class="sxs-lookup"><span data-stu-id="d961f-108">Issue the ticket with a call to I`SSOTicket.IssueTicket`.</span></span>  
  
### <a name="to-redeem-a-single-sign-on-ticket"></a><span data-ttu-id="d961f-109">シングル サインオン チケットを引き換えるには</span><span class="sxs-lookup"><span data-stu-id="d961f-109">To redeem a Single Sign-On ticket</span></span>  
  
1.  <span data-ttu-id="d961f-110">新しいチケット オブジェクトを I`SSOTicket` の呼び出しによって作成します。</span><span class="sxs-lookup"><span data-stu-id="d961f-110">Create a new ticket object with a call to I`SSOTicket`.</span></span>  
  
2.  <span data-ttu-id="d961f-111">I`SSOTicket.RedeemTicket` の呼び出しによって、チケットを引き換えます。</span><span class="sxs-lookup"><span data-stu-id="d961f-111">Redeem the ticket with a call to I`SSOTicket.RedeemTicket`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d961f-112">参照</span><span class="sxs-lookup"><span data-stu-id="d961f-112">See Also</span></span>  
 [<span data-ttu-id="d961f-113">エンタープライズ シングル サインオンを使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="d961f-113">Programming with Enterprise Single Sign-On</span></span>](../core/programming-with-enterprise-single-sign-on.md)