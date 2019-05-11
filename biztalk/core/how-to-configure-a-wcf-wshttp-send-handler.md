---
title: Wcf-wshttp 送信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, global variables
- configuring [WCF-WSHttp adapters], send handlers
- configuring [WCF-WSHttp adapters], global variables
- send handlers, WCF-WSHttp adapters
ms.assetid: b2c30edb-8f7b-4d3c-812b-5b877c47fda1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 295d6d5e281dcd614f8d624e0c725f29d2985db3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386579"
---
# <a name="how-to-configure-a-wcf-wshttp-send-handler"></a><span data-ttu-id="0139d-102">WCF-WSHttp 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="0139d-102">How to Configure a WCF-WSHttp Send Handler</span></span>
<span data-ttu-id="0139d-103">送信ハンドラーを Wcf-wshttp を構成するのには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0139d-103">Use the following procedure to configure the WCF-WSHttp send handler.</span></span>  

> [!CAUTION]
>  <span data-ttu-id="0139d-104">Wcf-wshttp アダプター ハンドラーを使用する場合には、これらのハンドラーのホスト インスタンスをインストールすることをお勧め[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]または[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="0139d-104">When using WCF-WSHttp adapter handlers, it is recommended that you install the host instances for these handlers on [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] computers.</span></span>  

### <a name="to-change-global-variables-for-a-wcf-wshttp-send-handler"></a><span data-ttu-id="0139d-105">グローバル変数を Wcf-wshttp 送信ハンドラーを変更するには</span><span class="sxs-lookup"><span data-stu-id="0139d-105">To change global variables for a WCF-WSHttp send handler</span></span>  

1. <span data-ttu-id="0139d-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="0139d-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="0139d-107">展開したアダプターの一覧でクリックして**Wcf-wshttp**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0139d-107">In the expanded adapter list, click **WCF-WSHttp**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="0139d-108">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="0139d-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="0139d-109">**全般** タブのをクリック**プロパティ**の**プロキシ** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0139d-109">In the **General** tab, Click **Properties**, On the **Proxy** tab, do the following.</span></span>  


   |   <span data-ttu-id="0139d-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="0139d-110">Use this</span></span>    |                                                                                                                                                                                                                        <span data-ttu-id="0139d-111">目的</span><span class="sxs-lookup"><span data-stu-id="0139d-111">To do this</span></span>                                                                                                                                                                                                                        |
   |---------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="0139d-112">**[プロキシを使用する]**</span><span class="sxs-lookup"><span data-stu-id="0139d-112">**Use proxy**</span></span> |                                                                                                                                                                              <span data-ttu-id="0139d-113">この送信ポートがプロキシ サーバーを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0139d-113">Indicate whether this send port uses a proxy server.</span></span><br /><br /> <span data-ttu-id="0139d-114">既定値はオフです。</span><span class="sxs-lookup"><span data-stu-id="0139d-114">The default value is cleared.</span></span>                                                                                                                                                                              |
   |  <span data-ttu-id="0139d-115">**Address**</span><span class="sxs-lookup"><span data-stu-id="0139d-115">**Address**</span></span>  |                      <span data-ttu-id="0139d-116">プロキシ サーバーのアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="0139d-116">Specify the address of the proxy server.</span></span> <span data-ttu-id="0139d-117">使用して、 **https**または**http**セキュリティ構成に応じてスキーム。</span><span class="sxs-lookup"><span data-stu-id="0139d-117">Use the **https** or the **http** scheme depending on the security configuration.</span></span> <span data-ttu-id="0139d-118">このアドレスの後に、コロンとポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="0139d-118">This address can be followed by a colon and the port number.</span></span> <span data-ttu-id="0139d-119">たとえば、 http://127.0.0.1:8080のようにします。</span><span class="sxs-lookup"><span data-stu-id="0139d-119">For example, http://127.0.0.1:8080.</span></span><br /><br /> <span data-ttu-id="0139d-120">このプロパティには値の場合にのみ**プロキシを使用して、** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="0139d-120">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="0139d-121">型:String</span><span class="sxs-lookup"><span data-stu-id="0139d-121">Type: String</span></span><br /><br /> <span data-ttu-id="0139d-122">最大長:256</span><span class="sxs-lookup"><span data-stu-id="0139d-122">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="0139d-123">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="0139d-123">The default is an empty string.</span></span>                      |
   | <span data-ttu-id="0139d-124">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="0139d-124">**User name**</span></span> | <span data-ttu-id="0139d-125">認証に使用するユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0139d-125">Specify the user name to use for authentication.</span></span> <span data-ttu-id="0139d-126">統合認証または基本認証が使用されている場合は、"ドメイン\ユーザー名" のように、ユーザー名にドメインを含めます。</span><span class="sxs-lookup"><span data-stu-id="0139d-126">If integrated or Basic authentication is used, the user name includes the domain, that is, domain\username.</span></span> <span data-ttu-id="0139d-127">ダイジェスト認証を使用する場合、ユーザー名がドメインを含まない\\します。</span><span class="sxs-lookup"><span data-stu-id="0139d-127">If Digest authentication is used, the user name does not include domain\\.</span></span><br /><br /> <span data-ttu-id="0139d-128">このプロパティには値の場合にのみ**プロキシを使用して、** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="0139d-128">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="0139d-129">型:String</span><span class="sxs-lookup"><span data-stu-id="0139d-129">Type: String</span></span><br /><br /> <span data-ttu-id="0139d-130">最小長:0</span><span class="sxs-lookup"><span data-stu-id="0139d-130">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="0139d-131">最大長:256</span><span class="sxs-lookup"><span data-stu-id="0139d-131">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="0139d-132">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="0139d-132">The default is an empty string.</span></span> |
   | <span data-ttu-id="0139d-133">**Password**</span><span class="sxs-lookup"><span data-stu-id="0139d-133">**Password**</span></span>  |                                                                                             <span data-ttu-id="0139d-134">認証に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="0139d-134">Specify the password to use for authentication.</span></span><br /><br /> <span data-ttu-id="0139d-135">このプロパティには値の場合にのみ**プロキシを使用して、** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="0139d-135">This property requires a value only if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="0139d-136">型:String</span><span class="sxs-lookup"><span data-stu-id="0139d-136">Type: String</span></span><br /><br /> <span data-ttu-id="0139d-137">最小長:0</span><span class="sxs-lookup"><span data-stu-id="0139d-137">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="0139d-138">最大長:256</span><span class="sxs-lookup"><span data-stu-id="0139d-138">Maximum length: 256</span></span><br /><br /> <span data-ttu-id="0139d-139">既定値は空の文字列です。</span><span class="sxs-lookup"><span data-stu-id="0139d-139">The default is an empty string.</span></span>                                                                                             |


5. <span data-ttu-id="0139d-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0139d-140">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0139d-141">参照</span><span class="sxs-lookup"><span data-stu-id="0139d-141">See Also</span></span>  
 [<span data-ttu-id="0139d-142">WCF-WSHttp アダプターの構成</span><span class="sxs-lookup"><span data-stu-id="0139d-142">Configuring the WCF-WSHttp Adapter</span></span>](../core/configuring-the-wcf-wshttp-adapter.md)