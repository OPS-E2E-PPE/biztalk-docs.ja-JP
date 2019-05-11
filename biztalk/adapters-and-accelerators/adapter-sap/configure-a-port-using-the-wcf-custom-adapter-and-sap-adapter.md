---
title: Biztalk WCF カスタム アダプターと SAP アダプターを使用してポートの構成 |Microsoft Docs
description: 送信または mySAP アダプターの BizTalk アダプター パック (BAP) を使用して SAP からメッセージを受信する WCF カスタム ポートを作成します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3962456-e9ac-4575-8266-b35e892dd428
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 304fa647f0b50549c6f5779f2579d8d2f473c9ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373857"
---
# <a name="configure-a-port-using-the-wcf-custom-adapter-and-sap-adapter"></a><span data-ttu-id="18c02-103">Wcf-custom アダプターと SAP アダプターを使用してポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="18c02-103">Configure a port using the WCF-custom adapter and SAP adapter</span></span>
<span data-ttu-id="18c02-104">このトピックでは構成 Wcf-custom 送信ポートと受信ポートを使用して SAP システムでの送信および受信の操作を実行する方法を手順については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="18c02-104">This topic provides instructions on how to configure WCF-Custom send and receive ports to perform outbound and inbound operations on SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="18c02-105">前提条件</span><span class="sxs-lookup"><span data-stu-id="18c02-105">Prerequisites</span></span>  
<span data-ttu-id="18c02-106">メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理者または BizTalk Operators グループ。</span><span class="sxs-lookup"><span data-stu-id="18c02-106">Sign in with an account that is a member of the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administrators or BizTalk Operators group.</span></span> <span data-ttu-id="18c02-107">詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最小セキュリティ ユーザー権限](../../core/minimum-security-user-rights.md)します。</span><span class="sxs-lookup"><span data-stu-id="18c02-107">For more detailed information about permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md), and [Minimum Security User Rights](../../core/minimum-security-user-rights.md).</span></span> 
  
## <a name="deploy-adapters-to-send-messages-to-sap"></a><span data-ttu-id="18c02-108">SAP にメッセージを送信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="18c02-108">Deploy adapters to send messages to SAP</span></span>  
<span data-ttu-id="18c02-109">WCF カスタムを構成するのには、次の手順送信ポートを使用して SAP システムにメッセージを送信するための完全な[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="18c02-109">Complete the following steps to configure a WCF-Custom send port for sending messages to SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="18c02-110">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="18c02-110">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="18c02-111">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-111">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="18c02-112">展開するアプリケーションを展開し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="18c02-112">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
4. <span data-ttu-id="18c02-113">右クリックし**送信ポート**、 をポイント**新規**、BizTalk Server と SAP システム間の通信のモードによって構成するポートの種類 をポイントします。</span><span class="sxs-lookup"><span data-stu-id="18c02-113">Right-click **Send Ports**, point to **New**, and point to a type of port you want to configure depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
5. <span data-ttu-id="18c02-114">**送信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、送信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="18c02-114">In the **Send Port Properties** dialog box, on the **General** tab, type a name for the send port.</span></span>  
  
6. <span data-ttu-id="18c02-115">**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-115">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
7. <span data-ttu-id="18c02-116">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18c02-116">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1. <span data-ttu-id="18c02-117">をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドに、SAP システムの接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-117">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the SAP system.</span></span> <span data-ttu-id="18c02-118">接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="18c02-118">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
   2. <span data-ttu-id="18c02-119">**全般** タブで、**アクション**テキスト ボックスに、操作のアクションを入力します。</span><span class="sxs-lookup"><span data-stu-id="18c02-119">On the **General** tab, in the **Action** text box, type the action for the operation.</span></span> <span data-ttu-id="18c02-120">参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)の各操作のアクションの一覧。</span><span class="sxs-lookup"><span data-stu-id="18c02-120">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) for a list of actions for each operation.</span></span> <span data-ttu-id="18c02-121">たとえばに、RFC_CUSTOMER_GET を呼び出すアクションは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="18c02-121">For example, the action to invoke the RFC_CUSTOMER_GET would be:</span></span>  
  
      ```  
      http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
      ```  
  
   3. <span data-ttu-id="18c02-122">をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-122">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="18c02-123">によって公開されるさまざまなバインドのプロパティを指定することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="18c02-123">You can specify the different binding properties exposed by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="18c02-124">バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="18c02-124">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
   4. <span data-ttu-id="18c02-125">をクリックして、**資格情報**タブし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18c02-125">Click the **Credentials** tab and do one of the following:</span></span>  
  
      -   <span data-ttu-id="18c02-126">選択、**シングル サインオンを使用しないでください**オプション、およびユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-126">Select the **Do not use Single Sign-On** option, and specify the user name and password to connect to an SAP system.</span></span>  
  
      -   <span data-ttu-id="18c02-127">選択、**使用してシングル サインオン**オプション、および SSO 関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-127">Select the **Use Single Sign-On** option, and specify an affiliate SSO application.</span></span>  
  
           <span data-ttu-id="18c02-128">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="18c02-128">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>
  
           <span data-ttu-id="18c02-129">戻る、**送信ポートのプロパティ**ダイアログ ボックスで、をクリックして **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="18c02-129">To return to the **Send Port Properties** dialog box, click **OK**.</span></span>  
  
