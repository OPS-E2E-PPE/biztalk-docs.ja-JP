---
title: "Biztalk WCF カスタム アダプターと Siebel アダプターを使用してポートを構成する |Microsoft ドキュメント"
description: "作成 wcf-custom 送信ポートと受信ポートを BizTalk Server で Siebel eBusiness Applications アダプターを使用するには"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53c5ee07-36ae-474b-9241-8b53c9066ca1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 485bfaf7bd958528630e96a64ca0129a56ec330d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-siebel-adapter"></a><span data-ttu-id="26c8c-103">Wcf-custom アダプターと Siebel アダプターを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-103">Configure a port using the WCF-custom adapter and Siebel adapter</span></span>
<span data-ttu-id="26c8c-104">このトピックでは、Wcf-custom を構成する方法について送信している Siebel システムでの送信操作を実行するポートでは、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-104">This topic provides instructions on how to configure WCF-Custom send ports to perform outbound operations on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="26c8c-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="26c8c-105">Prerequisites</span></span>  
<span data-ttu-id="26c8c-106">メンバーであるアカウントでサインイン、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators グループまたは BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="26c8c-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="26c8c-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploying-adapters-for-sending-messages-to-a-siebel-system"></a><span data-ttu-id="26c8c-108">Siebel システムへのメッセージ送信用のアダプターの展開</span><span class="sxs-lookup"><span data-stu-id="26c8c-108">Deploying Adapters for Sending Messages to a Siebel System</span></span>  
 <span data-ttu-id="26c8c-109">Siebel システムを使用して、メッセージを送信するための Wcf-custom 送信ポートを構成する次の手順、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="26c8c-109">Perform the following steps to configure a WCF-Custom send port for sending messages to a Siebel system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 
1.  <span data-ttu-id="26c8c-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="26c8c-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="26c8c-111">コンソール ツリーで  **BizTalk グループ**、順に展開**アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="26c8c-112">展開するアプリケーションを展開し、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-112">Expand the application under which you wish to deploy the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
4.  <span data-ttu-id="26c8c-113">右クリック**送信ポート**、 をポイント**新規**、し、ポートの種類によっては、BizTalk Server と Siebel システム間の通信モードを構成する をポイントします。</span><span class="sxs-lookup"><span data-stu-id="26c8c-113">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the Siebel system.</span></span>  
  
5.  <span data-ttu-id="26c8c-114">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6.  <span data-ttu-id="26c8c-115">**型**ドロップダウン リストで、 **Wcf-custom**  をクリック**構成**です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-115">From the **Type** drop-down list, select **WCF-Custom** and click **Configure**.</span></span>  
  
7.  <span data-ttu-id="26c8c-116">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
    1.  <span data-ttu-id="26c8c-117">をクリックして、**一般的な** タブで、**アドレス (URI)**フィールドは、接続の Siebel システムへの接続に URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-117">Click the **General** tab and in the **Address (URI)** field specify the connection URI to connect to a Siebel system.</span></span> <span data-ttu-id="26c8c-118">接続 URI の詳細については、次を参照してください。 [Siebel システム接続 URI を作成する](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-118">For more information about the connection URI, see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
    2.  <span data-ttu-id="26c8c-119">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="26c8c-120">参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)各操作のアクションの一覧についてはします。</span><span class="sxs-lookup"><span data-stu-id="26c8c-120">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span> <span data-ttu-id="26c8c-121">たとえば、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すアクションは。</span><span class="sxs-lookup"><span data-stu-id="26c8c-121">For example, the action to invoke the Insert operation on the Account business component is:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    3.  <span data-ttu-id="26c8c-122">クリックして、**バインド** タブとの間、**バインディングの種類**ドロップダウン リストで、 **siebelBinding**です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-122">Click the **Binding** tab and from the **Binding Type** drop-down list, select **siebelBinding**.</span></span> <span data-ttu-id="26c8c-123">によって公開されるさまざまなバインドのプロパティを指定することも、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-123">You can also specify the different binding properties exposed by the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="26c8c-124">詳細については、次を参照してください。 [BizTalk Adapter for Siebel のバインドのプロパティについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-124">For more information, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
    4.  <span data-ttu-id="26c8c-125">クリックして、**資格情報**タブし、次のいずれかの操作します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-125">Click the **Credentials** tab and do one of the following:</span></span>  
  
        -   <span data-ttu-id="26c8c-126">選択、**シングル サインオンを使用しない**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-126">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
        -   <span data-ttu-id="26c8c-127">選択、**を使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-127">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
         <span data-ttu-id="26c8c-128">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [Siebel アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-128">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>  
  
    5.  <span data-ttu-id="26c8c-129">戻るには、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-129">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8.  <span data-ttu-id="26c8c-130">**送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**です。</span><span class="sxs-lookup"><span data-stu-id="26c8c-130">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="26c8c-131">手順 4 で静的な一方向送信ポートを選択した場合は、送信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-131">If you chose Static One-Way Send Port in step 4, specify a send pipeline.</span></span> <span data-ttu-id="26c8c-132">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-132">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="26c8c-133">手順 4. で静的な送信請求-応答ポートを選択した場合は、送信を指定し、受信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="26c8c-133">If you chose Static Solicit-Response Port in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="26c8c-134">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-134">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="26c8c-135">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-135">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="26c8c-136">**[OK]**をクリックします。</span><span class="sxs-lookup"><span data-stu-id="26c8c-136">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c8c-137">参照</span><span class="sxs-lookup"><span data-stu-id="26c8c-137">See Also</span></span>  
[<span data-ttu-id="26c8c-138">Siebel アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="26c8c-138">Manually configure a physical port binding to the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)