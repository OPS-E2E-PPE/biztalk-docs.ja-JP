---
title: "レッスン 2: SWIFTSchemas プロジェクト用の厳密な名前の BizTalk アセンブリの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies, creating strong-names
- strong-named assemblies
ms.assetid: 2aacbf38-8b1d-46ea-89ae-5207327bedc1
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28afb0b029924a49dfd9a1bff87c5c847157d669
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="lesson-2-creating-a-strong-named-biztalk-assembly-for-the-swiftschemas-project"></a><span data-ttu-id="f7195-102">レッスン 2: SWIFTSchemas プロジェクト用の厳密な名前の BizTalk アセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="f7195-102">Lesson 2: Creating a Strong-Named BizTalk Assembly for the SWIFTSchemas Project</span></span>
<span data-ttu-id="f7195-103">このレッスンでは、BizTalk アセンブリのコンパイルし、展開の基になる、厳密な名前を作成します。</span><span class="sxs-lookup"><span data-stu-id="f7195-103">In this lesson, you create a strong name upon which the BizTalk assemblies are compiled and deployed.</span></span> <span data-ttu-id="f7195-104">厳密な名前のアセンブリには、いくつかのセキュリティの利点があります。</span><span class="sxs-lookup"><span data-stu-id="f7195-104">A strong-named assembly provides several security benefits:</span></span>  
  
-   <span data-ttu-id="f7195-105">厳密な名前では、デジタル署名と一意キーのペアを割り当てることによって、アセンブリの一意性を保証します。</span><span class="sxs-lookup"><span data-stu-id="f7195-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span>  
  
-   <span data-ttu-id="f7195-106">厳密な名前では、それ以降のバージョンのアセンブリを生成できます誰もできるようにして、アセンブリの系列を保護します。</span><span class="sxs-lookup"><span data-stu-id="f7195-106">A strong name protects the lineage of the assembly by ensuring that no one else can generate a subsequent version of the assembly.</span></span>  
  
-   <span data-ttu-id="f7195-107">厳密な名前では、アセンブリの内容が前回のビルド以降変更されていないことを保証するために強力な整合性チェックを提供します。</span><span class="sxs-lookup"><span data-stu-id="f7195-107">A strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since the last build.</span></span>  
  
 <span data-ttu-id="f7195-108">付属している厳密名ツール (sn.exe) を使用してキー ファイルを生成することができます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)]または[!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="f7195-108">You can generate a key file by using the strong name tool (sn.exe) that comes with [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)][!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] or the [!INCLUDE[btsDotNetFramework](../../includes/btsdotnetframework-md.md)].</span></span>  
  
### <a name="to-create-a-strong-named-biztalk-assembly"></a><span data-ttu-id="f7195-109">厳密な名前の BizTalk アセンブリを作成するには</span><span class="sxs-lookup"><span data-stu-id="f7195-109">To create a strong-named BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="f7195-110">Visual Studio コマンド プロンプトを起動します。</span><span class="sxs-lookup"><span data-stu-id="f7195-110">Start Visual Studio command prompt.</span></span>  
  
2.  <span data-ttu-id="f7195-111">Visual Studio コマンド プロンプトを参照、 \<*ドライブ*>: \labs フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="f7195-111">At the Visual Studio command prompt, browse to the \<*drive*>:\labs folder.</span></span>  
  
3.  <span data-ttu-id="f7195-112">コマンド プロンプトで次のように入力します。 **sn – k swift.snk**、ENTER キーを押します。</span><span class="sxs-lookup"><span data-stu-id="f7195-112">At the command prompt, type **sn –k swift.snk**, and then press ENTER.</span></span> <span data-ttu-id="f7195-113">成功メッセージが出力ウィンドウに表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f7195-113">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7195-114">適切なメッセージが表示されない場合は、Visual Studio を使用して、アセンブリのトラブルシューティングを行います。</span><span class="sxs-lookup"><span data-stu-id="f7195-114">If the correct message does not appear, use Visual Studio to troubleshoot your assembly.</span></span>  
  
4.  <span data-ttu-id="f7195-115">ソリューション エクスプ ローラーで右クリックし、 **SWIFTSchemas**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="f7195-115">In Solution Explorer, right-click the **SWIFTSchemas** project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="f7195-116">SWIFTSchemas プロパティ ページ] ダイアログ ボックスで、いることを確認**共通プロパティ**が拡張され、[**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="f7195-116">In the SWIFTSchemas Property Pages dialog box, ensure that **Common Properties** is expanded, and then select **Assembly**.</span></span>  
  
6.  <span data-ttu-id="f7195-117">アセンブリのプロパティと右側のペインで下へスクロールして、**厳密な名前**セクションで、の右側に**アセンブリ キー ファイル**です。</span><span class="sxs-lookup"><span data-stu-id="f7195-117">Scroll down the assembly properties in the right pane, and in the **Strong name** section, click the box to the right of **Assembly Key File**.</span></span> <span data-ttu-id="f7195-118">省略記号ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="f7195-118">Click the ellipsis button.</span></span>  
  
7.  <span data-ttu-id="f7195-119">アセンブリ キー ファイル ダイアログ ボックスでを参照  **\<*ドライブ*: > \labs** です。</span><span class="sxs-lookup"><span data-stu-id="f7195-119">In the Assembly Key File dialog box, browse to **\<*drive*:>\labs**.</span></span>  
  
8.  <span data-ttu-id="f7195-120">選択、 **swift.snk**クリックしてファイルをキー ファイルとして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="f7195-120">Select the **swift.snk** file as the key file, and then click **Open**.</span></span>  
  
9. <span data-ttu-id="f7195-121">SWIFTSchemas プロパティ ページ] ダイアログ ボックスで、[ **OK**です。</span><span class="sxs-lookup"><span data-stu-id="f7195-121">In the SWIFTSchemas Property Pages dialog box, click **OK**.</span></span>  
  
10. <span data-ttu-id="f7195-122">**ファイル** メニューのをクリックして**すべて保存**して変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="f7195-122">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
 <span data-ttu-id="f7195-123">進みます[レッスン 3: SWIFT スキーマをプロジェクトに追加する](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md)です。</span><span class="sxs-lookup"><span data-stu-id="f7195-123">Proceed to [Lesson 3: Adding SWIFT Schemas to a Project](../../adapters-and-accelerators/accelerator-swift/lesson-3-adding-swift-schemas-to-a-project.md).</span></span>