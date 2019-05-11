---
title: 追加して、Visual Studio のツールボックスからカスタム Functoid の削除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e3493608606df11a5237287a89cbf79d384800a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360905"
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a><span data-ttu-id="e0739-102">追加して、Visual Studio のツールボックスからカスタム Functoid の削除</span><span class="sxs-lookup"><span data-stu-id="e0739-102">Adding and Removing Custom Functoids from the Visual Studio Toolbox</span></span>
<span data-ttu-id="e0739-103">このトピックでは、カスタム functoid を追加およびからカスタム functoid を削除する方法を説明します、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。</span><span class="sxs-lookup"><span data-stu-id="e0739-103">This topic describes how to add custom functoids to and remove custom functoids from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
## <a name="adding-custom-functoids-to-visual-studio"></a><span data-ttu-id="e0739-104">Visual Studio にカスタム Functoid の追加</span><span class="sxs-lookup"><span data-stu-id="e0739-104">Adding Custom Functoids to Visual Studio</span></span>  
 <span data-ttu-id="e0739-105">カスタム functoid を追加する必要があります、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス前に、これらは、マップで使用できます。</span><span class="sxs-lookup"><span data-stu-id="e0739-105">Custom functoids must be added to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox before they can be used in a map.</span></span> <span data-ttu-id="e0739-106">カスタム functoid を追加するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0739-106">Use the following procedure to add custom functoids.</span></span>  
  
#### <a name="to-add-a-custom-functoid"></a><span data-ttu-id="e0739-107">カスタム functoid を追加するには</span><span class="sxs-lookup"><span data-stu-id="e0739-107">To add a custom functoid</span></span>  
  
