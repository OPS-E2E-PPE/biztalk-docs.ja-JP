---
title: レッスン 2:SWIFTSchemas プロジェクト用の厳密な名前の BizTalk アセンブリを作成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98739cfa16aa519bc67ca5a4c2b5dfa5bd2af371
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530347"
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a><span data-ttu-id="aea2d-102">レッスン 2:SWIFTSchemas プロジェクト用の厳密な名前の BizTalk アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-102">Lesson 2: Creating a Strong-Named BizTalk Assembly for the SWIFTSchemas Project</span></span>
<span data-ttu-id="aea2d-103">このレッスンでは、BizTalk アセンブリをコンパイルおよび展開する、厳密な名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-103">In this lesson, you create a strong name upon which the BizTalk assemblies are compiled and deployed.</span></span> <span data-ttu-id="aea2d-104">厳密な名前のアセンブリには、いくつかのセキュリティの利点があります。</span><span class="sxs-lookup"><span data-stu-id="aea2d-104">A strong-named assembly provides several security benefits:</span></span>  
  
- <span data-ttu-id="aea2d-105">厳密な名前では、デジタル署名と一意キーのペアを割り当てることで、アセンブリの一意性を保証します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span>  
  
- <span data-ttu-id="aea2d-106">厳密な名前では、誰もそれ以降のバージョンのアセンブリを生成できることを確認して、アセンブリの系統を保護します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-106">A strong name protects the lineage of the assembly by ensuring that no one else can generate a subsequent version of the assembly.</span></span>  
  
- <span data-ttu-id="aea2d-107">厳密な名前では、前回のビルド以降、アセンブリの内容が変更されていないことを保証するために厳密な整合性チェックを提供します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-107">A strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since the last build.</span></span>  
  
  <span data-ttu-id="aea2d-108">付属する厳密な名前ツール (sn.exe) を使用してキー ファイルを生成できる[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]または[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-108">You can generate a key file by using the strong name tool (sn.exe) that comes with [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] or the [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)].</span></span>  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a><span data-ttu-id="aea2d-109">厳密な名前の BizTalk アセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="aea2d-109">To create a strong-named BizTalk assembly</span></span>  
  
1. <span data-ttu-id="aea2d-110">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-110">Start Visual Studio command prompt.</span></span>  
  
2. <span data-ttu-id="aea2d-111">Visual Studio コマンド プロンプトを参照、 \<*ドライブ*\>: \labs フォルダー。</span><span class="sxs-lookup"><span data-stu-id="aea2d-111">At the Visual Studio command prompt, browse to the \<*drive*\>:\labs folder.</span></span>  
  
3. <span data-ttu-id="aea2d-112">コマンド プロンプトで「 **sn – k swift.snk**し、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-112">At the command prompt, type **sn –k swift.snk**, and then press ENTER.</span></span> <span data-ttu-id="aea2d-113">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-113">Ensure that a success message appears in the output window.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="aea2d-114">適切なメッセージが表示されない場合は、Visual Studio を使用して、アセンブリのトラブルシューティングを行う。</span><span class="sxs-lookup"><span data-stu-id="aea2d-114">If the correct message does not appear, use Visual Studio to troubleshoot your assembly.</span></span>  
  
4. <span data-ttu-id="aea2d-115">ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-115">In Solution Explorer, right-click the **SWIFTSchemas** project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="aea2d-116">SWIFTSchemas プロパティ ページ] ダイアログ ボックスで、ことを確認します**共通プロパティ**は拡張、および [**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-116">In the SWIFTSchemas Property Pages dialog box, ensure that **Common Properties** is expanded, and then select **Assembly**.</span></span>  
  
6. <span data-ttu-id="aea2d-117">アセンブリのプロパティと右側のウィンドウで下にスクロール、**厳密な名前**セクションで、の右側に**アセンブリ キー ファイル**します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-117">Scroll down the assembly properties in the right pane, and in the **Strong name** section, click the box to the right of **Assembly Key File**.</span></span> <span data-ttu-id="aea2d-118">省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="aea2d-118">Click the ellipsis button.</span></span>  
  
7. <span data-ttu-id="aea2d-119">アセンブリ キー ファイル ダイアログ ボックスを参照 **\<*ドライブ*:\>\labs**します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-119">In the Assembly Key File dialog box, browse to **\<*drive*:\>\labs**.</span></span>  
  
8. <span data-ttu-id="aea2d-120">選択、 **swift.snk**キーのファイルとしてファイルをクリックして**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-120">Select the **swift.snk** file as the key file, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="aea2d-121">SWIFTSchemas プロパティ ページ] ダイアログ ボックスで、[ **OK**します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-121">In the SWIFTSchemas Property Pages dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="aea2d-122">**ファイル** メニューのをクリックして**すべて保存**変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-122">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
    <span data-ttu-id="aea2d-123">続行する[レッスン 3。SWIFT スキーマをプロジェクトに追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md)します。</span><span class="sxs-lookup"><span data-stu-id="aea2d-123">Proceed to [Lesson 3: Adding SWIFT Schemas to a Project](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md).</span></span>