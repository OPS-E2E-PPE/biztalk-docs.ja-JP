---
title: "手順 14: Web サービスとしてのオーケストレーションの公開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- publishing, orchestrations
- Web services, orchestrations
- message enrichment tutorial, orchestrations
- publishing, Web services
- message enrichment tutorial, Web services
ms.assetid: 8f29a7be-a679-4ca6-a648-35338d9e9e98
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd7707ded0951eb1141368a91e7fe8f533e8241a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a><span data-ttu-id="0722a-102">手順 14: Web サービスとしてのオーケストレーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="0722a-102">Step 14: Publish the Orchestration as a Web Service</span></span>
<span data-ttu-id="0722a-103">このステップでは、BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開します。</span><span class="sxs-lookup"><span data-stu-id="0722a-103">In this step, you use the BizTalk Web Services Publishing Wizard to publish your orchestration as a Web service.</span></span>  
  
 <span data-ttu-id="0722a-104">Web サービスとしてのオーケストレーションを発行する前に [biztalkserverisolatedhost] のログオン アカウントは、BizTalk データベースにアクセス権を持つため、BizTalk 分離ホスト ユーザー グループの一部ことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0722a-104">Before publishing the orchestration as a Web service, you need to ensure that the logon account for BizTalkServerIsolatedHost is part of the BizTalk Isolated Host Users group, so it has access to the BizTalk databases.</span></span> <span data-ttu-id="0722a-105">これは、機能は、このチュートリアルでは、Web サービス公開ウィザードによって作成される SOAPReceivePort 受信場所の受信ハンドラーが BizTalkServerIsolatedHost、BizTalkServerApplication ではないため必要です。</span><span class="sxs-lookup"><span data-stu-id="0722a-105">This is necessary because the receive handler for the SOAPReceivePort receive location that is created by the Web Service Publishing Wizard for this tutorial is BizTalkServerIsolatedHost, not BizTalkServerApplication.</span></span> <span data-ttu-id="0722a-106">受信ハンドラーは BizTalkServerIsolatedHost は、SOAP アダプターは BizTalk プロセスではなく、IIS プロセスで実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="0722a-106">The receive handler is BizTalkServerIsolatedHost because the SOAP adapter runs under the IIS process, not the BizTalk process.</span></span>  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a><span data-ttu-id="0722a-107">アクセスするために、SOAPReceivePort の特権の受信場所</span><span class="sxs-lookup"><span data-stu-id="0722a-107">To ensure access privileges for the SOAPReceivePort receive location</span></span>  
  
1.  <span data-ttu-id="0722a-108">BizTalk Server 管理コンソールで、[**ホスト インスタンス**で、**プラットフォームの設定**] ノードを右クリックして**BizTalkServerIsolatedHost**をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-108">In BizTalk Server Administration Console, under **Host Instances** in the **Platform Settings** node, right-click **BizTalkServerIsolatedHost**, and then click **Properties**.</span></span> <span data-ttu-id="0722a-109">[プロパティ] ダイアログ ボックスで、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-109">In the Properties dialog box, click **Configure**.</span></span> <span data-ttu-id="0722a-110">注、**ログオン**アカウント。</span><span class="sxs-lookup"><span data-stu-id="0722a-110">Note the **Logon** account.</span></span>  
  
2.  <span data-ttu-id="0722a-111">コンピューターの管理 ダイアログ ボックスで **グループ**で、**ローカル ユーザーとグループ** ノードをダブルクリック**BizTalk 分離ホスト ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-111">In the Computer Management dialog box, under **Groups** in the **Local Users and Groups** node, double-click **BizTalk Isolated Host Users**.</span></span> <span data-ttu-id="0722a-112">ログオン アカウントする場合**BizTalkServerIsolatedHost**のメンバーではない**BizTalkServerIsolatedHost**グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="0722a-112">If the logon account for **BizTalkServerIsolatedHost** is not a member of **BizTalkServerIsolatedHost**, add it to the group.</span></span>  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a><span data-ttu-id="0722a-113">BizTalk Web サービス公開ウィザードを実行するには</span><span class="sxs-lookup"><span data-stu-id="0722a-113">To run the BizTalk Web Services Publishing Wizard</span></span>  
  
