---
title: "WCF LOB アダプター SDK を使用して、アダプターの展開 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 376b4dcf-2d2c-4872-a394-67edc0c3d088
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72c83998bbe16899055c839a73795d456a132381
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2017
---
# <a name="deploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="bc061-102">WCF LOB アダプター SDK を使用して、アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc061-102">Deploy an adapter using the WCF LOB adapter SDK</span></span>
<span data-ttu-id="bc061-103">アダプターを展開するにはアダプター アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールし、machine.config ファイルにアダプターを登録します。</span><span class="sxs-lookup"><span data-stu-id="bc061-103">To deploy an adapter, you must install the adapter assembly into the global assembly cache (GAC), and then register the adapter in the machine.config file.</span></span>  
  
## <a name="install-the-adapter-assembly-into-the-gac"></a><span data-ttu-id="bc061-104">アダプター アセンブリを GAC にインストールします。</span><span class="sxs-lookup"><span data-stu-id="bc061-104">Install the Adapter Assembly into the GAC</span></span>  
 <span data-ttu-id="bc061-105">Visual Studio を使用してアダプターを使用する前に、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]コマンドまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]機能、アセンブリを GAC にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc061-105">Before consuming an adapter in Visual Studio using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] command or in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] by using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] feature, you must install the assembly into the GAC.</span></span> <span data-ttu-id="bc061-106">厳密な名前であるアセンブリのみを GAC にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bc061-106">Only assemblies that are strong-named can be installed into the GAC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc061-107">この手順を完了するには、GAC に対する書き込み権限を持つアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc061-107">To complete this procedure, you must be logged on with an account that has Write permissions on the GAC.</span></span> <span data-ttu-id="bc061-108">ローカル コンピューターの管理者アカウントには、これらのアクセス許可が与えられています。</span><span class="sxs-lookup"><span data-stu-id="bc061-108">The Administrators account on the local computer has these permissions.</span></span>  
  
#### <a name="configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="bc061-109">厳密な名前のアセンブリ キー ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="bc061-109">Configure a strong name assembly key file</span></span>  
  
1.  <span data-ttu-id="bc061-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、厳密な名前が必要なアダプター プロジェクト ファイルを読み込めません。</span><span class="sxs-lookup"><span data-stu-id="bc061-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], load the adapter project file that needs a strong name.</span></span>  
  
2.  <span data-ttu-id="bc061-111">開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="bc061-111">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
3.  <span data-ttu-id="bc061-112">コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bc061-112">At the command prompt, from the folder where you want to store the key file, type the following command, and then press ENTER:</span></span>  
  
     <span data-ttu-id="bc061-113">**sn/k***file_name* **.snk** </span><span class="sxs-lookup"><span data-stu-id="bc061-113">**sn /k**  *file_name* **.snk**</span></span>  
  
     <span data-ttu-id="bc061-114">例: **sn/k EchoAdapter.snk**</span><span class="sxs-lookup"><span data-stu-id="bc061-114">Example: **sn /k EchoAdapter.snk**</span></span>  
  
     <span data-ttu-id="bc061-115">確認メッセージを**キーのペアに書き込まれる** \< *file_name*>**.snk** `,`コマンド ラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc061-115">A confirmation message, **Key pair written to** \<*file_name*>**.snk**`,` displays on the command line.</span></span>  
  
4.  <span data-ttu-id="bc061-116">Visual Studio ソリューション エクスプ ローラーでプロジェクトを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="bc061-116">In Visual Studio Solution Explorer, right-click the project, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="bc061-117">左側のウィンドウで展開**共通プロパティ**、クリックして**アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="bc061-117">In the left pane, expand **Common Properties**, and then click **Assembly**.</span></span>  
  
6.  <span data-ttu-id="bc061-118">右側のペインでまでスクロールし、**厳密な名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="bc061-118">In the right pane, scroll to the **Strong name** box.</span></span>  
  
7.  <span data-ttu-id="bc061-119">**厳密な名前**ボックス フィールドをクリックして、横に**アセンブリ キー ファイル**、参照ボタンをクリックして (**.**)、キー ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="bc061-119">In the **Strong name** box, click the field next to **Assembly Key File**, click the browse button (**…**), and then browse to the key file.</span></span>  
  
