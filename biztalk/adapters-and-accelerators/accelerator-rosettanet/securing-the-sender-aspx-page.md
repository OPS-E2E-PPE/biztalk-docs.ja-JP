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
# <a name="securing-the-sender-aspx-page"></a><span data-ttu-id="61b84-102">送信者の ASPX ページをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="61b84-102">Securing the Sender ASPX Page</span></span>
<span data-ttu-id="61b84-103">このトピックでは、権限のない使用から RNIFSend.aspx ページを保護する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="61b84-103">This topic describes how to protect the RNIFSend.aspx page from unauthorized use.</span></span> <span data-ttu-id="61b84-104">使用できる 2 つの手順があります。</span><span class="sxs-lookup"><span data-stu-id="61b84-104">There are two procedures that you can use:</span></span>  
  
-   <span data-ttu-id="61b84-105">インターネット インフォメーション サービス (IIS) マネージャーでは、承認されていないサーバーが使用しているない RNIFSend.aspx ページ、ネットワークからの承認されていないメッセージを送信するかどうかを確認する RNIFSend.aspx をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="61b84-105">In Internet Information Services (IIS) Manager, secure RNIFSend.aspx to make sure that no unauthorized server will use the RNIFSend.aspx page to transmit unauthorized messages from your network.</span></span>  
  
-   <span data-ttu-id="61b84-106">発信 HTTP 要求のプロトコル ルールを作成するのにには、Microsoft Internet Security and Acceleration (ISA) Server を使用します。</span><span class="sxs-lookup"><span data-stu-id="61b84-106">Use Microsoft Internet Security and Acceleration (ISA) Server to create a protocol rule of outgoing HTTP requests.</span></span>  
  
### <a name="to-secure-rnifsendaspx"></a><span data-ttu-id="61b84-107">RNIFSend.aspx をセキュリティで保護するには</span><span class="sxs-lookup"><span data-stu-id="61b84-107">To secure RNIFSend.aspx</span></span>  
  
1.  <span data-ttu-id="61b84-108">RNIF メッセージの送信に使用する Web サーバーで次のようにクリックします**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、 をクリックし、  **。インターネット インフォメーション サービス (IIS) マネージャー**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-108">On the Web server you use for RNIF message transmission, click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="61b84-109">IIS マネージャーで、ローカル コンピューターのノードを展開し、 **Websites**、順に展開**既定の Web サイト**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-109">In IIS Manager, expand the local computer node, expand **Web Sites**, and then expand **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="61b84-110">クリックして**BTARNApp**、右側のウィンドウで右クリック**RNIFSend.aspx**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-110">Click **BTARNApp**, and then in the right pane, right-click **RNIFSend.aspx**.</span></span>  
  
4.  <span data-ttu-id="61b84-111">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b84-111">Click **Properties**.</span></span> <span data-ttu-id="61b84-112">**ファイル セキュリティ**] タブで、 **IP アドレスとドメイン名の制限**セクションで、[**編集**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-112">On the **File Security** tab, in the **IP address and domain name restrictions** section, click **Edit**.</span></span>  
  
5.  <span data-ttu-id="61b84-113">[IP アドレスとドメイン名の制限] ダイアログ ボックスで、**拒否**、順にクリックします**追加**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-113">In the IP Address and Domain Name Restrictions dialog box, click **Denied Access**, and then click **Add**.</span></span>  
  
6.  <span data-ttu-id="61b84-114">**アクセスを許可する** ダイアログ ボックスで、送信操作を実行するすべての BizTalk Server を追加します。</span><span class="sxs-lookup"><span data-stu-id="61b84-114">In the **Grant Access** dialog box, add all BizTalk Servers performing send operations.</span></span> <span data-ttu-id="61b84-115">1 台のサーバーを追加する場合はクリックして**1 台のコンピューター**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-115">If adding a single server, click **Single computer**.</span></span> <span data-ttu-id="61b84-116">**IP アドレス**ボックスで、コンピューターの IP アドレスを入力し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-116">In the **IP Address** box, type the IP address for the computer, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="61b84-117">サーバーのグループを追加する場合はクリックして**のコンピューターのグループ**、し、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="61b84-117">If adding a group of servers, click **Group of Computers**, and then do the following:</span></span>  
  
    |<span data-ttu-id="61b84-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="61b84-118">Use this</span></span>|<span data-ttu-id="61b84-119">目的</span><span class="sxs-lookup"><span data-stu-id="61b84-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="61b84-120">**ネットワーク ID**</span><span class="sxs-lookup"><span data-stu-id="61b84-120">**Network ID**</span></span>|<span data-ttu-id="61b84-121">使用するネットワークを入力します。</span><span class="sxs-lookup"><span data-stu-id="61b84-121">Type the network you want to use.</span></span>|  
    |<span data-ttu-id="61b84-122">**サブネット マスク**</span><span class="sxs-lookup"><span data-stu-id="61b84-122">**Subnet mask**</span></span>|<span data-ttu-id="61b84-123">使用するサブネット マスクを入力します。</span><span class="sxs-lookup"><span data-stu-id="61b84-123">Type the subnet mask you want to use.</span></span>|  
  
8.  <span data-ttu-id="61b84-124">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="61b84-124">Click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61b84-125">場合のみこのコンピューターを追加する必要があります、別のインスタンスで実行されている別のホストにすべての送信操作が分割されます。</span><span class="sxs-lookup"><span data-stu-id="61b84-125">If you have separated all your send operations to a separate host running on a separate instance, then you only have to add this computer.</span></span> <span data-ttu-id="61b84-126">アクセスを拒否できます他のすべてのユーザー。</span><span class="sxs-lookup"><span data-stu-id="61b84-126">You can deny all others access.</span></span>  
  
9. <span data-ttu-id="61b84-127">をクリックして**OK**、順にクリックします**OK**もう一度です。</span><span class="sxs-lookup"><span data-stu-id="61b84-127">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-create-a-protocol-rule-of-outgoing-http-requests"></a><span data-ttu-id="61b84-128">発信 HTTP 要求のプロトコル ルールを作成するには</span><span class="sxs-lookup"><span data-stu-id="61b84-128">To create a protocol rule of outgoing HTTP requests</span></span>  
  
1.  <span data-ttu-id="61b84-129">ISA 管理で次のようにクリックします。**アクセス ポリシー**、 をクリックし、**プロトコル ルール**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-129">In ISA Management, click **Access Policy**, and then click **Protocol Rules**.</span></span>  
  
2.  <span data-ttu-id="61b84-130">という名前の新しいプロトコル ルールを作成**HTTP** TCP プロトコルを使用します。</span><span class="sxs-lookup"><span data-stu-id="61b84-130">Create a new protocol rule named **HTTP** that uses TCP protocol.</span></span>  
  
3.  <span data-ttu-id="61b84-131">プロトコル ルールの新しい HTTP のプロパティ ページで、**適用先** タブで **以下で指定したクライアント アドレス セットに適用されます**します。</span><span class="sxs-lookup"><span data-stu-id="61b84-131">In the property page of your new HTTP protocol rule, in the **Applies To** tab, select **Applies to Client address sets specified below**.</span></span> <span data-ttu-id="61b84-132">クライアント ページにアクセスする Ip のみを入力します。</span><span class="sxs-lookup"><span data-stu-id="61b84-132">Enter only those client IPs that you want to access the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b84-133">参照</span><span class="sxs-lookup"><span data-stu-id="61b84-133">See Also</span></span>  
 [<span data-ttu-id="61b84-134">構成、証明書、データベース、セキュリティの管理</span><span class="sxs-lookup"><span data-stu-id="61b84-134">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)