---
title: "手順 3: アセンブリに厳密な名前を割り当てます |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies
- message enrichment tutorial, strong name assemblies
- strong name assemblies
ms.assetid: 8709e4e1-b428-42af-ba3c-08225c17a9eb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57368dbbb2d8ecaa6621707ea7b989bf7f5b005d
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
---
# <a name="step-3-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="86791-102">手順 3: アセンブリに厳密な名前を割り当てます</span><span class="sxs-lookup"><span data-stu-id="86791-102">Step 3: Assign a Strong Name to the Assembly</span></span>
<span data-ttu-id="86791-103">この手順で作成して割り当てるの厳密な名前、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]アセンブリ。</span><span class="sxs-lookup"><span data-stu-id="86791-103">In this step, you create and assign a strong name for the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] assembly.</span></span> <span data-ttu-id="86791-104">厳密な名前のアセンブリは、いくつかのセキュリティ上の利点を提供し、グローバル アセンブリ キャッシュ (GAC) でプロジェクトを展開するために必要な。</span><span class="sxs-lookup"><span data-stu-id="86791-104">A strong-named assembly provides several security benefits and is required in order to deploy your project in the global assembly cache (GAC).</span></span> <span data-ttu-id="86791-105">厳密な名前では、デジタル署名と一意キーのペアを割り当てることによって、アセンブリの一意性を保証します。</span><span class="sxs-lookup"><span data-stu-id="86791-105">A strong name guarantees the uniqueness of the assembly by assigning a digital signature and a unique key pair.</span></span> <span data-ttu-id="86791-106">これは、アセンブリの系列をにより、それ以降のバージョンのアセンブリを生成できないことができますも保護します。</span><span class="sxs-lookup"><span data-stu-id="86791-106">This also protects the lineage of the assembly by ensuring that no one can generate a subsequent version of the assembly.</span></span> <span data-ttu-id="86791-107">最後に、厳密な名前は、アセンブリの内容がのビルド以降に変更していないことを保証するために強力な整合性チェックを提供します。</span><span class="sxs-lookup"><span data-stu-id="86791-107">Lastly, a strong name provides a strong integrity check to guarantee that the contents of the assembly have not changed since you built it.</span></span>  
  
### <a name="to-assign-a-strong-name-to-the-assembly"></a><span data-ttu-id="86791-108">アセンブリに厳密な名前を割り当てる</span><span class="sxs-lookup"><span data-stu-id="86791-108">To assign a strong name to the assembly</span></span>  
  
1.  <span data-ttu-id="86791-109">開始 **Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="86791-109">Start **Visual Studio Command Prompt**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="86791-110">厳密な名前キーを既に作成した場合は、再利用することができます。</span><span class="sxs-lookup"><span data-stu-id="86791-110">If you have already created a strong name key, you can reuse it.</span></span>  
  
2.  <span data-ttu-id="86791-111">コマンド プロンプトでに移動**\<*ドライブ*\>: \Tutorial\BTAHL7V22Common** (ここで\<*ドライブ*\>はインストール ドライブ文字) キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="86791-111">At the command prompt, move to**\<*drive*\>:\Tutorial\BTAHL7V22Common** (where \<*drive*\> is your installation drive letter) and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="86791-112">コマンド プロンプトで次のように入力します。 **sn – k key.snk**、キーを押します**Enter**です。</span><span class="sxs-lookup"><span data-stu-id="86791-112">At the command prompt, type **sn –k key.snk**, and then press **Enter**.</span></span> <span data-ttu-id="86791-113">示すメッセージが表示されます[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]キーファイル key.snk にキーのペアを書き込みました。</span><span class="sxs-lookup"><span data-stu-id="86791-113">A message appears indicating that [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] wrote the key pair to the key file key.snk.</span></span>  
  
4.  <span data-ttu-id="86791-114">ソリューション エクスプ ローラーで右クリックし、 **BTAHL7V22Common**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="86791-114">In Solution Explorer, right-click the **BTAHL7V22Common** project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="86791-115">BTAHL7V22Common プロパティ ページ] ダイアログ ボックスで、[**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="86791-115">In the BTAHL7V22Common Property Pages dialog box, click **Assembly**.</span></span>  
  
6.  <span data-ttu-id="86791-116">右側のペインでスクロールして、**厳密な名前**セクションで、フィールドの右側をクリックして**アセンブリ キー ファイル**、省略記号 (...) ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="86791-116">In the right pane, scroll down to the **Strong name** section, click the field to the right of **Assembly Key File**, and then click the ellipsis (…) button.</span></span>  
  
7.  <span data-ttu-id="86791-117">アセンブリ キー ファイル ダイアログ ボックスでを参照 **\<*ドライブ*\>: \Tutorial\BTAHL7V22Common\key.snk**をクリックして**開く**、 をクリックし、**OK**です。</span><span class="sxs-lookup"><span data-stu-id="86791-117">In the Assembly Key File dialog box, browse to **\<*drive*\>:\Tutorial\BTAHL7V22Common\key.snk**, click **Open**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="86791-118">ソリューション エクスプ ローラーで右クリック**BTAHL7V22Common**、クリックして**展開**です。</span><span class="sxs-lookup"><span data-stu-id="86791-118">In Solution Explorer, right-click **BTAHL7V22Common**, and then click **Deploy**.</span></span> [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]<span data-ttu-id="86791-119">次のプロジェクトから参照できるアセンブリを作成します。</span><span class="sxs-lookup"><span data-stu-id="86791-119"> creates an assembly that you can reference from your next project.</span></span>  
  
9. <span data-ttu-id="86791-120">BTAHL7V2XCommon プロジェクトに対して手順 4. ~ 8. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="86791-120">Repeat steps 4 through 8 for the BTAHL7V2XCommon project.</span></span>  
  
 <span data-ttu-id="86791-121">進みます[手順 4: スキーマ作成](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)です。</span><span class="sxs-lookup"><span data-stu-id="86791-121">Proceed to [Step 4: Create the Schemas](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86791-122">参照</span><span class="sxs-lookup"><span data-stu-id="86791-122">See Also</span></span>  
 [<span data-ttu-id="86791-123">メッセージ強化のチュートリアル</span><span class="sxs-lookup"><span data-stu-id="86791-123">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)