8.  <span data-ttu-id="bc061-120">キー ファイルをクリックし、をクリックして**開く**、順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="bc061-120">Click the key file, click **Open**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="bc061-121">Visual Studio のメニューをクリックして**ビルド**を選択し**ソリューションのビルド**です。</span><span class="sxs-lookup"><span data-stu-id="bc061-121">On the Visual Studio menu, click **Build**, and then choose **Build Solution**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bc061-122">アダプターのアセンブリは、他のアセンブリに依存している場合は、これらの参照先アセンブリが厳密な名前で署名されたことを確認します。それ以外の場合、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc061-122">If your adapter assembly depends on any other assemblies, ensure these referenced assemblies are signed with a strong name; otherwise you will get an error.</span></span>  
  
 <span data-ttu-id="bc061-123">ソースがある場合は、上記のように厳密な名前で再コンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="bc061-123">If you have the source, you can recompile with a strong name as shown previously.</span></span> <span data-ttu-id="bc061-124">参照アセンブリ、サードパーティに属している、厳密な名前を指定、ことを確認できない場合は、逆アセンブルし、厳密な名前でアセンブリを再構成できます。</span><span class="sxs-lookup"><span data-stu-id="bc061-124">If the reference assembly belongs to a third-party and you cannot ensure that it will be given a strong name, you can disassemble and then reassemble the assembly with a strong name.</span></span>  
  
 <span data-ttu-id="bc061-125">元のアセンブリは上書きされるため、元のバージョンを保持する場合を確認する、次の手順に進む前のバックアップ コピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="bc061-125">Your original assembly will be overwritten, so if you want to keep the original version, ensure you make a backup copy of it before proceeding with the following steps.</span></span>  
  
 <span data-ttu-id="bc061-126">Microsoft Intermediate Language (MSIL) の逆アセンブラーを使用して、アセンブリを逆アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="bc061-126">Use Microsoft Intermediate Language (MSIL) Disassembler to disassemble the assembly:</span></span>  
  
-   <span data-ttu-id="bc061-127">ILDASM thirdparty.dll/out:thirdparty.il</span><span class="sxs-lookup"><span data-stu-id="bc061-127">ILDASM thirdparty.dll /out:thirdparty.il</span></span>  
  
 <span data-ttu-id="bc061-128">MSIL アセンブラーを使用して、厳密な名前でアセンブリを再アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="bc061-128">Use MSIL Assembler to reassemble the assembly with a strong name:</span></span>  
  
-   <span data-ttu-id="bc061-129">ILASM thirdparty.il/dll/key=strongkeyfile.snk</span><span class="sxs-lookup"><span data-stu-id="bc061-129">ILASM thirdparty.il /dll /key=strongkeyfile.snk</span></span>  
  
#### <a name="install-an-assembly-in-the-gac"></a><span data-ttu-id="bc061-130">アセンブリを GAC にインストールします。</span><span class="sxs-lookup"><span data-stu-id="bc061-130">Install an assembly in the GAC</span></span>  
  
1.  <span data-ttu-id="bc061-131">アダプターが署名されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bc061-131">Verify that your adapter has been signed.</span></span>  
  
2.  <span data-ttu-id="bc061-132">開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプトです。</span><span class="sxs-lookup"><span data-stu-id="bc061-132">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
3.  <span data-ttu-id="bc061-133">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="bc061-133">Type the following command:</span></span>  
  
     <span data-ttu-id="bc061-134">**gacutil.exe/if"\<**  *アセンブリ .dll ファイルのパスを* **>"**</span><span class="sxs-lookup"><span data-stu-id="bc061-134">**gacutil.exe /if "\<** *path to the assembly .dll file* **>"**</span></span>  
  
