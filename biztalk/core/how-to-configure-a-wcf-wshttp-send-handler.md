---
title: "Wcf-wshttp 送信ハンドラーを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, global variables
- configuring [WCF-WSHttp adapters], send handlers
- configuring [WCF-WSHttp adapters], global variables
- send handlers, WCF-WSHttp adapters
ms.assetid: b2c30edb-8f7b-4d3c-812b-5b877c47fda1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11566bcc902ccbda33b6b15922292390df3d5201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-wshttp-send-handler"></a><span data-ttu-id="ffd09-102">WCF-WSHttp 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="ffd09-102">How to Configure a WCF-WSHttp Send Handler</span></span>
<span data-ttu-id="ffd09-103">WCF-WSHttp 送信ハンドラーを構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ffd09-103">Use the following procedure to configure the WCF-WSHttp send handler.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ffd09-104">WCF-WSHttp アダプター ハンドラーを使用する場合、これらのハンドラーのホスト インスタンスを [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] コンピューターにインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ffd09-104">When using WCF-WSHttp adapter handlers, it is recommended that you install the host instances for these handlers on [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  
  
### <a name="to-change-global-variables-for-a-wcf-wshttp-send-handler"></a><span data-ttu-id="ffd09-105">WCF-WSHttp 送信ハンドラーのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="ffd09-105">To change global variables for a WCF-WSHttp send handler</span></span>  
  
1.  <span data-ttu-id="ffd09-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="ffd09-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  
  
2.  <span data-ttu-id="ffd09-107">展開したアダプターの一覧でクリックして**Wcf-wshttp**、右側のペインで、構成する送信ハンドラを右クリックしをクリック**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="ffd09-107">In the expanded adapter list, click **WCF-WSHttp**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ffd09-108">**アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられる、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="ffd09-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  
  
4.  <span data-ttu-id="ffd09-109">**全般** タブをクリックして**プロパティ**の**プロキシ** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ffd09-109">In the **General** tab, Click **Properties**, On the **Proxy** tab, do the following.</span></span>  
  
    |<span data-ttu-id="ffd09-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ffd09-110">Use this</span></span>|<span data-ttu-id="ffd09-111">目的</span><span class="sxs-lookup"><span data-stu-id="ffd09-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="ffd09-112">**[プロキシを使用する]**</span><span class="sxs-lookup"><span data-stu-id="ffd09-112">**Use proxy**</span></span>|<span data-ttu-id="ffd09-113">この送信ポートがプロキシ サーバーを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ffd09-113">Indicate whether this send port uses a proxy server.</span></span><br /><br /> <span data-ttu-id="ffd09-114">既定値はオフです。</span><span class="sxs-lookup"><span data-stu-id="ffd09-114">The default value is cleared.</span></span>|  
    |<span data-ttu-id="ffd09-115">**Address**</span><span class="sxs-lookup"><span data-stu-id="ffd09-115">**Address**</span></span>|<span data-ttu-id="ffd09-116">プロキシ サーバーのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ffd09-116">Specify the address of the proxy server.</span></span> <span data-ttu-id="ffd09-117">使用して、 **https**または**http**セキュリティ構成に応じてスキームです。</span><span class="sxs-lookup"><span data-stu-id="ffd09-117">Use the **https** or the **http** scheme depending on the security configuration.</span></span> <span data-ttu-id="ffd09-118">このアドレスの後に、コロンとポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffd09-118">This address can be followed by a colon and the port number.</span></span> <span data-ttu-id="ffd09-119">たとえば、http://127.0.0.1:8080 と指定します。</span><span class="sxs-lookup"><span data-stu-id="ffd09-119">For example, http://127.0.0.1:8080.</span></span><br /><br /> <span data-ttu-id="ffd09-120">このプロパティには、値の場合にのみが必要です。**プロキシを使用して**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ffd09-120">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="ffd09-121">型:文字列</span><span class="sxs-lookup"><span data-stu-id="ffd09-121">Type: String</span></span><br /><br /> <span data-ttu-id="ffd09-122">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="ffd09-122">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="ffd09-123">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="ffd09-123">The default is an empty string.</span></span>|  
    |<span data-ttu-id="ffd09-124">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="ffd09-124">**User name**</span></span>|<span data-ttu-id="ffd09-125">認証に使用するユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="ffd09-125">Specify the user name to use for authentication.</span></span> <span data-ttu-id="ffd09-126">統合認証または基本認証が使用されている場合は、"ドメイン\ユーザー名" のように、ユーザー名にドメインを含めます。</span><span class="sxs-lookup"><span data-stu-id="ffd09-126">If integrated or Basic authentication is used, the user name includes the domain, that is, domain\username.</span></span> <span data-ttu-id="ffd09-127">ダイジェスト認証を使用する場合、ユーザー名がドメインを含まない\\です。</span><span class="sxs-lookup"><span data-stu-id="ffd09-127">If Digest authentication is used, the user name does not include domain\\.</span></span><br /><br /> <span data-ttu-id="ffd09-128">このプロパティには、値の場合にのみが必要です。**プロキシを使用して**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ffd09-128">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="ffd09-129">型:文字列</span><span class="sxs-lookup"><span data-stu-id="ffd09-129">Type: String</span></span><br /><br /> <span data-ttu-id="ffd09-130">最小長: 0</span><span class="sxs-lookup"><span data-stu-id="ffd09-130">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="ffd09-131">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="ffd09-131">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="ffd09-132">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="ffd09-132">The default is an empty string.</span></span>|  
    |<span data-ttu-id="ffd09-133">**Password**</span><span class="sxs-lookup"><span data-stu-id="ffd09-133">**Password**</span></span>|<span data-ttu-id="ffd09-134">認証に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="ffd09-134">Specify the password to use for authentication.</span></span><br /><br /> <span data-ttu-id="ffd09-135">このプロパティには、値の場合にのみが必要です。**プロキシを使用して**が選択されています。</span><span class="sxs-lookup"><span data-stu-id="ffd09-135">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="ffd09-136">型:文字列</span><span class="sxs-lookup"><span data-stu-id="ffd09-136">Type: String</span></span><br /><br /> <span data-ttu-id="ffd09-137">最小長: 0</span><span class="sxs-lookup"><span data-stu-id="ffd09-137">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="ffd09-138">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="ffd09-138">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="ffd09-139">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="ffd09-139">The default is an empty string.</span></span>|  
  
5.  <span data-ttu-id="ffd09-140">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffd09-140">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffd09-141">参照</span><span class="sxs-lookup"><span data-stu-id="ffd09-141">See Also</span></span>  
 [<span data-ttu-id="ffd09-142">Wcf-wshttp アダプタを構成します。</span><span class="sxs-lookup"><span data-stu-id="ffd09-142">Configuring the WCF-WSHttp Adapter</span></span>](../core/configuring-the-wcf-wshttp-adapter.md)