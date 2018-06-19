---
title: A4SWIFT のスキーマを展開する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, A4SWIFT
- deploying, A4SWIFT schemas
- A4SWIFT, deploying schemas
- schemas, deploying
ms.assetid: a6aed2cd-3578-442e-ab1e-8284cc5f7b72
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc89b26d0eee970268d5e9084cd0827d3100fd7b
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25966424"
---
# <a name="deploying-a4swift-schemas"></a><span data-ttu-id="91a4b-102">A4SWIFT のスキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-102">Deploying A4SWIFT Schemas</span></span>
<span data-ttu-id="91a4b-103">交換する SWIFT メッセージのスキーマを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="91a4b-103">You must deploy schemas for the SWIFT messages that you want to exchange.</span></span>  
  
 <span data-ttu-id="91a4b-104">**概要**</span><span class="sxs-lookup"><span data-stu-id="91a4b-104">**Summary**</span></span>  
  
 <span data-ttu-id="91a4b-105">次のスキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-105">Deploy the following schemas:</span></span>  
  
-   <span data-ttu-id="91a4b-106">SWIFT Base Types.xsd</span><span class="sxs-lookup"><span data-stu-id="91a4b-106">SWIFT Base Types.xsd</span></span>  
  
-   <span data-ttu-id="91a4b-107">SWIFT Common Data Types.xsd</span><span class="sxs-lookup"><span data-stu-id="91a4b-107">SWIFT Common Data Types.xsd</span></span>  
  
-   <span data-ttu-id="91a4b-108">メッセージ型、MT103.xsd などの特定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="91a4b-108">Specific schema for a message type, for example, MT103.xsd</span></span>  
  
### <a name="to-create-a-strong-named-swift-project"></a><span data-ttu-id="91a4b-109">厳密な名前の SWIFT プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="91a4b-109">To create a strong-named SWIFT project</span></span>  
  
1.  <span data-ttu-id="91a4b-110">Visual Studio で、[**ファイル**、] をポイント**新規**、クリックして**プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-110">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="91a4b-111">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="91a4b-111">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  
  
3.  <span data-ttu-id="91a4b-112">**テンプレート**ペインで、**空の BizTalk Server プロジェクト**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-112">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  
  
4.  <span data-ttu-id="91a4b-113">**名前**ボックスで、プロジェクト名の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-113">In the **Name** box, type the name you want for the project name.</span></span>  
  
5.  <span data-ttu-id="91a4b-114">**ソリューション**ボックスで、**新しいソリューションを作成**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-114">In the **Solution** box, select **Create new Solution**.</span></span> <span data-ttu-id="91a4b-115">**場所**ボックスに、スキーマにプロジェクトを追加するプロジェクトの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-115">In the **Location** box, enter the location of the project that you are adding the schema project to.</span></span>  
  
6.  <span data-ttu-id="91a4b-116">をクリックして**OK**新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="91a4b-116">Click **OK** to open the new project.</span></span>  
    [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="91a4b-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定されたフォルダーにプロジェクト フォルダーとファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  
  
7.  <span data-ttu-id="91a4b-118">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-118">Start Visual Studio command prompt.</span></span>  
  
8.  <span data-ttu-id="91a4b-119">Visual Studio コマンド プロンプトを参照 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-119">At the Visual Studio command prompt, browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT**.</span></span>  
  
9. <span data-ttu-id="91a4b-120">コマンド プロンプトで次のように入力します。 **sn – k key.snk**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-120">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="91a4b-121">キーのペアが key.snk に書き込まれたことを示すコマンド プロンプト ウィンドウで、メッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-121">Ensure that a message is displayed in the command-prompt window indicating that a key pair was written to key.snk.</span></span>  
  
10. <span data-ttu-id="91a4b-122">ソリューション エクスプ ローラーで、プロジェクト名を右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-122">In Solution Explorer, right-click your project name, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="91a4b-123">左側のウィンドウで、**プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-123">In the left pane of the **Property Pages** dialog box, click **Assembly**.</span></span>  
  
12. <span data-ttu-id="91a4b-124">右側のペインで、**プロパティ ページ**を下にスクロール ダイアログ ボックスで、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、をクリックし、省略記号ボタン () ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="91a4b-124">In the right pane of the **Property Pages** dialog box, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis () button.</span></span>  
  
13. <span data-ttu-id="91a4b-125">**アセンブリ キー ファイル** ダイアログ ボックスを参照 **\<*ドライブ*\>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)]、クリックして**key.snk**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-125">In the **Assembly Key File** dialog box, browse to **\<*drive*\>:\Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)], click **key.snk**, and then click **Open**.</span></span>  
  
14. <span data-ttu-id="91a4b-126">**プロパティ ページ**ダイアログ ボックスで、をクリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-126">In the **Property Pages** dialog box, click **OK** to save your changes.</span></span>  
  
### <a name="to-add-a-swift-schema"></a><span data-ttu-id="91a4b-127">SWIFT スキーマに追加するには</span><span class="sxs-lookup"><span data-stu-id="91a4b-127">To add a SWIFT schema</span></span>  
  
1.  <span data-ttu-id="91a4b-128">ソリューション エクスプ ローラーの Visual Studio でプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="91a4b-128">In Solution Explorer of Visual Studio, open your project.</span></span>  
  
2.  <span data-ttu-id="91a4b-129">プロジェクトを右クリックし、順にポイント **追加**, 、クリックして **既存項目の**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-129">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span>  
  
3.  <span data-ttu-id="91a4b-130">**既存項目の追加** ダイアログ ボックスで、:\\**files \microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base スキーマ**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-130">In the **Add Existing Item** dialog box, in the :\\**Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Schemas**.</span></span> <span data-ttu-id="91a4b-131">選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-131">Select the **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** schemas, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="91a4b-132">プロジェクトを右クリックし、順にポイント**追加**、クリックして**既存項目の追加**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-132">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
5.  <span data-ttu-id="91a4b-133">**既存項目の追加** ダイアログ ボックスで、**ファイルの場所**ドロップダウン ボックスに移動**\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator 用 SWIFT \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Category n\MTxxx**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-133">In the **Add Existing Item** dialog box, in the **Look in** drop-down box, move to **\<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category n\MTxxx**.</span></span> <span data-ttu-id="91a4b-134">インスタンス メッセージの種類のスキーマを選択**MT103.xsd**、クリックして**追加**です。</span><span class="sxs-lookup"><span data-stu-id="91a4b-134">Select a schema for a message type, for instance **MT103.xsd**, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="91a4b-135">ソリューション エクスプ ローラーで示すように、A4SWIFT は、プロジェクトのスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-135">A4SWIFT adds the schema for your project, as shown in Solution Explorer.</span></span>  
  
6.  <span data-ttu-id="91a4b-136">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、 **ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-136">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
7.  <span data-ttu-id="91a4b-137">ソリューション エクスプ ローラーでプロジェクト名を右クリックし、をクリックし、 **展開**します。</span><span class="sxs-lookup"><span data-stu-id="91a4b-137">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>