4.  <span data-ttu-id="bc061-135">これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="bc061-135">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
## <a name="register-the-adapter-in-machineconfig"></a><span data-ttu-id="bc061-136">Machine.config でアダプターを登録します。</span><span class="sxs-lookup"><span data-stu-id="bc061-136">Register the Adapter in Machine.config</span></span>  
 <span data-ttu-id="bc061-137">使用して、アダプターの開発、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF バインドとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc061-137">An adapter developed using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is surfaced as a WCF binding.</span></span>  <span data-ttu-id="bc061-138">詳細については、Microsoft.ServiceModel.Channels.Common.AdapterBinding を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc061-138">See Microsoft.ServiceModel.Channels.Common.AdapterBinding for more information.</span></span>  <span data-ttu-id="bc061-139">WCF アダプター バインドに登録を使用して\<bindingExtensions > セクション内\<システムです。ServiceModel > WCF アダプター トランスポートのバインド要素が登録されるとを使用して\<bindingElementExtensions > セクション内\<システムです。ServiceModel >。</span><span class="sxs-lookup"><span data-stu-id="bc061-139">The adapter binding is registered with WCF using \<bindingExtensions> section within \<system.ServiceModel> and the adapter transport binding element is registered with WCF using \<bindingElementExtensions> section within \<system.ServiceModel>.</span></span>  
  
 <span data-ttu-id="bc061-140">テキスト エディターを使用して、machine.config ファイルを手動で編集することができます。</span><span class="sxs-lookup"><span data-stu-id="bc061-140">You can manually edit the machine.config file using a text editor.</span></span>  
  
#### <a name="manually-edit-the-machineconfig-file"></a><span data-ttu-id="bc061-141">Machine.config ファイルを手動で編集します。</span><span class="sxs-lookup"><span data-stu-id="bc061-141">Manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="bc061-142">Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="bc061-142">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="bc061-143">これを行うには、をクリックして**開始**をクリックして**実行**、「notepad \<Windows のインストール パス > \Microsoft.NET\Framework\\< バージョン\>\CONFIG\machine.config、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="bc061-143">To do this, click **Start**, click **Run**, type notepad \<Windows install path>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="bc061-144">Machine.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="bc061-144">Update the machine.config file.</span></span> <span data-ttu-id="bc061-145">ファイルに system.serviceModel セクションが含まれていない場合は、ルート タグの終わりの前に、構成ファイルの末尾に次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="bc061-145">If the file does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bc061-146">"MyAdapterBinding"、バージョン、カルチャ、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="bc061-146">Replace "myAdapterBinding", version, culture and other assembly-specific information with your adapter's information.</span></span>  
  
    ```  
    \<system.serviceModel>  
      <extensions>  
        <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
        </bindingExtensions>      <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
      </extensions>  
    \</system.serviceModel>  
    ```  
  
     - <span data-ttu-id="bc061-147">または -</span><span class="sxs-lookup"><span data-stu-id="bc061-147">OR -</span></span>  
  
     <span data-ttu-id="bc061-148">Machine.config ファイルの system.serviceModel セクションが含まれている場合は、のどの要素が不足しているは、"MyAdapter"とその他の情報をアダプターの情報に置き換えるを加算してを決定します。</span><span class="sxs-lookup"><span data-stu-id="bc061-148">If your machine.config file contains a system.serviceModel section, determine which elements are missing and add them, replacing "MyAdapter" and other information with your adapter's information.</span></span>  
  
    ```  
    <extensions>  
      <bindingExtensions>  
            <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
      </bindingExtensions>  
          <bindingElementExtensions>  
            <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
          </bindingElementExtensions>  
    </extensions>  
    ```  
  
3.  <span data-ttu-id="bc061-149">machine.config ファイルを閉じて保存します。</span><span class="sxs-lookup"><span data-stu-id="bc061-149">Close and save the machine.config file.</span></span>  
  
 <span data-ttu-id="bc061-150">使用することも、[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx) machine.config ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="bc061-150">You can also use the [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) to modify the machine.config file.</span></span>
  
#### <a name="edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="bc061-151">サービス構成エディターを使用して、machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="bc061-151">Edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="bc061-152">開く、**サービス構成エディター**です。</span><span class="sxs-lookup"><span data-stu-id="bc061-152">Open the **Service Configuration Editor**.</span></span> <span data-ttu-id="bc061-153">参照してください[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="bc061-153">See [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) for  more information.</span></span>
  
2.  <span data-ttu-id="bc061-154">ツリー ビュー ウィンドウ (ラベルの付いた**構成**)、ノード ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc061-154">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="bc061-155">をクリックして、 **[詳細設定]**フォルダーで、をクリックして、**拡張機能**フォルダー、およびバインド拡張要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="bc061-155">Click the **Advanced** folder, click the **Extensions** folder, and then select the binding extensions element.</span></span>  
  
     <span data-ttu-id="bc061-156">![サービス構成エディター。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")</span><span class="sxs-lookup"><span data-stu-id="bc061-156">![Service configuration editor.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")</span></span>  
  
