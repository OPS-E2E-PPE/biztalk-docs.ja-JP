---
title: SOAP 送信ハンドラーを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, SOAP adapters
- SOAP adapters, denial of service
- denital of service, HTTP adapters
- configuring [SOAP adapters], send handlers
- configuring [SOAP adapters], denial of service
- SOAP adapters, send handlers
- denial of service, SOAP adapters
ms.assetid: fd610a3f-ca10-42e0-b81e-219e07e33830
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4bcbe39861c37db348e1e37752fbad6d9616033
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005483"
---
# <a name="how-to-configure-a-soap-send-handler"></a><span data-ttu-id="dcb6e-102">SOAP 送信ハンドラーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="dcb6e-102">How to Configure a SOAP Send Handler</span></span>
<span data-ttu-id="dcb6e-103">次の手順を実行して、SOAP 送信ハンドラーを構成します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-103">Use the following procedure to configure the SOAP send handler.</span></span>  

> [!CAUTION]
>  <span data-ttu-id="dcb6e-104">HTTP または SOAP アダプタ ハンドラを使用する場合は、Microsoft では、これらのハンドラーのホスト インスタンスをインストールすることをお勧め[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]コンピューター。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-104">When using HTTP or SOAP adapter handlers, it is recommended that you install the host instances for these handlers on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]computers.</span></span>  

### <a name="to-change-global-variables-for-a-soap-send-handler"></a><span data-ttu-id="dcb6e-105">SOAP 送信ハンドラーのグローバル変数を変更するには</span><span class="sxs-lookup"><span data-stu-id="dcb6e-105">To change global variables for a SOAP send handler</span></span>  

1. <span data-ttu-id="dcb6e-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-106">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then expand **Adapters**.</span></span>  

2. <span data-ttu-id="dcb6e-107">展開したアダプターの一覧でクリックして**SOAP**、右側のウィンドウで、構成する送信ハンドラーを右クリックし をクリック、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-107">In the expanded adapter list, click **SOAP**, in the right pane, right-click the send handler that you want to configure, and then click **Properties**.</span></span>  

3. <span data-ttu-id="dcb6e-108">**アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、受信ハンドラーが関連付けられているが、ホストを選択します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-108">In the **Adapter Handler Properties** dialog box, on the **General** tab, in the **Host Name** list, select the host with which the receive handler will be associated.</span></span>  

4. <span data-ttu-id="dcb6e-109">**プロキシ** タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-109">On the **Proxy** tab, do the following.</span></span>  


   |   <span data-ttu-id="dcb6e-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="dcb6e-110">Use this</span></span>    |                                                                                                                  <span data-ttu-id="dcb6e-111">目的</span><span class="sxs-lookup"><span data-stu-id="dcb6e-111">To do this</span></span>                                                                                                                   |
   |---------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="dcb6e-112">**[プロキシを使用する]**</span><span class="sxs-lookup"><span data-stu-id="dcb6e-112">**Use proxy**</span></span> |                                                                                          <span data-ttu-id="dcb6e-113">SOAP 送信ハンドラーがプロキシ サーバーを使用するかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-113">Indicate whether the SOAP send handler uses a proxy server.</span></span>                                                                                          |
   |  <span data-ttu-id="dcb6e-114">**[サーバー]**</span><span class="sxs-lookup"><span data-stu-id="dcb6e-114">**Server**</span></span>   |                  <span data-ttu-id="dcb6e-115">プロキシ サーバーの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-115">Specify the name of the proxy server.</span></span><br /><br /> <span data-ttu-id="dcb6e-116">場合にこのプロパティが値にのみ必要と**プロキシを使用して、** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-116">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="dcb6e-117">型:文字列</span><span class="sxs-lookup"><span data-stu-id="dcb6e-117">Type: String</span></span><br /><br /> <span data-ttu-id="dcb6e-118">最小長: 0</span><span class="sxs-lookup"><span data-stu-id="dcb6e-118">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="dcb6e-119">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="dcb6e-119">Maximum length: 256</span></span>                   |
   |   <span data-ttu-id="dcb6e-120">**[ポート]**</span><span class="sxs-lookup"><span data-stu-id="dcb6e-120">**Port**</span></span>    | <span data-ttu-id="dcb6e-121">SOAP 送信ハンドラーが使用するポートを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-121">Specify the port the SOAP send handler uses.</span></span><br /><br /> <span data-ttu-id="dcb6e-122">場合にこのプロパティが値にのみ必要と**プロキシを使用して、** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-122">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="dcb6e-123">既定値: 80</span><span class="sxs-lookup"><span data-stu-id="dcb6e-123">Default Value: 80</span></span><br /><br /> <span data-ttu-id="dcb6e-124">型: 長整数</span><span class="sxs-lookup"><span data-stu-id="dcb6e-124">Type: Long</span></span><br /><br /> <span data-ttu-id="dcb6e-125">最小値: 0</span><span class="sxs-lookup"><span data-stu-id="dcb6e-125">Minimum value: 0</span></span><br /><br /> <span data-ttu-id="dcb6e-126">最大値: 65535</span><span class="sxs-lookup"><span data-stu-id="dcb6e-126">Maximum value: 65535</span></span> |
   | <span data-ttu-id="dcb6e-127">**ユーザー名**</span><span class="sxs-lookup"><span data-stu-id="dcb6e-127">**User name**</span></span> |             <span data-ttu-id="dcb6e-128">認証に使用するユーザー名を指定します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-128">Specify the user name to use for authentication.</span></span><br /><br /> <span data-ttu-id="dcb6e-129">場合にこのプロパティが値にのみ必要と**プロキシを使用して、** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-129">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="dcb6e-130">型:文字列</span><span class="sxs-lookup"><span data-stu-id="dcb6e-130">Type: String</span></span><br /><br /> <span data-ttu-id="dcb6e-131">最小長: 0</span><span class="sxs-lookup"><span data-stu-id="dcb6e-131">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="dcb6e-132">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="dcb6e-132">Maximum length: 256</span></span>             |
   | <span data-ttu-id="dcb6e-133">**Password**</span><span class="sxs-lookup"><span data-stu-id="dcb6e-133">**Password**</span></span>  |             <span data-ttu-id="dcb6e-134">認証に使用するパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-134">Specify the password to use for authentication.</span></span><br /><br /> <span data-ttu-id="dcb6e-135">場合にこのプロパティが値にのみ必要と**プロキシを使用して、** が選択されています。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-135">This property only requires a value if **Use proxy** is selected.</span></span><br /><br /> <span data-ttu-id="dcb6e-136">型:文字列</span><span class="sxs-lookup"><span data-stu-id="dcb6e-136">Type: String</span></span><br /><br /> <span data-ttu-id="dcb6e-137">最小長: 0</span><span class="sxs-lookup"><span data-stu-id="dcb6e-137">Minimum length: 0</span></span><br /><br /> <span data-ttu-id="dcb6e-138">最大長: 256</span><span class="sxs-lookup"><span data-stu-id="dcb6e-138">Maximum length: 256</span></span>              |


5. <span data-ttu-id="dcb6e-139">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dcb6e-139">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dcb6e-140">参照</span><span class="sxs-lookup"><span data-stu-id="dcb6e-140">See Also</span></span>  
 <span data-ttu-id="dcb6e-141">[SOAP アダプターの構成](../core/configuring-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="dcb6e-141">[Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="dcb6e-142">Web サービスの公開</span><span class="sxs-lookup"><span data-stu-id="dcb6e-142">Publishing Web Services</span></span>](../core/publishing-web-services.md)