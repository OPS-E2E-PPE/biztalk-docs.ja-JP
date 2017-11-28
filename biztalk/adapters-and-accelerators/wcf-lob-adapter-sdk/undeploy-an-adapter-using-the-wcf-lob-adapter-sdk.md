---
title: "WCF LOB アダプター SDK を使用してアダプターを展開解除 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98f9a124-9e63-4451-af0e-ffee752fbeac
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a8da6ff335460cbd957a33ac5074f65205dfb77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="undeploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="0bdaa-102">WCF LOB アダプター SDK を使用してアダプターを展開解除します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-102">Undeploy an adapter using the WCF LOB adapter SDK</span></span>
<span data-ttu-id="0bdaa-103">コンピューターからアダプターを展開解除するには、ユーザーは、次の 2 つのタスクを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-103">To undeploy an adapter from a computer, the user needs to perform the following two tasks:</span></span>  
  
1.  <span data-ttu-id="0bdaa-104">グローバル アセンブリ キャッシュ (GAC) から、アダプター アセンブリ (と任意の依存アセンブリ) をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-104">Uninstall the adapter assembly (and any dependent assemblies) from the global assembly cache (GAC).</span></span>  
  
2.  <span data-ttu-id="0bdaa-105">Machine.config ファイルで、アダプターのバインドとアダプターのバインド要素を削除します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-105">Remove the adapter binding and adapter binding element in the machine.config file.</span></span>  
  
## <a name="uninstall-an-assembly-from-the-gac"></a><span data-ttu-id="0bdaa-106">アセンブリを GAC からアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-106">Uninstall an Assembly from the GAC</span></span>  
  
#### <a name="use-the-windows-interface"></a><span data-ttu-id="0bdaa-107">Windows インターフェイスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-107">Use the Windows interface</span></span>  
  
1.  <span data-ttu-id="0bdaa-108">次のように Windows エクスプ ローラーを開き: をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**アクセサリ**、順にクリック**Windows エクスプ ローラー**.</span><span class="sxs-lookup"><span data-stu-id="0bdaa-108">Open Windows Explorer as follows: Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
2.  <span data-ttu-id="0bdaa-109">Systemdrive%\Windows\Assembly に置かれている、GAC に参照します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-109">Browse to the GAC, which is located at %systemdrive%\Windows\Assembly.</span></span>  
  
3.  <span data-ttu-id="0bdaa-110">アプリケーションに含まれている各アセンブリ ファイルを右クリックし、をクリックして**アンインストール**、順にクリック**はい**ことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-110">Right-click each assembly file that is included in your application, click **Uninstall**, and then click **Yes** to confirm.</span></span>  
  
#### <a name="use-the-command-line"></a><span data-ttu-id="0bdaa-111">コマンドラインを使用してください。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-111">Use the command line</span></span>  
  
1.  <span data-ttu-id="0bdaa-112">開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-112">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
2.  <span data-ttu-id="0bdaa-113">コマンド プロンプトで、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-113">At the command prompt, type the following command:</span></span>  
  
     <span data-ttu-id="0bdaa-114">**gacutil/u** \<*の完全修飾**アセンブリ名*></span><span class="sxs-lookup"><span data-stu-id="0bdaa-114">**gacutil /u** \<*fully qualified**assembly name*></span></span>  
  
     <span data-ttu-id="0bdaa-115">このコマンドでは、アセンブリ名は、GAC からアンインストールするアセンブリの名前です。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-115">In this command, the assembly name is the name of the assembly to uninstall from the GAC.</span></span>  
  
     <span data-ttu-id="0bdaa-116">アセンブリ hello.dll を GAC から削除する例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-116">The following example removes an assembly named hello.dll from the GAC.</span></span>  
  
     `gacutil /u "MyAdapter,Version=1.0.0.0, Culture=neutral, PublicKeyToken=fafafafafafafafa"`
  
## <a name="remove-the-adapter-binding-from-the-machineconfig-file"></a><span data-ttu-id="0bdaa-117">Machine.config ファイルからアダプターのバインドを削除します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-117">Remove the Adapter Binding from the Machine.config File</span></span>  
 <span data-ttu-id="0bdaa-118">手動でアダプターのバインドを解除、machine.config ファイルを編集したり、サービス構成エディターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-118">You can manually edit the machine.config file to remove the adapter binding, or use the Service Configuration Editor.</span></span> <span data-ttu-id="0bdaa-119">このセクションでは、両方の手順を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-119">This section lists both steps.</span></span> 
  
