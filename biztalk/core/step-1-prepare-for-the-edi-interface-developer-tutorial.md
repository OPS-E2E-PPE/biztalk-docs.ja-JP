---
title: 手順 1:EDI インターフェイス開発チュートリアルの準備 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9be1bddf-d673-4054-87f5-0205b8b5cc0d
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d01678bb342909d13beb15141765b789b12a0687
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392801"
---
# <a name="step-1-prepare-for-the-edi-interface-developer-tutorial"></a><span data-ttu-id="fee65-102">手順 1:EDI インターフェイス開発チュートリアルを準備します。</span><span class="sxs-lookup"><span data-stu-id="fee65-102">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>
<span data-ttu-id="fee65-103">![手順 9 の 1](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")</span><span class="sxs-lookup"><span data-stu-id="fee65-103">![Step 1 of 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-1of9.gif "Step_1of9")</span></span>  
  
 <span data-ttu-id="fee65-104">EDI インターフェイス開発チュートリアルは、1 台のコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="fee65-104">The EDI Interface Development tutorial is run on a single computer.</span></span> <span data-ttu-id="fee65-105">チュートリアルを準備するには、インストールして構成する必要があります[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]」の説明に従って[BizTalk Server 2013 および 2013 R2 のインストールの概要](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)します。</span><span class="sxs-lookup"><span data-stu-id="fee65-105">To prepare for the tutorial, you must install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] as described in [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span> <span data-ttu-id="fee65-106">BizTalk EDI アプリケーションへの参照を追加することも必要があります。</span><span class="sxs-lookup"><span data-stu-id="fee65-106">You must also add reference to the BizTalk EDI Application</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fee65-107">このチュートリアルが機能するには、IIS 7.5 または IIS 8 を使用するプラットフォームで実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fee65-107">For this tutorial to work, it must be run on a platform using IIS 7.5 or IIS 8.</span></span>  
  
 <span data-ttu-id="fee65-108">EDI インターフェイス開発チュートリアルに必要なファイルにある、 [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]sdk \edi Interface Developer Tutorial フォルダ。</span><span class="sxs-lookup"><span data-stu-id="fee65-108">The files required for the EDI Interface Developer tutorial are located in the [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial folder.</span></span> <span data-ttu-id="fee65-109">フォルダーおよびチュートリアルに必要なファイルは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="fee65-109">The folders and files required for the tutorial are as follows:</span></span>  
  
|<span data-ttu-id="fee65-110">Folder\File</span><span class="sxs-lookup"><span data-stu-id="fee65-110">Folder\File</span></span>|<span data-ttu-id="fee65-111">目的</span><span class="sxs-lookup"><span data-stu-id="fee65-111">Purpose</span></span>|  
|------------------|-------------|  
|<span data-ttu-id="fee65-112">\SDK\EDI Interface Developer Tutorial\EDI Inbound Processing.sln</span><span class="sxs-lookup"><span data-stu-id="fee65-112">\SDK\EDI Interface Developer Tutorial\EDI Inbound Processing.sln</span></span>|<span data-ttu-id="fee65-113">このメッセージング シナリオを作成する Visual Studio で使用するソリューション ファイル</span><span class="sxs-lookup"><span data-stu-id="fee65-113">The solution file that you use in Visual Studio to create this messaging scenario</span></span>|  
|<span data-ttu-id="fee65-114">\SDK\EDI Interface Developer Tutorial\keyfile.snk</span><span class="sxs-lookup"><span data-stu-id="fee65-114">\SDK\EDI Interface Developer Tutorial\keyfile.snk</span></span>|<span data-ttu-id="fee65-115">ソリューション ファイルに指定されたアセンブリ キー ファイル</span><span class="sxs-lookup"><span data-stu-id="fee65-115">The assembly key file specified for the solution file</span></span>|  
|<span data-ttu-id="fee65-116">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt</span><span class="sxs-lookup"><span data-stu-id="fee65-116">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\SamplePO.txt</span></span>|<span data-ttu-id="fee65-117">ソリューションのテストに使用するサンプル メッセージ ファイル (バージョン 4010 850)</span><span class="sxs-lookup"><span data-stu-id="fee65-117">The sample message file (version 4010 850) that you use to test the solution</span></span>|  
|<span data-ttu-id="fee65-118">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm</span><span class="sxs-lookup"><span data-stu-id="fee65-118">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\Inbound4010850_to_OrderFile.btm</span></span>|<span data-ttu-id="fee65-119">850 メッセージ データを注文システムで必要な形式に変換する BizTalk マップ。</span><span class="sxs-lookup"><span data-stu-id="fee65-119">The BizTalk map that converts the 850 message data into the format required by the Order System.</span></span>|  
|<span data-ttu-id="fee65-120">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp</span><span class="sxs-lookup"><span data-stu-id="fee65-120">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\SendOrderFilePipeline.btp</span></span>|<span data-ttu-id="fee65-121">注文システムにメッセージを送信するためのテスト メッセージを処理する送信パイプラインです。</span><span class="sxs-lookup"><span data-stu-id="fee65-121">The send pipeline that processes the test message for sending the message to the order system.</span></span>|  
|<span data-ttu-id="fee65-122">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\X12_00401_850.xsd</span><span class="sxs-lookup"><span data-stu-id="fee65-122">\SDK\EDI Interface Developer Tutorial\ Inbound_EDI\X12_00401_850.xsd</span></span>|<span data-ttu-id="fee65-123">テスト メッセージの 850 スキーマです。</span><span class="sxs-lookup"><span data-stu-id="fee65-123">The 850 schema for the test message.</span></span>|  
<span data-ttu-id="fee65-124">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM</span><span class="sxs-lookup"><span data-stu-id="fee65-124">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\fromTHEM</span></span>|<span data-ttu-id="fee65-125">Fabrikam から受信 850 メッセージの受信場所フォルダー</span><span class="sxs-lookup"><span data-stu-id="fee65-125">Folder where the inbound 850 message is received from Fabrikam</span></span>|  
|<span data-ttu-id="fee65-126">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem</span><span class="sxs-lookup"><span data-stu-id="fee65-126">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toOrderSystem</span></span>|<span data-ttu-id="fee65-127">フォルダーを送信 850 メッセージの送信先、注文システムのバック エンド アプリケーションを表す</span><span class="sxs-lookup"><span data-stu-id="fee65-127">Folder where the outbound 850 message is sent to, representing your Order System back-end application</span></span>|  
|<span data-ttu-id="fee65-128">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997</span><span class="sxs-lookup"><span data-stu-id="fee65-128">\SDK\EDI Interface Developer Tutorial\ ProcessEDI_TestLocations\Scenario A\toTHEM_997</span></span>|<span data-ttu-id="fee65-129">フォルダーを 997 受信確認の送信先 Fabrikam を表す</span><span class="sxs-lookup"><span data-stu-id="fee65-129">Folder where the 997 acknowledgment is sent to, representing Fabrikam</span></span>|  
  
## <a name="prerequisites"></a><span data-ttu-id="fee65-130">前提条件</span><span class="sxs-lookup"><span data-stu-id="fee65-130">Prerequisites</span></span>  
 <span data-ttu-id="fee65-131">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fee65-131">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-add-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="fee65-132">BizTalk EDI アプリケーションへの参照を追加するには</span><span class="sxs-lookup"><span data-stu-id="fee65-132">To add reference to the BizTalk EDI Application</span></span>  
  
1. <span data-ttu-id="fee65-133">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、、**アプリケーション**ノードで、BizTalk アプリケーション 1 などの edi で使用するアプリケーションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="fee65-133">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, under the **Applications** node, right-click the application that you want to use for EDI, such as BizTalk Application 1.</span></span> <span data-ttu-id="fee65-134">をポイント**追加**、し、[参照] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fee65-134">Point to **Add**, and then click References.</span></span>  
  
2. <span data-ttu-id="fee65-135">**アプリケーション参照の追加**ダイアログ ボックスで、 **BizTalk EDI アプリケーション**、 をクリックし、 **OK**。</span><span class="sxs-lookup"><span data-stu-id="fee65-135">In the **Add Application Reference** dialog box, select **BizTalk EDI Application**, and then click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fee65-136">次の手順</span><span class="sxs-lookup"><span data-stu-id="fee65-136">Next Steps</span></span>  
 <span data-ttu-id="fee65-137">作成および」の説明に従って、Inbound_EDI アセンブリを配置する[手順 2。更新し、チュートリアルのソリューションを展開](../core/step-2-update-and-deploy-the-tutorial-solution.md)します。</span><span class="sxs-lookup"><span data-stu-id="fee65-137">You build and deploy the Inbound_EDI assembly, as described in [Step 2: Update and Deploy the Tutorial Solution](../core/step-2-update-and-deploy-the-tutorial-solution.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee65-138">参照</span><span class="sxs-lookup"><span data-stu-id="fee65-138">See Also</span></span>  
 [<span data-ttu-id="fee65-139">チュートリアル 2: EDI インターフェイス開発チュートリアル</span><span class="sxs-lookup"><span data-stu-id="fee65-139">Tutorial 2: EDI Interface Developer Tutorial</span></span>](../core/tutorial-2-edi-interface-developer-tutorial.md)