---
title: Biztalk WCF カスタム アダプターと Siebel アダプターを使用するポートの構成 |Microsoft Docs
description: 作成 wcf-custom 送信ポートと受信ポートを BizTalk server、Siebel eBusiness Applications アダプターを使用するには
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53c5ee07-36ae-474b-9241-8b53c9066ca1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df6d9e9cea34a9bfd95765ad4d37f51fcf55f4ff
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017991"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-siebel-adapter"></a><span data-ttu-id="2de37-103">Wcf-custom アダプターと Siebel アダプターを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="2de37-103">Configure a port using the WCF-custom adapter and Siebel adapter</span></span>
<span data-ttu-id="2de37-104">このトピックでは、Wcf-custom を構成する方法については送信ポートを使用して Siebel システムでの送信操作を実行する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2de37-104">This topic provides instructions on how to configure WCF-Custom send ports to perform outbound operations on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2de37-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="2de37-105">Prerequisites</span></span>  
<span data-ttu-id="2de37-106">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="2de37-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="2de37-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="2de37-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security Rights ](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx).</span></span>
  
## <a name="deploying-adapters-for-sending-messages-to-a-siebel-system"></a><span data-ttu-id="2de37-108">Siebel システムへのメッセージ送信用のアダプターの展開</span><span class="sxs-lookup"><span data-stu-id="2de37-108">Deploying Adapters for Sending Messages to a Siebel System</span></span>  
 <span data-ttu-id="2de37-109">使用して Siebel システムにメッセージを送信するための Wcf-custom 送信ポートを構成するのには、次の手順を実行、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2de37-109">Perform the following steps to configure a WCF-Custom send port for sending messages to a Siebel system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
 
1. <span data-ttu-id="2de37-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="2de37-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="2de37-111">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="2de37-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="2de37-112">展開するアプリケーションを展開し、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2de37-112">Expand the application under which you wish to deploy the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
4. <span data-ttu-id="2de37-113">右クリックし**送信ポート**、 をポイント**新規**、BizTalk Server と Siebel システム間の通信のモードによって構成するポートの種類 をポイントします。</span><span class="sxs-lookup"><span data-stu-id="2de37-113">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the Siebel system.</span></span>  
  
5. <span data-ttu-id="2de37-114">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2de37-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="2de37-115">**型**ドロップダウン リストで、 **Wcf-custom**クリック**構成**します。</span><span class="sxs-lookup"><span data-stu-id="2de37-115">From the **Type** drop-down list, select **WCF-Custom** and click **Configure**.</span></span>  
  
7. <span data-ttu-id="2de37-116">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2de37-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="2de37-117">をクリックして、**全般** タブで、**アドレス (URI)** フィールドは、Siebel システムに接続する接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="2de37-117">Click the **General** tab and in the **Address (URI)** field specify the connection URI to connect to a Siebel system.</span></span> <span data-ttu-id="2de37-118">接続 URI の詳細については、[Siebel システム接続 URI の作成](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de37-118">For more information about the connection URI, see [Create the Siebel system connection URI](../../adapters-and-accelerators/adapter-siebel/create-the-siebel-system-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="2de37-119">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="2de37-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="2de37-120">参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)の各操作のアクションの一覧。</span><span class="sxs-lookup"><span data-stu-id="2de37-120">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span> <span data-ttu-id="2de37-121">たとえば、アカウントのビジネス コンポーネントに対する挿入操作を呼び出すアクションは。</span><span class="sxs-lookup"><span data-stu-id="2de37-121">For example, the action to invoke the Insert operation on the Account business component is:</span></span>  
  
      ```  
      http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
      ```  
  
   3. <span data-ttu-id="2de37-122">をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **siebelBinding**します。</span><span class="sxs-lookup"><span data-stu-id="2de37-122">Click the **Binding** tab and from the **Binding Type** drop-down list, select **siebelBinding**.</span></span> <span data-ttu-id="2de37-123">によって公開されるさまざまなバインドのプロパティを指定することも、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2de37-123">You can also specify the different binding properties exposed by the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="2de37-124">詳細については、[Siebel のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de37-124">For more information, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  
  
   4. <span data-ttu-id="2de37-125">をクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2de37-125">Click the **Credentials** tab and do one of the following:</span></span>  
  
      - <span data-ttu-id="2de37-126">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と Siebel システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="2de37-126">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to a Siebel system.</span></span>  
  
      - <span data-ttu-id="2de37-127">選択、**使用してシングル サインオン**オプション、および、ESSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="2de37-127">Select the **Use Single Sign-On** option, and specify an affiliate ESSO application.</span></span>  
  
        <span data-ttu-id="2de37-128">BizTalk Server に関するセキュリティの詳細については、[Siebel アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2de37-128">For more information about security with respect to BizTalk Server, see [Security with Siebel adapter and BizTalk Server](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md).</span></span>  
  
   5. <span data-ttu-id="2de37-129">戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="2de37-129">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8. <span data-ttu-id="2de37-130">**送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="2de37-130">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="2de37-131">手順 4 で静的な一方向送信ポートを選択した場合は、送信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="2de37-131">If you chose Static One-Way Send Port in step 4, specify a send pipeline.</span></span> <span data-ttu-id="2de37-132">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="2de37-132">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="2de37-133">手順 4. で静的な送信請求-応答ポートを選択した場合は、送信を指定し、受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="2de37-133">If you chose Static Solicit-Response Port in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="2de37-134">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="2de37-134">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="2de37-135">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="2de37-135">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="2de37-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2de37-136">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2de37-137">参照</span><span class="sxs-lookup"><span data-stu-id="2de37-137">See Also</span></span>  
[<span data-ttu-id="2de37-138">Siebel アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="2de37-138">Manually configure a physical port binding to the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)