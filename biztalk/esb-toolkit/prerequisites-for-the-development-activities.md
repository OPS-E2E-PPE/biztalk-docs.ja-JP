---
title: 開発活動の前提条件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c91405-f9a4-4676-b5c5-fe90b3b51b45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c81bd4acffed295de12e8b123451ae1eb77864f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65301783"
---
# <a name="prerequisites-for-the-development-activities"></a><span data-ttu-id="2d4e3-102">開発活動の前提条件</span><span class="sxs-lookup"><span data-stu-id="2d4e3-102">Prerequisites for the Development Activities</span></span>
<span data-ttu-id="2d4e3-103">このセクションの一部として含まれる開発作業の手順を完了するための環境を準備する方法を説明します、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-103">This section describes how to prepare your environment to complete the steps in the development activities that are included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="2d4e3-104">開発作業の手順のいずれかの操作を行う前に、次のセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-104">Complete the following setup before you attempt any of the procedures in the development activities:</span></span>  
  
## <a name="set-up-your-computer-to-perform-the-procedures-in-the-biztalk-esb-toolkit-development-activities"></a><span data-ttu-id="2d4e3-105">BizTalk ESB Toolkit の開発アクティビティで手順を実行するコンピューターをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-105">Set up your computer to perform the procedures in the BizTalk ESB Toolkit development activities</span></span>  
  
1.  <span data-ttu-id="2d4e3-106">インストールし、スケジュールのサンプル アプリケーション、動的解決サンプル アプリケーション、および複数の Web サービスのサンプル アプリケーションをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-106">Install and deploy the Itinerary sample application, the Dynamic Resolution sample application, and the Multiple Web Services sample application.</span></span> <span data-ttu-id="2d4e3-107">インストールして、これらのアプリケーションの展開についての詳細については、次を参照してください。 [BizTalk ESB Toolkit のサンプル アプリケーション](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-107">For more information about installing and deploying these applications, see [BizTalk ESB Toolkit Sample Applications](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span></span>  
  
2.  <span data-ttu-id="2d4e3-108">UDDI 発行元のユーティリティを実行します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-108">Run the UDDI Publisher Utility.</span></span>  
  
3.  <span data-ttu-id="2d4e3-109">開発用コンピューター上の Windows エクスプ ローラーで、次のパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-109">On your development computer, in Windows Explorer, create the following paths:</span></span>  
  
    -   <span data-ttu-id="2d4e3-110">C:\HowTos</span><span class="sxs-lookup"><span data-stu-id="2d4e3-110">C:\HowTos</span></span>  
  
    -   <span data-ttu-id="2d4e3-111">C:\HowTos\Itineraries</span><span class="sxs-lookup"><span data-stu-id="2d4e3-111">C:\HowTos\Itineraries</span></span>  
  
    -   <span data-ttu-id="2d4e3-112">C:\HowTos\DropFolder</span><span class="sxs-lookup"><span data-stu-id="2d4e3-112">C:\HowTos\DropFolder</span></span>  
  
    -   <span data-ttu-id="2d4e3-113">C:\HowTos\Out</span><span class="sxs-lookup"><span data-stu-id="2d4e3-113">C:\HowTos\Out</span></span>  
  
4.  <span data-ttu-id="2d4e3-114">BizTalk Server サービス アカウントがあることを確認**フルコントロール**C:\HowTos ディレクトリ構造へのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-114">Ensure that your BizTalk Server service account has **Full Control** permissions to the C:\HowTos directory structure.</span></span>  
  
5.  <span data-ttu-id="2d4e3-115">Microsoft BizTalk Server サービス アカウントがあることを確認**書き込み**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out へのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-115">Ensure that your Microsoft BizTalk Server service account has **Write** permissions to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out.</span></span>  
  
6.  <span data-ttu-id="2d4e3-116">次のテスト メッセージを C:\HowTos フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-116">Copy the following test message to the C:\HowTos folder:</span></span>  
  
    -   <span data-ttu-id="2d4e3-117">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml</span><span class="sxs-lookup"><span data-stu-id="2d4e3-117">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml</span></span>  
  
7.  <span data-ttu-id="2d4e3-118">C:\HowTos フォルダーでは、次の場所にある、旅行プランのテスト用クライアント アプリケーションへのショートカットを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-118">In the C:\HowTos folder, create a shortcut to the Itinerary Test Client application, found at the following location:</span></span>  
  
    -   <span data-ttu-id="2d4e3-119">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug\ESB.Itinerary.Test.exe</span><span class="sxs-lookup"><span data-stu-id="2d4e3-119">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug\ESB.Itinerary.Test.exe</span></span>  
  
## <a name="create-the-visual-studio-solution"></a><span data-ttu-id="2d4e3-120">Visual Studio ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-120">Create the Visual Studio solution</span></span>  
  
1.  <span data-ttu-id="2d4e3-121">Visual Studio で、ファイル メニューをポイント**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-121">In Visual Studio, on the File menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="2d4e3-122">**新しいプロジェクト** ダイアログ ボックスで、プロジェクトの種類 ペインで、をクリックして**Visual C#** 、 をクリックし、**クラス ライブラリ**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-122">In the **New Project** dialog box, in the Project types pane, click **Visual C#**, and then click **Class Library** in the Templates pane.</span></span>  
  
3.  <span data-ttu-id="2d4e3-123">**名前**ボックスに「 **ItineraryLibrary**します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-123">In the **Name** box, type **ItineraryLibrary**.</span></span>  
  
4.  <span data-ttu-id="2d4e3-124">**場所**ボックスに「 **C:\HowTos**します。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-124">In the **Location** box, type **C:\HowTos**.</span></span>  
  
5.  <span data-ttu-id="2d4e3-125">選択、**ソリューションのディレクトリを作成**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-125">Select the **Create directory for solution** check box.</span></span>  
  
6.  <span data-ttu-id="2d4e3-126">**ソリューション名**ボックスに「**パターン**、順にクリックします**OK** 、ソリューションを作成しますします。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-126">In the **Solution Name** box, type **Patterns**, and then click **OK** to create the solution.</span></span>  
  
7.  <span data-ttu-id="2d4e3-127">削除、 **Class1.cs**ファイルから、 **ItineraryLibrary**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="2d4e3-127">Delete the **Class1.cs** file from the **ItineraryLibrary** project.</span></span>