8. <span data-ttu-id="18c02-130">**送信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-130">From the **Send handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
9. <span data-ttu-id="18c02-131">手順 4 で静的な一方向送信ポートを選択した場合は、送信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-131">If you chose Static One-Way Send Port in step 4, specify a send pipeline.</span></span> <span data-ttu-id="18c02-132">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="18c02-132">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
10. <span data-ttu-id="18c02-133">選択した場合**静的な送信請求-応答ポート**手順 4 で、指定の送信および受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="18c02-133">If you chose **Static Solicit-Response Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="18c02-134">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="18c02-134">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
    2.  <span data-ttu-id="18c02-135">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="18c02-135">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="18c02-136">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18c02-136">Click **OK**.</span></span>  
  
## <a name="deploy-adapters-to-receive-messages-from-sap"></a><span data-ttu-id="18c02-137">SAP からメッセージを受信アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="18c02-137">Deploy adapters to receive messages from SAP</span></span>
<span data-ttu-id="18c02-138">WCF カスタムを構成するのには、次の手順を使用して SAP システムからメッセージを受信するためのポートの受信完了、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="18c02-138">Complete the following steps to configure a WCF-Custom receive port for receiving messages from SAP system using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
1. <span data-ttu-id="18c02-139">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="18c02-139">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="18c02-140">コンソール ツリーで、展開**BizTalk グループ**、順に展開**アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-140">In the console tree, expand **BizTalk Group**, and then expand **Applications**.</span></span>  
  
3. <span data-ttu-id="18c02-141">展開するアプリケーションを展開し、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="18c02-141">Expand the application under which you want to deploy the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
4. <span data-ttu-id="18c02-142">右クリックして**受信ポート**、 をポイント**新規**、 をクリック**一方向の受信ポート**または**要求-応答受信ポート**に応じて、BizTalk Server と SAP システム間の通信のモードです。</span><span class="sxs-lookup"><span data-stu-id="18c02-142">Right-click **Receive Ports**, point to **New**, and click **One-way Receive Port** or **Request Response Receive Port** depending on the mode of communication between BizTalk Server and the SAP system.</span></span>  
  
5. <span data-ttu-id="18c02-143">**受信ポートのプロパティ** ダイアログ ボックスで、**全般** タブで、受信ポートの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="18c02-143">In the **Receive Port Properties** dialog box, on the **General** tab, type a name for the receive port.</span></span>  
  
