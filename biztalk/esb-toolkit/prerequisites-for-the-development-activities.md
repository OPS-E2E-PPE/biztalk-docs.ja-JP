---
title: "開発活動の前提条件 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54c91405-f9a4-4676-b5c5-fe90b3b51b45
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efdb0a358b378886b8944c9d3d9428b169bab7a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="prerequisites-for-the-development-activities"></a><span data-ttu-id="8b30e-102">開発活動の前提条件</span><span class="sxs-lookup"><span data-stu-id="8b30e-102">Prerequisites for the Development Activities</span></span>
<span data-ttu-id="8b30e-103">このセクションの一部として含まれている開発作業の手順を実行するように環境を準備する方法について説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="8b30e-103">This section describes how to prepare your environment to complete the steps in the development activities that are included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="8b30e-104">開発作業の手順のいずれかの操作を行う前に、次のセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="8b30e-104">Complete the following setup before you attempt any of the procedures in the development activities:</span></span>  
  
## <a name="set-up-your-computer-to-perform-the-procedures-in-the-biztalk-esb-toolkit-development-activities"></a><span data-ttu-id="8b30e-105">BizTalk ESB Toolkit の開発作業の手順を実行するコンピューターを設定します。</span><span class="sxs-lookup"><span data-stu-id="8b30e-105">Set up your computer to perform the procedures in the BizTalk ESB Toolkit development activities</span></span>  
  
1.  <span data-ttu-id="8b30e-106">インストールし、旅程サンプル アプリケーション、動的な解決サンプル アプリケーション、および複数の Web サービス サンプル アプリケーションを展開します。</span><span class="sxs-lookup"><span data-stu-id="8b30e-106">Install and deploy the Itinerary sample application, the Dynamic Resolution sample application, and the Multiple Web Services sample application.</span></span> <span data-ttu-id="8b30e-107">インストールして、これらのアプリケーションの展開に関する詳細については、次を参照してください。 [BizTalk ESB Toolkit のサンプル アプリケーション](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md)です。</span><span class="sxs-lookup"><span data-stu-id="8b30e-107">For more information about installing and deploying these applications, see [BizTalk ESB Toolkit Sample Applications](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span></span>  
  
2.  <span data-ttu-id="8b30e-108">UDDI 発行元のユーティリティを実行します。</span><span class="sxs-lookup"><span data-stu-id="8b30e-108">Run the UDDI Publisher Utility.</span></span>  
  
3.  <span data-ttu-id="8b30e-109">開発用コンピューター上の Windows エクスプ ローラーで、次のパスを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b30e-109">On your development computer, in Windows Explorer, create the following paths:</span></span>  
  
    -   <span data-ttu-id="8b30e-110">C:\HowTos</span><span class="sxs-lookup"><span data-stu-id="8b30e-110">C:\HowTos</span></span>  
  
    -   <span data-ttu-id="8b30e-111">C:\HowTos\Itineraries</span><span class="sxs-lookup"><span data-stu-id="8b30e-111">C:\HowTos\Itineraries</span></span>  
  
    -   <span data-ttu-id="8b30e-112">C:\HowTos\DropFolder</span><span class="sxs-lookup"><span data-stu-id="8b30e-112">C:\HowTos\DropFolder</span></span>  
  
    -   <span data-ttu-id="8b30e-113">C:\HowTos\Out</span><span class="sxs-lookup"><span data-stu-id="8b30e-113">C:\HowTos\Out</span></span>  
  
4.  <span data-ttu-id="8b30e-114">いることを確認、[!INCLUDE[prague](../includes/prague-md.md)]サービス アカウントが**フルコントロール**C:\HowTos ディレクトリ構造へのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="8b30e-114">Ensure that your [!INCLUDE[prague](../includes/prague-md.md)] service account has **Full Control** permissions to the C:\HowTos directory structure.</span></span>  
  
5.  <span data-ttu-id="8b30e-115">Microsoft BizTalk Server サービス アカウントがあることを確認**書き込み**C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out へのアクセス許可。</span><span class="sxs-lookup"><span data-stu-id="8b30e-115">Ensure that your Microsoft BizTalk Server service account has **Write** permissions to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out.</span></span>  
  
6.  <span data-ttu-id="8b30e-116">次のテスト メッセージを C:\HowTos フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="8b30e-116">Copy the following test message to the C:\HowTos folder:</span></span>  
  
    -   <span data-ttu-id="8b30e-117">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml</span><span class="sxs-lookup"><span data-stu-id="8b30e-117">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml</span></span>  
  
7.  <span data-ttu-id="8b30e-118">C:\HowTos フォルダーでは、次の場所で見つかった、行程テスト用クライアント アプリケーションへのショートカットを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b30e-118">In the C:\HowTos folder, create a shortcut to the Itinerary Test Client application, found at the following location:</span></span>  
  
    -   <span data-ttu-id="8b30e-119">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB です。Itinerary.Test\bin\Debug\ESB です。Itinerary.Test.exe</span><span class="sxs-lookup"><span data-stu-id="8b30e-119">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug\ESB.Itinerary.Test.exe</span></span>  
  
## <a name="create-the-visual-studio-solution"></a><span data-ttu-id="8b30e-120">Visual Studio ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b30e-120">Create the Visual Studio solution</span></span>  
  
1.  <span data-ttu-id="8b30e-121">[!INCLUDE[vs2010](../includes/vs2010-md.md)]、[ファイル] メニューのをポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="8b30e-121">In [!INCLUDE[vs2010](../includes/vs2010-md.md)], on the File menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="8b30e-122">**新しいプロジェクト**ダイアログ ボックスで、プロジェクトの種類 ペインで、をクリックして**Visual c#**、クリックして**クラス ライブラリ**テンプレート ペインでします。</span><span class="sxs-lookup"><span data-stu-id="8b30e-122">In the **New Project** dialog box, in the Project types pane, click **Visual C#**, and then click **Class Library** in the Templates pane.</span></span>  
  
3.  <span data-ttu-id="8b30e-123">**名前**ボックスに、入力**ItineraryLibrary**です。</span><span class="sxs-lookup"><span data-stu-id="8b30e-123">In the **Name** box, type **ItineraryLibrary**.</span></span>  
  
4.  <span data-ttu-id="8b30e-124">**場所**ボックスに、入力**C:\HowTos**です。</span><span class="sxs-lookup"><span data-stu-id="8b30e-124">In the **Location** box, type **C:\HowTos**.</span></span>  
  
5.  <span data-ttu-id="8b30e-125">選択、**ソリューションのディレクトリを作成**チェック ボックスをオンします。</span><span class="sxs-lookup"><span data-stu-id="8b30e-125">Select the **Create directory for solution** check box.</span></span>  
  
6.  <span data-ttu-id="8b30e-126">**ソリューション名**ボックスに、入力**パターン**、クリックして**[ok]**ソリューションを作成します。</span><span class="sxs-lookup"><span data-stu-id="8b30e-126">In the **Solution Name** box, type **Patterns**, and then click **OK** to create the solution.</span></span>  
  
7.  <span data-ttu-id="8b30e-127">削除、 **Class1.cs**ファイルから、 **ItineraryLibrary**プロジェクト。</span><span class="sxs-lookup"><span data-stu-id="8b30e-127">Delete the **Class1.cs** file from the **ItineraryLibrary** project.</span></span>