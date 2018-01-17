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
ms.openlocfilehash: 8c742d21dd2f2e1d95f697beea3d5d5dfa0461d2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a><span data-ttu-id="abbce-102">手順 14: Web サービスとしてのオーケストレーションを公開します。</span><span class="sxs-lookup"><span data-stu-id="abbce-102">Step 14: Publish the Orchestration as a Web Service</span></span>
<span data-ttu-id="abbce-103">このステップでは、BizTalk Web サービス公開ウィザードを使用して、オーケストレーションを Web サービスとして公開します。</span><span class="sxs-lookup"><span data-stu-id="abbce-103">In this step, you use the BizTalk Web Services Publishing Wizard to publish your orchestration as a Web service.</span></span>  
  
 <span data-ttu-id="abbce-104">Web サービスとしてのオーケストレーションを発行する前に [biztalkserverisolatedhost] のログオン アカウントは、BizTalk データベースにアクセス権を持つため、BizTalk 分離ホスト ユーザー グループの一部ことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="abbce-104">Before publishing the orchestration as a Web service, you need to ensure that the logon account for BizTalkServerIsolatedHost is part of the BizTalk Isolated Host Users group, so it has access to the BizTalk databases.</span></span> <span data-ttu-id="abbce-105">これは、機能は、このチュートリアルでは、Web サービス公開ウィザードによって作成される SOAPReceivePort 受信場所の受信ハンドラーが BizTalkServerIsolatedHost、BizTalkServerApplication ではないため必要です。</span><span class="sxs-lookup"><span data-stu-id="abbce-105">This is necessary because the receive handler for the SOAPReceivePort receive location that is created by the Web Service Publishing Wizard for this tutorial is BizTalkServerIsolatedHost, not BizTalkServerApplication.</span></span> <span data-ttu-id="abbce-106">受信ハンドラーは BizTalkServerIsolatedHost は、SOAP アダプターは BizTalk プロセスではなく、IIS プロセスで実行されるためです。</span><span class="sxs-lookup"><span data-stu-id="abbce-106">The receive handler is BizTalkServerIsolatedHost because the SOAP adapter runs under the IIS process, not the BizTalk process.</span></span>  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a><span data-ttu-id="abbce-107">アクセスするために、SOAPReceivePort の特権の受信場所</span><span class="sxs-lookup"><span data-stu-id="abbce-107">To ensure access privileges for the SOAPReceivePort receive location</span></span>  
  
1.  <span data-ttu-id="abbce-108">BizTalk Server 管理コンソールで、[**ホスト インスタンス**で、**プラットフォームの設定**] ノードを右クリックして**BizTalkServerIsolatedHost**をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-108">In BizTalk Server Administration Console, under **Host Instances** in the **Platform Settings** node, right-click **BizTalkServerIsolatedHost**, and then click **Properties**.</span></span> <span data-ttu-id="abbce-109">[プロパティ] ダイアログ ボックスで、**構成**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-109">In the Properties dialog box, click **Configure**.</span></span> <span data-ttu-id="abbce-110">注、**ログオン**アカウント。</span><span class="sxs-lookup"><span data-stu-id="abbce-110">Note the **Logon** account.</span></span>  
  
2.  <span data-ttu-id="abbce-111">コンピューターの管理 ダイアログ ボックスで **グループ**で、**ローカル ユーザーとグループ** ノードをダブルクリック**BizTalk 分離ホスト ユーザー**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-111">In the Computer Management dialog box, under **Groups** in the **Local Users and Groups** node, double-click **BizTalk Isolated Host Users**.</span></span> <span data-ttu-id="abbce-112">ログオン アカウントする場合**BizTalkServerIsolatedHost**のメンバーではない**BizTalkServerIsolatedHost**グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="abbce-112">If the logon account for **BizTalkServerIsolatedHost** is not a member of **BizTalkServerIsolatedHost**, add it to the group.</span></span>  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a><span data-ttu-id="abbce-113">BizTalk Web サービス公開ウィザードを実行するには</span><span class="sxs-lookup"><span data-stu-id="abbce-113">To run the BizTalk Web Services Publishing Wizard</span></span>  
  
1.  <span data-ttu-id="abbce-114">ソリューション エクスプ ローラーの Visual Studio で、**ソリューション 'BTAHL7V22Common'**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-114">In Solution Explorer of Visual Studio, click **Solution 'BTAHL7V22Common'**.</span></span> <span data-ttu-id="abbce-115">**ツール** メニューのをクリックして**BizTalk Web サービス公開ウィザード**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-115">On the **Tools** menu, click **BizTalk Web Services Publishing Wizard**.</span></span>  
  
