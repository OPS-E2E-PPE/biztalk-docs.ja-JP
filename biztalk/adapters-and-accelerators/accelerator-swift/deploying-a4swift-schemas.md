---
title: A4SWIFT スキーマの展開 |Microsoft Docs
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
ms.openlocfilehash: 3bcd4b739313affc65788b1511bed4bd786616c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378354"
---
# <a name="deploying-a4swift-schemas"></a><span data-ttu-id="1054a-102">A4SWIFT スキーマの展開</span><span class="sxs-lookup"><span data-stu-id="1054a-102">Deploying A4SWIFT Schemas</span></span>
<span data-ttu-id="1054a-103">交換する SWIFT メッセージのスキーマを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1054a-103">You must deploy schemas for the SWIFT messages that you want to exchange.</span></span>  
  
 <span data-ttu-id="1054a-104">**まとめ**</span><span class="sxs-lookup"><span data-stu-id="1054a-104">**Summary**</span></span>  
  
 <span data-ttu-id="1054a-105">次のスキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="1054a-105">Deploy the following schemas:</span></span>  
  
-   <span data-ttu-id="1054a-106">SWIFT Base Types.xsd</span><span class="sxs-lookup"><span data-stu-id="1054a-106">SWIFT Base Types.xsd</span></span>  
  
-   <span data-ttu-id="1054a-107">SWIFT Common Data Types.xsd</span><span class="sxs-lookup"><span data-stu-id="1054a-107">SWIFT Common Data Types.xsd</span></span>  
  
-   <span data-ttu-id="1054a-108">メッセージの種類では、たとえば、MT103.xsd に対して特定のスキーマ</span><span class="sxs-lookup"><span data-stu-id="1054a-108">Specific schema for a message type, for example, MT103.xsd</span></span>  
  
### <a name="to-create-a-strong-named-swift-project"></a><span data-ttu-id="1054a-109">厳密な名前の SWIFT プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="1054a-109">To create a strong-named SWIFT project</span></span>  
  
1. <span data-ttu-id="1054a-110">Visual Studio で、次のようにクリックします。**ファイル**、 をポイント**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-110">In Visual Studio, click **File**, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="1054a-111">新しいプロジェクト ダイアログ ボックスで、**プロジェクトの種類**ペインで、 **BizTalk プロジェクト**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="1054a-111">In the New Project dialog box, in the **Project types** pane, select the **BizTalk Projects** folder.</span></span>  
  
3. <span data-ttu-id="1054a-112">**テンプレート**ペインで、**空の BizTalk Server プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-112">In the **Templates** pane, select **Empty BizTalk Server Project**.</span></span>  
  
4. <span data-ttu-id="1054a-113">**名前**ボックスで、プロジェクト名の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1054a-113">In the **Name** box, type the name you want for the project name.</span></span>  
  
5. <span data-ttu-id="1054a-114">**ソリューション**ボックスで、**新しいソリューションを作成**です。</span><span class="sxs-lookup"><span data-stu-id="1054a-114">In the **Solution** box, select **Create new Solution**.</span></span> <span data-ttu-id="1054a-115">**場所**ボックスに、スキーマ プロジェクトに追加するプロジェクトの場所を入力します。</span><span class="sxs-lookup"><span data-stu-id="1054a-115">In the **Location** box, enter the location of the project that you are adding the schema project to.</span></span>  
  