6. <span data-ttu-id="18c02-144">**受信場所**] タブで [**新規**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-144">On the **Receive Locations** tab, click **New**.</span></span> <span data-ttu-id="18c02-145">**受信場所のプロパティ** ダイアログ ボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="18c02-145">The **Receive Location Properties** dialog box appears.</span></span>  
  
7. <span data-ttu-id="18c02-146">**受信場所のプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18c02-146">In the **Receive Location Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="18c02-147">受信場所の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-147">Specify a name for the receive location.</span></span>  
  
   2.  <span data-ttu-id="18c02-148">**型**ドロップダウン リストで、 **Wcf-custom**、 をクリックし、**構成**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-148">From the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
8. <span data-ttu-id="18c02-149">**Wcf-custom トランスポートのプロパティ** ダイアログ ボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18c02-149">In the **WCF-Custom Transport Properties** dialog box, do the following:</span></span>  
  
   1.  <span data-ttu-id="18c02-150">をクリックして、**全般** タブで、し、**アドレス (URI)** フィールドに、SAP システムの接続 URI を指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-150">Click the **General** tab, and in the **Address (URI)** field, specify the connection URI for the SAP system.</span></span> <span data-ttu-id="18c02-151">接続 URI の詳細については、次を参照してください。 [SAP システム接続 URI の作成](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)です。</span><span class="sxs-lookup"><span data-stu-id="18c02-151">For more information about the connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
   2.  <span data-ttu-id="18c02-152">をクリックして、**バインド** タブとの間、**バインドの種類**ドロップダウン リストで、 **sapBinding**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-152">Click the **Binding** tab, and from the **Binding Type** drop-down list, select **sapBinding**.</span></span> <span data-ttu-id="18c02-153">バインド プロパティの詳細については、次を参照してください。 [mySAP Business Suite のバインドのプロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="18c02-153">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  
  
   3.  <span data-ttu-id="18c02-154">をクリックして、**他**タブをクリックし、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="18c02-154">Click the **Others** tab, and do one of the following:</span></span>  
  
       -   <span data-ttu-id="18c02-155">選択**ユーザー アカウント**ユーザー名と SAP システムへの接続にパスワードを指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-155">Select **User account**, and specify the user name and password to connect to an SAP system.</span></span>  
  
       -   <span data-ttu-id="18c02-156">選択**関連アプリケーションから資格情報を Get**オプション、および関連アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-156">Select **Get credentials from affiliate application** option, and specify an affiliate application.</span></span>  
  
            <span data-ttu-id="18c02-157">BizTalk Server に関するセキュリティの詳細については、次を参照してください。 [SAP アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md)します。</span><span class="sxs-lookup"><span data-stu-id="18c02-157">For more information about security with respect to BizTalk Server, see [Security with the SAP adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sap/security-with-the-sap-adapter-and-biztalk-server.md).</span></span>
  
            <span data-ttu-id="18c02-158">をクリックして**OK**に戻る、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="18c02-158">Click **OK** to return to the **Receive Location Properties** dialog box.</span></span>  
  
9. <span data-ttu-id="18c02-159">**受信ハンドラー**ドロップダウン リストで、 **BizTalkServerApplication**します。</span><span class="sxs-lookup"><span data-stu-id="18c02-159">From the **Receive handler** drop-down list, select **BizTalkServerApplication**.</span></span>  
  
10. <span data-ttu-id="18c02-160">選択した場合**一方向の受信ポート**手順 4 で、受信パイプラインを指定します。</span><span class="sxs-lookup"><span data-stu-id="18c02-160">If you chose **One-way Receive Port** in step 4, specify a receive pipeline.</span></span> <span data-ttu-id="18c02-161">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="18c02-161">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
11. <span data-ttu-id="18c02-162">選択した場合**要求-応答受信ポート**手順 4 で、指定の送信および受信パイプライン。</span><span class="sxs-lookup"><span data-stu-id="18c02-162">If you chose **Request Response Receive Port** in step 4, specify send and receive pipelines.</span></span>  
  
    1.  <span data-ttu-id="18c02-163">**受信パイプライン**ドロップダウン リストで、[xmlreceive] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="18c02-163">From the **Receive pipeline** drop-down list, select the pipeline corresponding to XMLReceive.</span></span>  
  
    2.  <span data-ttu-id="18c02-164">**送信パイプライン**ドロップダウン リストで、[xmltransmit] に対応するパイプラインを選択します。</span><span class="sxs-lookup"><span data-stu-id="18c02-164">From the **Send pipeline** drop-down list, select the pipeline corresponding to XMLTransmit.</span></span>  
  
12. <span data-ttu-id="18c02-165">クリックして**OK i**n、**受信場所のプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="18c02-165">Click **OK i**n the **Receive Location Properties** dialog box.</span></span>  
  
13. <span data-ttu-id="18c02-166">クリックして**OK**で、**受信ポートのプロパティ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="18c02-166">Click **OK** in the **Receive Port Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18c02-167">参照</span><span class="sxs-lookup"><span data-stu-id="18c02-167">See Also</span></span>  
[<span data-ttu-id="18c02-168">SAP アダプターを物理ポートのバインドを手動で構成します。</span><span class="sxs-lookup"><span data-stu-id="18c02-168">Manually configure a physical port binding to the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)