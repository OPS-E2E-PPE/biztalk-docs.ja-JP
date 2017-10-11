---
title: "追加して、Visual Studio のツールボックスからカスタム Functoid の削除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b34d546de0bbb2a79300c4f672bdfcecdab5958
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a><span data-ttu-id="3b529-102">Visual Studio ツールボックスに対するカスタム Functoid の追加と削除</span><span class="sxs-lookup"><span data-stu-id="3b529-102">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>
<span data-ttu-id="3b529-103">ここでは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに対し、カスタム Functoid を追加する方法と削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b529-103">This topic describes how to add custom functoids to and remove custom functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
## <a name="adding-custom-functoids-to-visual-studio"></a><span data-ttu-id="3b529-104">Visual Studio へのカスタム Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="3b529-104">Adding Custom Functoids to Visual Studio</span></span>  
 <span data-ttu-id="3b529-105">カスタム Functoid をマップ内で使用するには、事前に [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに追加しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b529-105">Custom functoids must be added to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox before they can be used in a map.</span></span> <span data-ttu-id="3b529-106">カスタム Functoid を追加するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3b529-106">Use the following procedure to add custom functoids.</span></span>  
  
#### <a name="to-add-a-custom-functoid"></a><span data-ttu-id="3b529-107">カスタム Functoid を追加するには</span><span class="sxs-lookup"><span data-stu-id="3b529-107">To add a custom functoid</span></span>  
  
1.  <span data-ttu-id="3b529-108">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールボックスに Functoid を追加します。</span><span class="sxs-lookup"><span data-stu-id="3b529-108">Add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
    1.  <span data-ttu-id="3b529-109">Windows エクスプローラーを使用して、カスタム Functoid が実装されているアセンブリを探します。</span><span class="sxs-lookup"><span data-stu-id="3b529-109">Using Windows Explorer, find the assembly that implements your custom functoids.</span></span>  
  
    2.  <span data-ttu-id="3b529-110">アセンブリをコピー、 \< *BizTalk Server のインストール フォルダー*>**\Developer Tools\Mapper 拡張**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="3b529-110">Copy the assembly to the \<*BizTalk Server installation folder*>**\Developer Tools\Mapper Extensions** directory.</span></span> <span data-ttu-id="3b529-111">BizTalk マッパーは、このフォルダーに対してカスタム Functoid を検索します。</span><span class="sxs-lookup"><span data-stu-id="3b529-111">This is where BizTalk Mapper looks for custom functoids.</span></span>  
  
    3.  <span data-ttu-id="3b529-112">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-112">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    4.  <span data-ttu-id="3b529-113">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブです。</span><span class="sxs-lookup"><span data-stu-id="3b529-113">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    5.  <span data-ttu-id="3b529-114">をクリックして**リセット**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-114">Click **Reset**, and then click **OK**.</span></span> <span data-ttu-id="3b529-115">この処理は時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="3b529-115">This process may take a few moments.</span></span>  
  
         <span data-ttu-id="3b529-116">カスタム Functoid が、各カテゴリを示すタブの下にあるツールボックスに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b529-116">Your custom functoids should now appear in the Toolbox under tabs matching their category.</span></span>  
  
     <span data-ttu-id="3b529-117">\- または -</span><span class="sxs-lookup"><span data-stu-id="3b529-117">\- OR -</span></span>  
  
    1.  <span data-ttu-id="3b529-118">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-118">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="3b529-119">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブです。</span><span class="sxs-lookup"><span data-stu-id="3b529-119">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    3.  <span data-ttu-id="3b529-120">をクリックして**リセット**、クリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-120">Click **Reset**, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="3b529-121">カスタム Functoid でインライン コードが公開されない場合は、アセンブリがグローバル アセンブリ キャッシュで使用可能になっているかどうかを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3b529-121">If your custom functoid does not expose any inline code, make sure its assembly is made available in the global assembly cache.</span></span>  
  
    4.  <span data-ttu-id="3b529-122">**ファイル** メニューのをクリックして**終了**を閉じる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3b529-122">On the **File** menu, click **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
    5.  <span data-ttu-id="3b529-123">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-123">Start **Visual Studio Command Prompt**.</span></span>  
  
    6.  <span data-ttu-id="3b529-124">コマンド プロンプトで次のように入力します。 **devenv/setup**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-124">At the command prompt, type **devenv /setup**.</span></span>  
  
    7.  <span data-ttu-id="3b529-125">開始**Microsoft Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-125">Start **Microsoft Visual Studio**.</span></span>  
  
         <span data-ttu-id="3b529-126">カスタム Functoid が、該当するタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b529-126">The custom functoid(s) should appear in the appropriate tab.</span></span>  
  
2.  <span data-ttu-id="3b529-127">アセンブリをグローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="3b529-127">Add the assembly to the global assembly cache.</span></span> <span data-ttu-id="3b529-128">アセンブリにインライン型の Functoid だけが含まれる場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="3b529-128">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
    1.  <span data-ttu-id="3b529-129">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-129">Start **Visual Studio Command Prompt**.</span></span>  
  
    2.  <span data-ttu-id="3b529-130">アセンブリを含むフォルダーに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="3b529-130">Switch to the folder containing your assembly.</span></span>  
  
    3.  <span data-ttu-id="3b529-131">コマンド プロンプトで次のように入力します。 **gacutil/if < assembly_path >**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-131">At the command prompt, type **gacutil /if <assembly_path >**.</span></span> <span data-ttu-id="3b529-132">たとえば、アセンブリ名が FunctoidLibrary.dll の場合は、入力**gacutil/if FunctoidLibrary.dll**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-132">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary.dll**.</span></span>  
  
    4.  <span data-ttu-id="3b529-133">入力が完了したら、**終了**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-133">When you are finished, type **exit**.</span></span>  
  
## <a name="removing-custom-functoids-from-visual-studio"></a><span data-ttu-id="3b529-134">Visual Studio からのカスタム Functoid の削除</span><span class="sxs-lookup"><span data-stu-id="3b529-134">Removing Custom Functoids from Visual Studio</span></span>  
 <span data-ttu-id="3b529-135">カスタム Functoid を削除するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="3b529-135">Use the following procedure to remove custom functoids.</span></span>  
  
#### <a name="to-remove-a-custom-functoid"></a><span data-ttu-id="3b529-136">カスタム Functoid を削除するには</span><span class="sxs-lookup"><span data-stu-id="3b529-136">To remove a custom functoid</span></span>  
  
1.  <span data-ttu-id="3b529-137">Functoid を削除、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスします。</span><span class="sxs-lookup"><span data-stu-id="3b529-137">Remove the functoid from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
    1.  <span data-ttu-id="3b529-138">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-138">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
    2.  <span data-ttu-id="3b529-139">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブです。</span><span class="sxs-lookup"><span data-stu-id="3b529-139">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
    3.  <span data-ttu-id="3b529-140">Select の一覧で、カスタム functoid を検索、**削除**チェック ボックスをクリックして**[ok]**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-140">Find the custom functoid in the list, select the **Remove** check box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="3b529-141">\- または -</span><span class="sxs-lookup"><span data-stu-id="3b529-141">\- OR -</span></span>  
  
    1.  <span data-ttu-id="3b529-142">マップを編集中に、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトをクリックして、**ツールボックス**タブ、ツールボックス パレットをします。</span><span class="sxs-lookup"><span data-stu-id="3b529-142">While editing a map in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab to bring up the Toolbox Palette.</span></span>  
  
    2.  <span data-ttu-id="3b529-143">カスタム Functoid を含む Functoid グループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3b529-143">Click the functoid group containing your custom functoid.</span></span>  
  
    3.  <span data-ttu-id="3b529-144">削除、およびをクリックする functoid を右クリックして**削除**または del キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3b529-144">Right-click the functoid you want to remove, and then click **Delete** or press the delete key.</span></span>  
  
2.  <span data-ttu-id="3b529-145">Functoid アセンブリが削除、 **Developer tools \mapper Extensions**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="3b529-145">Remove the functoid assembly from the **Developer Tools\Mapper Extensions** directory.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="3b529-146">アセンブリにアクティブな Functoid が含まれている場合は、アセンブリを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="3b529-146">If an assembly contains active functoids, then do not remove it.</span></span> <span data-ttu-id="3b529-147">削除すると、他のマップが壊れます。</span><span class="sxs-lookup"><span data-stu-id="3b529-147">Doing so will break other maps.</span></span>  
  
    1.  <span data-ttu-id="3b529-148">Windows エクスプ ローラーを起動しに移動し、 **Developer tools \mapper Extensions**ディレクトリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="3b529-148">Start Windows Explorer and navigate to the **Developer Tools\Mapper Extensions** directory of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="3b529-149">削除した functoid を含むアセンブリを右クリックし、をクリックして**削除**ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="3b529-149">Right-click the assembly containing the removed functoid, and then click **Delete** to remove the file.</span></span>  
  
3.  <span data-ttu-id="3b529-150">グローバル アセンブリ キャッシュから Functoid アセンブリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="3b529-150">Remove the functoid assembly from the global assembly cache.</span></span> <span data-ttu-id="3b529-151">アセンブリにインライン型の Functoid だけが含まれる場合は、この手順を省略できます。</span><span class="sxs-lookup"><span data-stu-id="3b529-151">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="3b529-152">アセンブリにアクティブな Functoid が含まれている場合は、グローバル アセンブリ キャッシュからアセンブリを削除しないでください。</span><span class="sxs-lookup"><span data-stu-id="3b529-152">If an assembly contains active functoids, then do not remove it from the global assembly cache.</span></span> <span data-ttu-id="3b529-153">削除すると、他のマップが壊れます。</span><span class="sxs-lookup"><span data-stu-id="3b529-153">Doing so will break other maps.</span></span>  
  
    1.  <span data-ttu-id="3b529-154">開始**Visual Studio コマンド プロンプト**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-154">Start **Visual Studio Command Prompt**.</span></span>  
  
    2.  <span data-ttu-id="3b529-155">コマンド プロンプトで次のように入力します。 **gacutil/u < assembly_display_name >**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-155">At the command prompt, type **gacutil /u <assembly_display_name>**.</span></span> <span data-ttu-id="3b529-156">たとえば、アセンブリ名が FunctoidLibrary.dll の場合は、入力**gacutil/if FunctoidLibrary**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-156">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary**.</span></span>  
  
    3.  <span data-ttu-id="3b529-157">入力が完了したら、**終了**です。</span><span class="sxs-lookup"><span data-stu-id="3b529-157">When you are finished, type **exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b529-158">参照</span><span class="sxs-lookup"><span data-stu-id="3b529-158">See Also</span></span>  
 [<span data-ttu-id="3b529-159">カスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="3b529-159">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)