3.  <span data-ttu-id="bc061-157">新しいバインディング拡張を作成します。</span><span class="sxs-lookup"><span data-stu-id="bc061-157">Create a new binding extension.</span></span> <span data-ttu-id="bc061-158">クリックして、**新規**を開くには、拡張ボタン**構成要素エディタ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bc061-158">Click the **New** button to open the Extension **Configuration Element Editor** dialog box.</span></span> <span data-ttu-id="bc061-159">**構成名**、たとえば、拡張機能の一意の名前を入力*MyAdapterExtension*です。</span><span class="sxs-lookup"><span data-stu-id="bc061-159">In **Configuration Name**, enter a unique name for the extensions, for example *MyAdapterExtension*.</span></span>  
  
     <span data-ttu-id="bc061-160">![Extension 構成要素エディタ](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")</span><span class="sxs-lookup"><span data-stu-id="bc061-160">![Extension configuration element editor](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")</span></span>  
  
4.  <span data-ttu-id="bc061-161">クリックして、**型**フィールドに、省略記号ボタンをクリックして (**.**) を開くには、**バインド拡張型ブラウザー**  ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bc061-161">Click the **Type** field, and then click the ellipsis button (**...**) to open the **Binding Extension Type Browser** dialog box.</span></span>  
  
5.  <span data-ttu-id="bc061-162">GAC の Dll を一覧表示する、グローバル アセンブリ キャッシュ (GAC) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc061-162">Click the global assembly cache (GAC) icon to list the DLLs in the GAC.</span></span>  
  
6.  <span data-ttu-id="bc061-163">アダプターのアセンブリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc061-163">Click your adapter assembly.</span></span>  
  
     <span data-ttu-id="bc061-164">![拡張型ブラウザーの構築します。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")</span><span class="sxs-lookup"><span data-stu-id="bc061-164">![Building extension type browser.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")</span></span>  
  
7.  <span data-ttu-id="bc061-165">クリックして、**開く**ボタンをクリックして、アセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="bc061-165">Click the **Open** button to select the assembly.</span></span>  
  
8.  <span data-ttu-id="bc061-166">**バインド拡張型ブラウザー**  ダイアログ ボックスで、バインディング コレクションの要素を実装した型名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc061-166">In the **Binding Extension Type Browser** dialog box, click the type name that implements the binding collection element.</span></span>  
  
     <span data-ttu-id="bc061-167">![拡張型ブラウザーの構築します。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")</span><span class="sxs-lookup"><span data-stu-id="bc061-167">![Building extension type browser.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")</span></span>  
  
9. <span data-ttu-id="bc061-168">クリックして、**開く**ボタンの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="bc061-168">Click the **Open** button to select the type.</span></span>  
  
10. <span data-ttu-id="bc061-169">をクリックして**OK**を閉じる、 **Extension 構成要素エディタ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="bc061-169">Click **OK** to close the **Extension Configuration Element Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="bc061-170">詳細ウィンドウで、**バインディング拡張エディター**、バインド拡張機能が表示されることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bc061-170">In the details pane of the **Binding Extensions Editor**, verify that your binding extension appears.</span></span> <span data-ttu-id="bc061-171">次の図に MyAdapterExtension は強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="bc061-171">In the following figure, MyAdapterExtension is highlighted.</span></span>  
  
     <span data-ttu-id="bc061-172">![追加された拡張機能とサービス構成エディター。] (../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span><span class="sxs-lookup"><span data-stu-id="bc061-172">![Service configuration editor with added extension.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span></span>  
  
12. <span data-ttu-id="bc061-173">閉じる、**サービス構成エディター**です。</span><span class="sxs-lookup"><span data-stu-id="bc061-173">Close the **Service Configuration Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc061-174">参照</span><span class="sxs-lookup"><span data-stu-id="bc061-174">See Also</span></span>  
 [<span data-ttu-id="bc061-175">WCF LOB アダプター SDK を使用して、アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="bc061-175">Deploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)