1. <span data-ttu-id="e0739-108">Functoid を追加、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。</span><span class="sxs-lookup"><span data-stu-id="e0739-108">Add the functoid to the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
   1. <span data-ttu-id="e0739-109">Windows エクスプ ローラーを使用して、カスタム functoid を実装するアセンブリを検索します。</span><span class="sxs-lookup"><span data-stu-id="e0739-109">Using Windows Explorer, find the assembly that implements your custom functoids.</span></span>  
  
   2. <span data-ttu-id="e0739-110">アセンブリをコピー、 \< *BizTalk Server のインストール フォルダー*\>**\Developer Tools\Mapper 拡張**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="e0739-110">Copy the assembly to the \<*BizTalk Server installation folder*\>**\Developer Tools\Mapper Extensions** directory.</span></span> <span data-ttu-id="e0739-111">これは、BizTalk マッパーがカスタム functoid を検索する場所です。</span><span class="sxs-lookup"><span data-stu-id="e0739-111">This is where BizTalk Mapper looks for custom functoids.</span></span>  
  
   3. <span data-ttu-id="e0739-112">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="e0739-112">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   4. <span data-ttu-id="e0739-113">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブ。</span><span class="sxs-lookup"><span data-stu-id="e0739-113">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   5. <span data-ttu-id="e0739-114">クリックして**リセット**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-114">Click **Reset**, and then click **OK**.</span></span> <span data-ttu-id="e0739-115">このプロセスには数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="e0739-115">This process may take a few moments.</span></span>  
  
       <span data-ttu-id="e0739-116">カスタム functoid ツールボックスのタブの各カテゴリの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0739-116">Your custom functoids should now appear in the Toolbox under tabs matching their category.</span></span>  
  
      <span data-ttu-id="e0739-117">\- または -</span><span class="sxs-lookup"><span data-stu-id="e0739-117">\- OR -</span></span>  
  
   6. <span data-ttu-id="e0739-118">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="e0739-118">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   7. <span data-ttu-id="e0739-119">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブ。</span><span class="sxs-lookup"><span data-stu-id="e0739-119">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   8. <span data-ttu-id="e0739-120">クリックして**リセット**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-120">Click **Reset**, and then click **OK**.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="e0739-121">カスタム functoid でインライン コードが公開されない場合は、グローバル アセンブリ キャッシュに利用可能になってそのアセンブリを確認します。</span><span class="sxs-lookup"><span data-stu-id="e0739-121">If your custom functoid does not expose any inline code, make sure its assembly is made available in the global assembly cache.</span></span>  
  
   9. <span data-ttu-id="e0739-122">**ファイル** メニューのをクリックして**終了**を閉じる[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0739-122">On the **File** menu, click **Exit** to close [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
   10. <span data-ttu-id="e0739-123">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-123">Start **Visual Studio Command Prompt**.</span></span>  
  
   11. <span data-ttu-id="e0739-124">コマンド プロンプトで「 **devenv/setup**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-124">At the command prompt, type **devenv /setup**.</span></span>  
  
   12. <span data-ttu-id="e0739-125">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-125">Start **Microsoft Visual Studio**.</span></span>  
  
        <span data-ttu-id="e0739-126">カスタム functoid は、適切なタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0739-126">The custom functoid(s) should appear in the appropriate tab.</span></span>  
  
2. <span data-ttu-id="e0739-127">アセンブリをグローバル アセンブリ キャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="e0739-127">Add the assembly to the global assembly cache.</span></span> <span data-ttu-id="e0739-128">アセンブリにのみインライン型の functoid が含まれている場合は、この手順をスキップすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0739-128">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
   1.  <span data-ttu-id="e0739-129">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-129">Start **Visual Studio Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="e0739-130">アセンブリを含むフォルダーに切り替えます。</span><span class="sxs-lookup"><span data-stu-id="e0739-130">Switch to the folder containing your assembly.</span></span>  
  
   3.  <span data-ttu-id="e0739-131">コマンド プロンプトで「 **gacutil/if < assembly_path >** します。</span><span class="sxs-lookup"><span data-stu-id="e0739-131">At the command prompt, type **gacutil /if <assembly_path >**.</span></span> <span data-ttu-id="e0739-132">たとえば、アセンブリ名が FunctoidLibrary.dll の場合は、入力**gacutil/if FunctoidLibrary.dll**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-132">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary.dll**.</span></span>  
  
   4.  <span data-ttu-id="e0739-133">入力が完了したら、**終了**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-133">When you are finished, type **exit**.</span></span>  
  
## <a name="removing-custom-functoids-from-visual-studio"></a><span data-ttu-id="e0739-134">Visual Studio からのカスタム Functoid の削除</span><span class="sxs-lookup"><span data-stu-id="e0739-134">Removing Custom Functoids from Visual Studio</span></span>  
 <span data-ttu-id="e0739-135">カスタム functoid を削除するのにには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e0739-135">Use the following procedure to remove custom functoids.</span></span>  
  
#### <a name="to-remove-a-custom-functoid"></a><span data-ttu-id="e0739-136">カスタム functoid を削除するには</span><span class="sxs-lookup"><span data-stu-id="e0739-136">To remove a custom functoid</span></span>  
  
1. <span data-ttu-id="e0739-137">Functoid を削除、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックスです。</span><span class="sxs-lookup"><span data-stu-id="e0739-137">Remove the functoid from the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Toolbox.</span></span>  
  
   1. <span data-ttu-id="e0739-138">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクトで、**ツール** メニューをクリックして**ツールボックス アイテムの選択**です。</span><span class="sxs-lookup"><span data-stu-id="e0739-138">From a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, on the **Tools** menu, click **Choose Toolbox Items**.</span></span>  
  
   2. <span data-ttu-id="e0739-139">**ツールボックス アイテムの選択**ダイアログ ボックスで、をクリックして、 **BizTalk マッパー Functoid**タブ。</span><span class="sxs-lookup"><span data-stu-id="e0739-139">In the **Choose Toolbox items** dialog box, click the **BizTalk Mapper Functoids** tab.</span></span>  
  
   3. <span data-ttu-id="e0739-140">カスタム functoid を一覧で検索、**削除**チェック ボックスをオンにして **[ok]** します。</span><span class="sxs-lookup"><span data-stu-id="e0739-140">Find the custom functoid in the list, select the **Remove** check box, and then click **OK**.</span></span>  
  
      <span data-ttu-id="e0739-141">\- または -</span><span class="sxs-lookup"><span data-stu-id="e0739-141">\- OR -</span></span>  
  
   4. <span data-ttu-id="e0739-142">マップを編集中に、 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk プロジェクト をクリックして、**ツールボックス**タブをツールボックス パレットを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0739-142">While editing a map in a [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] BizTalk project, click the **Toolbox** tab to bring up the Toolbox Palette.</span></span>  
  
   5. <span data-ttu-id="e0739-143">カスタム functoid を含む functoid グループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0739-143">Click the functoid group containing your custom functoid.</span></span>  
  
   6. <span data-ttu-id="e0739-144">削除するをクリックする functoid を右クリックして**削除**または del キーを押します。</span><span class="sxs-lookup"><span data-stu-id="e0739-144">Right-click the functoid you want to remove, and then click **Delete** or press the delete key.</span></span>  
  
2. <span data-ttu-id="e0739-145">Functoid アセンブリの削除、 **Developer tools \mapper Extensions**ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="e0739-145">Remove the functoid assembly from the **Developer Tools\Mapper Extensions** directory.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="e0739-146">アセンブリにアクティブな functoid が含まれている場合は削除されません。</span><span class="sxs-lookup"><span data-stu-id="e0739-146">If an assembly contains active functoids, then do not remove it.</span></span> <span data-ttu-id="e0739-147">そうと、その他のマップが解除されます。</span><span class="sxs-lookup"><span data-stu-id="e0739-147">Doing so will break other maps.</span></span>  
  
   1. <span data-ttu-id="e0739-148">Windows エクスプ ローラーを起動しに移動し、 **Developer tools \mapper Extensions**ディレクトリ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="e0739-148">Start Windows Explorer and navigate to the **Developer Tools\Mapper Extensions** directory of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="e0739-149">削除の functoid を含むアセンブリを右クリックし、をクリックし、**削除**ファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="e0739-149">Right-click the assembly containing the removed functoid, and then click **Delete** to remove the file.</span></span>  
  
3. <span data-ttu-id="e0739-150">Functoid のアセンブリをグローバル アセンブリ キャッシュから削除します。</span><span class="sxs-lookup"><span data-stu-id="e0739-150">Remove the functoid assembly from the global assembly cache.</span></span> <span data-ttu-id="e0739-151">アセンブリにのみインライン型の functoid が含まれている場合は、この手順をスキップすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0739-151">If your assembly contains only inline functoids, then you can skip this step.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="e0739-152">アセンブリにアクティブな functoid が含まれている場合、グローバル アセンブリ キャッシュから削除されません。</span><span class="sxs-lookup"><span data-stu-id="e0739-152">If an assembly contains active functoids, then do not remove it from the global assembly cache.</span></span> <span data-ttu-id="e0739-153">そうと、その他のマップが解除されます。</span><span class="sxs-lookup"><span data-stu-id="e0739-153">Doing so will break other maps.</span></span>  
  
   1.  <span data-ttu-id="e0739-154">開始**Visual Studio コマンド プロンプト**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-154">Start **Visual Studio Command Prompt**.</span></span>  
  
   2.  <span data-ttu-id="e0739-155">コマンド プロンプトで「 **gacutil/u < assembly_display_name >** します。</span><span class="sxs-lookup"><span data-stu-id="e0739-155">At the command prompt, type **gacutil /u <assembly_display_name>**.</span></span> <span data-ttu-id="e0739-156">たとえば、アセンブリ名が FunctoidLibrary.dll の場合は、入力**gacutil/if FunctoidLibrary**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-156">For example, if your assembly name is FunctoidLibrary.dll, then type **gacutil /if FunctoidLibrary**.</span></span>  
  
   3.  <span data-ttu-id="e0739-157">入力が完了したら、**終了**します。</span><span class="sxs-lookup"><span data-stu-id="e0739-157">When you are finished, type **exit**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0739-158">参照</span><span class="sxs-lookup"><span data-stu-id="e0739-158">See Also</span></span>  
 [<span data-ttu-id="e0739-159">カスタム Functoid の開発</span><span class="sxs-lookup"><span data-stu-id="e0739-159">Developing Custom Functoids</span></span>](../core/developing-custom-functoids.md)