6. <span data-ttu-id="1054a-116">をクリックして**OK**を新しいプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="1054a-116">Click **OK** to open the new project.</span></span>  
   [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="1054a-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] ソリューション エクスプ ローラーに新しいプロジェクトを追加し、指定したフォルダーで、プロジェクト フォルダーとファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="1054a-117">[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] adds a new project to Solution Explorer, and creates the project folder and files in the folder specified.</span></span>  
  
7. <span data-ttu-id="1054a-118">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="1054a-118">Start Visual Studio command prompt.</span></span>  
  
8. <span data-ttu-id="1054a-119">Visual Studio コマンド プロンプトを参照 **\<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-119">At the Visual Studio command prompt, browse to **\<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT**.</span></span>  
  
9. <span data-ttu-id="1054a-120">コマンド プロンプトで「 **sn – k key.snk**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="1054a-120">At the command prompt, type **sn –k key.snk**, and then press ENTER.</span></span> <span data-ttu-id="1054a-121">キーのペアが key.snk に書き込まれたことを示すコマンド プロンプト ウィンドウで、メッセージが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1054a-121">Ensure that a message is displayed in the command-prompt window indicating that a key pair was written to key.snk.</span></span>  
  
10. <span data-ttu-id="1054a-122">ソリューション エクスプ ローラーで、プロジェクト名を右クリックし をクリックし、**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-122">In Solution Explorer, right-click your project name, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="1054a-123">左側のウィンドウで、**プロパティ ページ**ダイアログ ボックスで、をクリックして**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-123">In the left pane of the **Property Pages** dialog box, click **Assembly**.</span></span>  
  
12. <span data-ttu-id="1054a-124">右側のウィンドウで、**プロパティ ページ** ダイアログ ボックスで、下にスクロール、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、 をクリックし、省略記号 () ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1054a-124">In the right pane of the **Property Pages** dialog box, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis () button.</span></span>  
  
13. <span data-ttu-id="1054a-125">**アセンブリ キー ファイル** ダイアログ ボックスを参照 **\<*ドライブ*\>: \Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)]、クリックして**key.snk**、クリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="1054a-125">In the **Assembly Key File** dialog box, browse to **\<*drive*\>:\Program Files\Microsoft**[!INCLUDE[btaA4SWIFTNoVersionui](../../includes/btaa4swiftnoversionui-md.md)], click **key.snk**, and then click **Open**.</span></span>  
  
14. <span data-ttu-id="1054a-126">**プロパティ ページ**ダイアログ ボックスで、をクリックして**OK**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="1054a-126">In the **Property Pages** dialog box, click **OK** to save your changes.</span></span>  
  
### <a name="to-add-a-swift-schema"></a><span data-ttu-id="1054a-127">SWIFT スキーマに追加するには</span><span class="sxs-lookup"><span data-stu-id="1054a-127">To add a SWIFT schema</span></span>  
  
1.  <span data-ttu-id="1054a-128">ソリューション エクスプ ローラーの Visual Studio でプロジェクトを開きます。</span><span class="sxs-lookup"><span data-stu-id="1054a-128">In Solution Explorer of Visual Studio, open your project.</span></span>  
  
2.  <span data-ttu-id="1054a-129">プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-129">Right-click your project, point to **Add**, and then click **Existing Item**.</span></span>  
  
3.  <span data-ttu-id="1054a-130">**既存項目の追加** ダイアログ ボックスで、:\\**files \microsoft BizTalk Accelerator for SWIFT\<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Base スキーマ**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-130">In the **Add Existing Item** dialog box, in the :\\**Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Base Schemas**.</span></span> <span data-ttu-id="1054a-131">選択、 **SWIFT ベース Types.xsd**と**SWIFT 共通データ Types.xsd**スキーマ、およびクリック**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-131">Select the **SWIFT Base Types.xsd** and **SWIFT Common Data Types.xsd** schemas, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="1054a-132">プロジェクトを右クリックし、[**追加**、] をクリックし、**既存項目の追加**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-132">Right-click your project, point to **Add**, and then click **Add Existing Item**.</span></span>  
  
5.  <span data-ttu-id="1054a-133">**既存項目の追加** ダイアログ ボックスで、**検索**ドロップダウン ボックスに移動 **\<ドライブ\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category n\MTxxx**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-133">In the **Add Existing Item** dialog box, in the **Look in** drop-down box, move to **\<drive\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT \<version\> Message Pack\SWIFT Messages\A4SWIFT-SRG\<version\>\Category n\MTxxx**.</span></span> <span data-ttu-id="1054a-134">インスタンス メッセージの種類のスキーマを選択**MT103.xsd**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-134">Select a schema for a message type, for instance **MT103.xsd**, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1054a-135">A4SWIFT は、ソリューション エクスプ ローラーで示すように、プロジェクトのスキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="1054a-135">A4SWIFT adds the schema for your project, as shown in Solution Explorer.</span></span>  
  
6.  <span data-ttu-id="1054a-136">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-136">In Solution Explorer, right-click the project name, and then click **Build**.</span></span>  
  
7.  <span data-ttu-id="1054a-137">ソリューション エクスプ ローラーでプロジェクト名を右クリックし をクリックし、**デプロイ**します。</span><span class="sxs-lookup"><span data-stu-id="1054a-137">In Solution Explorer, right-click the project name, and then click **Deploy**.</span></span>