#### <a name="manually-edit-the-machineconfig-file"></a><span data-ttu-id="0bdaa-120">Machine.config ファイルを手動で編集します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-120">Manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="0bdaa-121">Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-121">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="0bdaa-122">これを行うには、をクリックして**開始**をクリックして**実行**、型**メモ帳\<Windows のインストール パス > \Microsoft.NET\Framework\\< バージョン\>\CONFIG\machine.config**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-122">To do this, click **Start**, click **Run**, type **notepad \<Windows install path>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config**, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bdaa-123">編集の誤りを防ぐ変更する前に、machine.config ファイルのバックアップを作成します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-123">Make a backup of the machine.config file before you make changes to guard against editing mistakes.</span></span>  
  
2.  <span data-ttu-id="0bdaa-124">Machine.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-124">Update the machine.config file.</span></span> <span data-ttu-id="0bdaa-125">削除するアダプターの bindingExtensions 要素を探します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-125">Find the bindingExtensions element for the adapter you want to remove.</span></span> <span data-ttu-id="0bdaa-126">存在するその他の情報に基づき、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-126">Based on the other information that is present, do one of the following:</span></span>  
  
    -   <span data-ttu-id="0bdaa-127">その他の bindingExtensions がある場合は、アダプター拡張機能のみを削除します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-127">If there are other bindingExtensions, remove only your adapter extension.</span></span>  
  
    -   <span data-ttu-id="0bdaa-128">その他の bindingExtensions がない場合 (アダプター拡張機能を含む)、bindingExtensions セクションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-128">If there are no other bindingExtensions, you can remove the bindingExtensions section (including your adapter extension).</span></span>  
  
    -   <span data-ttu-id="0bdaa-129">その他の bindingExtensions または拡張機能しない場合は、拡張セクションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-129">If there are no other bindingExtensions or extensions, you can remove the extensions section.</span></span>  
  
    -   <span data-ttu-id="0bdaa-130">最後に、system.serviceModel アダプター拡張機能のみが含まれている場合は、全体の system.serviceModel セクションを削除できます。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-130">Finally, if system.serviceModel contains only your adapter extension, you can remove the entire system.serviceModel section.</span></span>  
  
3.  <span data-ttu-id="0bdaa-131">BindingElementExtensions 要素に対して、手順 2. を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-131">Repeat step 2 for the bindingElementExtensions element.</span></span>  
  
4.  <span data-ttu-id="0bdaa-132">machine.config ファイルを閉じて保存します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-132">Close and save the machine.config file.</span></span>  
  
#### <a name="use-the-service-configuration-editor-do-change-the-machineconfig-file"></a><span data-ttu-id="0bdaa-133">サービス構成エディターを使用して、machine.config ファイルを変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-133">Use the Service Configuration Editor do change the machine.config file</span></span>  
  
1.  <span data-ttu-id="0bdaa-134">サービス構成エディタを開きます。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-134">Open Service Configuration Editor.</span></span> <span data-ttu-id="0bdaa-135">参照してください[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-135">See [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) for more information.</span></span>
  
2.  <span data-ttu-id="0bdaa-136">ツリー ビュー ウィンドウ (ラベルの付いた**構成**)、ノード ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-136">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="0bdaa-137">をクリックして、 **[詳細設定]**フォルダーで、をクリックして、**拡張機能**フォルダー、およびバインド拡張要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-137">Click the **Advanced** folder, click the **Extensions** folder, and then select the binding extensions element.</span></span>  
  
3.  <span data-ttu-id="0bdaa-138">バインド拡張機能のエディターの詳細ウィンドウで [削除、およびをクリックする、バインド拡張機能] をクリックして**削除**です。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-138">In the details pane of the Binding Extensions Editor, click the binding extension that you want to delete, and then click **Delete**.</span></span> <span data-ttu-id="0bdaa-139">次の図に MyAdapterExtension が強調表示され、削除されます。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-139">In the following figure, MyAdapterExtension is highlighted and will be deleted.</span></span>  
  
     <span data-ttu-id="0bdaa-140">![追加された拡張機能とサービス構成エディター。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span><span class="sxs-lookup"><span data-stu-id="0bdaa-140">![Service configuration editor with added extension.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span></span>  
  
4.  <span data-ttu-id="0bdaa-141">サービス構成エディタを閉じます。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-141">Close the Service Configuration Editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bdaa-142">参照</span><span class="sxs-lookup"><span data-stu-id="0bdaa-142">See Also</span></span>  
 <span data-ttu-id="0bdaa-143">[展開の制限事項](../../core/deployment-limitations1.md) </span><span class="sxs-lookup"><span data-stu-id="0bdaa-143">[Deployment Limitations](../../core/deployment-limitations1.md) </span></span>  
 [<span data-ttu-id="0bdaa-144">WCF LOB アダプター SDK を使用して、アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="0bdaa-144">Deploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)