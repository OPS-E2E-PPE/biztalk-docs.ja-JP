---
title: 送信者の ASPX ページをセキュリティで保護する |Microsoft ドキュメント
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
ms.openlocfilehash: a0c5d5ec97d4d4aed862ffc1dbc0d75d0c0430d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207762"
---
# <a name="securing-the-sender-aspx-page"></a><span data-ttu-id="61e03-102">送信者の ASPX ページをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="61e03-102">Securing the Sender ASPX Page</span></span>
<span data-ttu-id="61e03-103">ここでは、RNIFSend.aspx ページの不正使用を防止する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61e03-103">This topic describes how to protect the RNIFSend.aspx page from unauthorized use.</span></span> <span data-ttu-id="61e03-104">次の 2 種類の手順を使用できます。</span><span class="sxs-lookup"><span data-stu-id="61e03-104">There are two procedures that you can use:</span></span>  
  
-   <span data-ttu-id="61e03-105">インターネット インフォメーション サービス (IIS) マネージャーで RNIFSend.aspx をセキュリティ保護し、承認されていないサーバーが RNIFSend.aspx ページを使用して、認証されていないメッセージをネットワークから送信するのを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="61e03-105">In Internet Information Services (IIS) Manager, secure RNIFSend.aspx to make sure that no unauthorized server will use the RNIFSend.aspx page to transmit unauthorized messages from your network.</span></span>  
  
-   <span data-ttu-id="61e03-106">Microsoft Internet Security and Acceleration (ISA) Server を使用して、発信 HTTP 要求のプロトコル ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="61e03-106">Use Microsoft Internet Security and Acceleration (ISA) Server to create a protocol rule of outgoing HTTP requests.</span></span>  
  
### <a name="to-secure-rnifsendaspx"></a><span data-ttu-id="61e03-107">RNIFSend.aspx をセキュリティ保護するには</span><span class="sxs-lookup"><span data-stu-id="61e03-107">To secure RNIFSend.aspx</span></span>  
  
1.  <span data-ttu-id="61e03-108">RNIF メッセージの送信に使用する Web サーバーでをクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、クリックして**インターネット インフォメーション サービス (IIS) マネージャー**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-108">On the Web server you use for RNIF message transmission, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="61e03-109">IIS マネージャーで、ローカル コンピューターのノードを展開し、 **Websites**、順に展開**既定の Web サイト**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-109">In IIS Manager, expand the local computer node, expand **Web Sites**, and then expand **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="61e03-110">をクリックして**BTARNApp**、右側のペインで右クリックし、 **RNIFSend.aspx**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-110">Click **BTARNApp**, and then in the right pane, right-click **RNIFSend.aspx**.</span></span>  
  
4.  <span data-ttu-id="61e03-111">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61e03-111">Click **Properties**.</span></span> <span data-ttu-id="61e03-112">**ファイル セキュリティ** タブの 、 **IP アドレスとドメイン名の制限**セクションで、**編集**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-112">On the **File Security** tab, in the **IP address and domain name restrictions** section, click **Edit**.</span></span>  
  
5.  <span data-ttu-id="61e03-113">[IP アドレスとドメイン名の制限] ダイアログ ボックスで、**拒否**、順にクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-113">In the IP Address and Domain Name Restrictions dialog box, click **Denied Access**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="61e03-114">**アクセス権の付与** ダイアログ ボックスで送信操作を実行するすべての BizTalk Server を追加します。</span><span class="sxs-lookup"><span data-stu-id="61e03-114">In the **Grant Access** dialog box, add all BizTalk Servers performing send operations.</span></span> <span data-ttu-id="61e03-115">1 台のサーバーを追加する場合はクリックして**1 台のコンピューター**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-115">If adding a single server, click **Single computer**.</span></span> <span data-ttu-id="61e03-116">**IP アドレス**ボックスに、コンピューターの IP アドレスを入力し、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-116">In the **IP Address** box, type the IP address for the computer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="61e03-117">サーバーのグループを追加すると、クリックして**コンピューターのグループ**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="61e03-117">If adding a group of servers, click **Group of Computers**, and then do the following:</span></span>  
  
    |<span data-ttu-id="61e03-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="61e03-118">Use this</span></span>|<span data-ttu-id="61e03-119">目的</span><span class="sxs-lookup"><span data-stu-id="61e03-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="61e03-120">**ネットワーク ID**</span><span class="sxs-lookup"><span data-stu-id="61e03-120">**Network ID**</span></span>|<span data-ttu-id="61e03-121">使用するネットワークを入力します。</span><span class="sxs-lookup"><span data-stu-id="61e03-121">Type the network you want to use.</span></span>|  
    |<span data-ttu-id="61e03-122">**サブネット マスク**</span><span class="sxs-lookup"><span data-stu-id="61e03-122">**Subnet mask**</span></span>|<span data-ttu-id="61e03-123">使用するサブネット マスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="61e03-123">Type the subnet mask you want to use.</span></span>|  
  
8.  <span data-ttu-id="61e03-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61e03-124">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61e03-125">すべての送信操作が個々のインスタンスで実行されているそれぞれのホストに既に分離されている場合は、このコンピューターを追加するだけです。</span><span class="sxs-lookup"><span data-stu-id="61e03-125">If you have separated all your send operations to a separate host running on a separate instance, then you only have to add this computer.</span></span> <span data-ttu-id="61e03-126">他のすべてのアクセスを拒否できます。</span><span class="sxs-lookup"><span data-stu-id="61e03-126">You can deny all others access.</span></span>  
  
9. <span data-ttu-id="61e03-127">をクリックして **[ok]**、順にクリック**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="61e03-127">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-create-a-protocol-rule-of-outgoing-http-requests"></a><span data-ttu-id="61e03-128">発信 HTTP 要求のプロトコル ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="61e03-128">To create a protocol rule of outgoing HTTP requests</span></span>  
  
1.  <span data-ttu-id="61e03-129">ISA の管理 をクリックして**アクセス ポリシー**、クリックして**プロトコル ルール**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-129">In ISA Management, click **Access Policy**, and then click **Protocol Rules**.</span></span>  
  
2.  <span data-ttu-id="61e03-130">という名前の新しいプロトコル ルールを作成する**HTTP** TCP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="61e03-130">Create a new protocol rule named **HTTP** that uses TCP protocol.</span></span>  
  
3.  <span data-ttu-id="61e03-131">プロトコル ルールの新しい HTTP のプロパティ ページで、**適用先** タブで **以下に指定されたクライアント アドレス セットに適用されます**です。</span><span class="sxs-lookup"><span data-stu-id="61e03-131">In the property page of your new HTTP protocol rule, in the **Applies To** tab, select **Applies to Client address sets specified below**.</span></span> <span data-ttu-id="61e03-132">ページにアクセスする必要があるクライアント IP のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="61e03-132">Enter only those client IPs that you want to access the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e03-133">参照</span><span class="sxs-lookup"><span data-stu-id="61e03-133">See Also</span></span>  
 [<span data-ttu-id="61e03-134">構成、証明書、データベース、およびセキュリティを管理します。</span><span class="sxs-lookup"><span data-stu-id="61e03-134">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)