2.  <span data-ttu-id="abbce-116">**BizTalk Web サービス公開ウィザード**の**へようこそ**  ページで、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-116">In the **BizTalk Web Services Publishing Wizard**, on the **Welcome** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="abbce-117">**Web サービスの作成**  ページで、 **BizTalk オーケストレーション web サービスとして発行**, 、 をクリックし、 **次**します。</span><span class="sxs-lookup"><span data-stu-id="abbce-117">On the **Create Web Service** page, select **Publish BizTalk orchestrations as web services**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="abbce-118">**BizTalk アセンブリ**] ページの [、 **BizTalk アセンブリ ファイル (\\*.dll)**フィールドを参照または入力 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**、] をクリックして**BTAHL7 Project.dll**をクリックして**開く**、順にクリック**[次へ**.</span><span class="sxs-lookup"><span data-stu-id="abbce-118">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\\*.dll)** field, browse to or type **\<*drive*\>:\Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**, click **BTAHL7 Project.dll**, click **Open**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="abbce-119">**オーケストレーションとポート** ページで、すべてのノードが選択されていることを確認し、をクリックして**次**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-119">On the **Orchestrations and Ports** page, ensure that all nodes are selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="abbce-120">**Web サービスのプロパティ** ページの**web サービスのターゲット名前空間**、型**http://localhost**、順にクリック**次**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-120">On the **Web Service Properties** page, for **Target namespace of web service**, type **http://localhost**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="abbce-121">**Web サービス プロジェクト**] ページで、[ **web サービスへの匿名アクセスを許可する**と**次のアプリケーションに受信場所を作成する BizTalk**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-121">On the **Web Service Project** page, select **Allow anonymous access to web service** and **Create BizTalk receive locations in the following application**.</span></span> <span data-ttu-id="abbce-122">選択**BizTalk アプリケーション 1**アプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="abbce-122">Select **BizTalk Application 1** for the application.</span></span> <span data-ttu-id="abbce-123">既定の保持、**場所**フィールドです。</span><span class="sxs-lookup"><span data-stu-id="abbce-123">Keep the default in the **Location** field.</span></span> <span data-ttu-id="abbce-124">をクリックして**次**を既定のプロジェクトの場所を受け入れるようにします。</span><span class="sxs-lookup"><span data-stu-id="abbce-124">Click **Next** to accept the default project location.</span></span>  
  
8.  <span data-ttu-id="abbce-125">**Web サービス プロジェクトの概要** ページで、をクリックして**作成**ASP.NET Web サービス プロジェクトを生成します。</span><span class="sxs-lookup"><span data-stu-id="abbce-125">On the **Web Service Project Summary** page, click **Create** to generate the ASP.NET Web Service project.</span></span>  
  
9. <span data-ttu-id="abbce-126">**[完了]** をクリックして、ウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="abbce-126">Click **Finish** to close the wizard.</span></span>  
  
10. <span data-ttu-id="abbce-127">BizTalk Server 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="abbce-127">Open the BizTalk Server Administration Console.</span></span> <span data-ttu-id="abbce-128">コンソールで、展開**BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開**アプリケーション**、順に展開**BizTalk アプリケーション 1**.</span><span class="sxs-lookup"><span data-stu-id="abbce-128">In the console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
11. <span data-ttu-id="abbce-129">をクリックして**受信場所**を右クリックして**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、クリックして**プロパティ**.</span><span class="sxs-lookup"><span data-stu-id="abbce-129">Click **Receive Locations**, right-click **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, and then click **Properties**.</span></span>  
  
12. <span data-ttu-id="abbce-130">受信場所のプロパティ ダイアログ ボックスで、**受信パイプライン** **Microsoft.BizTalk.DefaultPipelines.XMLReceive**クリックしてドロップダウン リストから**OK**.</span><span class="sxs-lookup"><span data-stu-id="abbce-130">In the Receive Location Properties dialog box, click **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLReceive** from the drop-down list, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="abbce-131">右クリック**WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**、クリックして**を有効にする**です。</span><span class="sxs-lookup"><span data-stu-id="abbce-131">Right-click **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, and then click **Enable**.</span></span>  
  
 <span data-ttu-id="abbce-132">進みます[手順 15: 構成、送信ポートと受信ポート](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)です。</span><span class="sxs-lookup"><span data-stu-id="abbce-132">Proceed to [Step 15: Configure the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbce-133">参照</span><span class="sxs-lookup"><span data-stu-id="abbce-133">See Also</span></span>  
 [<span data-ttu-id="abbce-134">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="abbce-134">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)