1.  <span data-ttu-id="0722a-114">ソリューション エクスプ ローラーの Visual Studio で、**ソリューション 'BTAHL7V22Common'**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-114">In Solution Explorer of Visual Studio, click **Solution 'BTAHL7V22Common'**.</span></span> <span data-ttu-id="0722a-115">**ツール** メニューのをクリックして**BizTalk Web サービス公開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-115">On the **Tools** menu, click **BizTalk Web Services Publishing Wizard**.</span></span>  
  
2.  <span data-ttu-id="0722a-116">**BizTalk Web サービス公開ウィザード**の**へようこそ**  ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-116">In the **BizTalk Web Services Publishing Wizard**, on the **Welcome** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="0722a-117">**Web サービスの作成**] ページで、[ **BizTalk オーケストレーション web サービスとして公開**、クリックして**[次へ]**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-117">On the **Create Web Service** page, select **Publish BizTalk orchestrations as web services**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="0722a-118">**BizTalk アセンブリ** ページの 、 **BizTalk アセンブリ ファイル (\*.dll)**フィールドを参照または入力  **\<*ドライブ*>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**、 をクリックして**BTAHL7 Project.dll**、 をクリックして**開く**、順にクリック**次**.</span><span class="sxs-lookup"><span data-stu-id="0722a-118">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\*.dll)** field, browse to or type **\<*drive*>:\Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**, click **BTAHL7 Project.dll**, click **Open**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="0722a-119">**オーケストレーションとポート** ページで、すべてのノードが選択されていることを確認し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-119">On the **Orchestrations and Ports** page, ensure that all nodes are selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="0722a-120">**Web サービスのプロパティ** ページの**web サービスのターゲット名前空間**、型**http://localhost**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-120">On the **Web Service Properties** page, for **Target namespace of web service**, type **http://localhost**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="0722a-121">**Web サービス プロジェクト**] ページで、[ **web サービスへの匿名アクセスを許可する**と**次のアプリケーションに受信場所を作成する BizTalk**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-121">On the **Web Service Project** page, select **Allow anonymous access to web service** and **Create BizTalk receive locations in the following application**.</span></span> <span data-ttu-id="0722a-122">選択**BizTalk アプリケーション 1**アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="0722a-122">Select **BizTalk Application 1** for the application.</span></span> <span data-ttu-id="0722a-123">既定の保持、**場所**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="0722a-123">Keep the default in the **Location** field.</span></span> <span data-ttu-id="0722a-124">をクリックして**次**を既定のプロジェクトの場所を受け入れるようにします。</span><span class="sxs-lookup"><span data-stu-id="0722a-124">Click **Next** to accept the default project location.</span></span>  
  
8.  <span data-ttu-id="0722a-125">**Web サービス プロジェクトの概要** ページで、をクリックして**作成**ASP.NET Web サービス プロジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="0722a-125">On the **Web Service Project Summary** page, click **Create** to generate the ASP.NET Web Service project.</span></span>  
  
9. <span data-ttu-id="0722a-126">**[完了]** をクリックして、ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="0722a-126">Click **Finish** to close the wizard.</span></span>  
  
10. <span data-ttu-id="0722a-127">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0722a-127">Open the BizTalk Server Administration Console.</span></span> <span data-ttu-id="0722a-128">コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**.</span><span class="sxs-lookup"><span data-stu-id="0722a-128">In the console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
11. <span data-ttu-id="0722a-129">をクリックして**受信場所**を右クリックして**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、クリックして**プロパティ**.</span><span class="sxs-lookup"><span data-stu-id="0722a-129">Click **Receive Locations**, right-click **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, and then click **Properties**.</span></span>  
  
12. <span data-ttu-id="0722a-130">受信場所のプロパティ ダイアログ ボックスで、**受信パイプライン** **Microsoft.BizTalk.DefaultPipelines.XMLReceive**クリックしてドロップダウン リストから**OK**.</span><span class="sxs-lookup"><span data-stu-id="0722a-130">In the Receive Location Properties dialog box, click **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLReceive** from the drop-down list, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="0722a-131">右クリック**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="0722a-131">Right-click **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, and then click **Enable**.</span></span>  
  
 <span data-ttu-id="0722a-132">進みます[手順 15: 構成、送信ポートと受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="0722a-132">Proceed to [Step 15: Configure the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0722a-133">参照</span><span class="sxs-lookup"><span data-stu-id="0722a-133">See Also</span></span>  
 [<span data-ttu-id="0722a-134">メッセージの強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="0722a-134">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)