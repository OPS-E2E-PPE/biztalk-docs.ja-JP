---
title: WCF LOB アダプター SDK を使用して、アダプターの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 376b4dcf-2d2c-4872-a394-67edc0c3d088
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa1ad45eeafae2f6f91936124f01677b5dc6c32a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363713"
---
# <a name="deploy-an-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="54687-102">WCF LOB アダプター SDK を使用して、アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="54687-102">Deploy an adapter using the WCF LOB adapter SDK</span></span>
<span data-ttu-id="54687-103">アダプターを展開するには、アダプター アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールして、machine.config ファイルでアダプターを登録します。</span><span class="sxs-lookup"><span data-stu-id="54687-103">To deploy an adapter, you must install the adapter assembly into the global assembly cache (GAC), and then register the adapter in the machine.config file.</span></span>  
  
## <a name="install-the-adapter-assembly-into-the-gac"></a><span data-ttu-id="54687-104">アダプターのアセンブリを GAC にインストールします。</span><span class="sxs-lookup"><span data-stu-id="54687-104">Install the Adapter Assembly into the GAC</span></span>  
 <span data-ttu-id="54687-105">Visual Studio を使用してアダプターを使用する前に、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]コマンドまたは[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]を使用して、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]機能、GAC にアセンブリをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54687-105">Before consuming an adapter in Visual Studio using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] command or in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] by using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] feature, you must install the assembly into the GAC.</span></span> <span data-ttu-id="54687-106">厳密な名前であるアセンブリだけを GAC にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="54687-106">Only assemblies that are strong-named can be installed into the GAC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54687-107">この手順を完了するには、GAC に対する書き込み権限を持つアカウントでログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="54687-107">To complete this procedure, you must be logged on with an account that has Write permissions on the GAC.</span></span> <span data-ttu-id="54687-108">ローカル コンピューターの管理者アカウントには、これらのアクセス許可が与えられています。</span><span class="sxs-lookup"><span data-stu-id="54687-108">The Administrators account on the local computer has these permissions.</span></span>  
  
#### <a name="configure-a-strong-name-assembly-key-file"></a><span data-ttu-id="54687-109">厳密な名前のアセンブリ キー ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="54687-109">Configure a strong name assembly key file</span></span>  
  
1. <span data-ttu-id="54687-110">[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、厳密な名前が必要なアダプター プロジェクト ファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="54687-110">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], load the adapter project file that needs a strong name.</span></span>  
  
2. <span data-ttu-id="54687-111">開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプト。</span><span class="sxs-lookup"><span data-stu-id="54687-111">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
3. <span data-ttu-id="54687-112">コマンド プロンプトで、キー ファイルを格納するフォルダーから次のコマンドを入力し、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="54687-112">At the command prompt, from the folder where you want to store the key file, type the following command, and then press ENTER:</span></span>  
  
    <span data-ttu-id="54687-113">**sn /k**  *file_name* **.snk**</span><span class="sxs-lookup"><span data-stu-id="54687-113">**sn /k**  *file_name* **.snk**</span></span>  
  
    <span data-ttu-id="54687-114">例: **sn/k EchoAdapter.snk**</span><span class="sxs-lookup"><span data-stu-id="54687-114">Example: **sn /k EchoAdapter.snk**</span></span>  
  
    <span data-ttu-id="54687-115">確認メッセージ、**キーのペアに書き込まれる** \< *file_name*\>**.snk** `,`コマンド ラインで表示されます。</span><span class="sxs-lookup"><span data-stu-id="54687-115">A confirmation message, **Key pair written to** \<*file_name*\>**.snk**`,` displays on the command line.</span></span>  
  
4. <span data-ttu-id="54687-116">Visual Studio ソリューション エクスプ ローラーでプロジェクトを右クリックし、クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="54687-116">In Visual Studio Solution Explorer, right-click the project, and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="54687-117">左側のウィンドウで展開**共通プロパティ**、 をクリックし、**アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="54687-117">In the left pane, expand **Common Properties**, and then click **Assembly**.</span></span>  
  
6. <span data-ttu-id="54687-118">右側のウィンドウのスクロール、**厳密な名前**ボックス。</span><span class="sxs-lookup"><span data-stu-id="54687-118">In the right pane, scroll to the **Strong name** box.</span></span>  
  
7. <span data-ttu-id="54687-119">**厳密な名前**ボックスで、フィールドの横に **アセンブリ キー ファイル**、参照ボタンをクリックします (**.**)、キー ファイルを参照します。</span><span class="sxs-lookup"><span data-stu-id="54687-119">In the **Strong name** box, click the field next to **Assembly Key File**, click the browse button (**…**), and then browse to the key file.</span></span>  
  
8. <span data-ttu-id="54687-120">キー ファイルをクリックして**オープン**、順にクリックします**OK**します。</span><span class="sxs-lookup"><span data-stu-id="54687-120">Click the key file, click **Open**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="54687-121">Visual Studio のメニュー**ビルド**を選び、**ソリューションのビルド**。</span><span class="sxs-lookup"><span data-stu-id="54687-121">On the Visual Studio menu, click **Build**, and then choose **Build Solution**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54687-122">アダプターのアセンブリは、他のアセンブリに依存する場合は、これらの参照先アセンブリが; 厳密な名前で署名されたことを確認します。それ以外の場合、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="54687-122">If your adapter assembly depends on any other assemblies, ensure these referenced assemblies are signed with a strong name; otherwise you will get an error.</span></span>  
  
 <span data-ttu-id="54687-123">ソースがある場合は、前述のように厳密な名前で再コンパイルすることができます。</span><span class="sxs-lookup"><span data-stu-id="54687-123">If you have the source, you can recompile with a strong name as shown previously.</span></span> <span data-ttu-id="54687-124">参照アセンブリがサード パーティに属する厳密な名前を指定があることを確認できない場合は、逆アセンブルし、厳密な名前でアセンブリを再構築し、できます。</span><span class="sxs-lookup"><span data-stu-id="54687-124">If the reference assembly belongs to a third-party and you cannot ensure that it will be given a strong name, you can disassemble and then reassemble the assembly with a strong name.</span></span>  
  
 <span data-ttu-id="54687-125">元のアセンブリは上書きされます、元のバージョンを保持したい場合は、確認するため、次の手順に進む前のバックアップ コピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="54687-125">Your original assembly will be overwritten, so if you want to keep the original version, ensure you make a backup copy of it before proceeding with the following steps.</span></span>  
  
 <span data-ttu-id="54687-126">アセンブリを逆アセンブルするのにには、Microsoft Intermediate Language (MSIL) の逆アセンブラーを使用します。</span><span class="sxs-lookup"><span data-stu-id="54687-126">Use Microsoft Intermediate Language (MSIL) Disassembler to disassemble the assembly:</span></span>  
  
- <span data-ttu-id="54687-127">ILDASM thirdparty.dll/out:thirdparty.il</span><span class="sxs-lookup"><span data-stu-id="54687-127">ILDASM thirdparty.dll /out:thirdparty.il</span></span>  
  
  <span data-ttu-id="54687-128">MSIL アセンブラーを使用して、厳密な名前でアセンブリを再アセンブルします。</span><span class="sxs-lookup"><span data-stu-id="54687-128">Use MSIL Assembler to reassemble the assembly with a strong name:</span></span>  
  
- <span data-ttu-id="54687-129">ILASM thirdparty.il/dll/key=strongkeyfile.snk</span><span class="sxs-lookup"><span data-stu-id="54687-129">ILASM thirdparty.il /dll /key=strongkeyfile.snk</span></span>  
  
#### <a name="install-an-assembly-in-the-gac"></a><span data-ttu-id="54687-130">アセンブリを GAC にインストールします。</span><span class="sxs-lookup"><span data-stu-id="54687-130">Install an assembly in the GAC</span></span>  
  
1. <span data-ttu-id="54687-131">アダプターが署名されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54687-131">Verify that your adapter has been signed.</span></span>  
  
2. <span data-ttu-id="54687-132">開く、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]コマンド プロンプト。</span><span class="sxs-lookup"><span data-stu-id="54687-132">Open a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] command prompt.</span></span>  
  
3. <span data-ttu-id="54687-133">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="54687-133">Type the following command:</span></span>  
  
    <span data-ttu-id="54687-134">**gacutil.exe/if"\<**  *アセンブリ .dll ファイルへのパス*  **\>"**</span><span class="sxs-lookup"><span data-stu-id="54687-134">**gacutil.exe /if "\<** *path to the assembly .dll file* **\>"**</span></span>  
  
4. <span data-ttu-id="54687-135">これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="54687-135">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
## <a name="register-the-adapter-in-machineconfig"></a><span data-ttu-id="54687-136">Machine.config にアダプターを登録します。</span><span class="sxs-lookup"><span data-stu-id="54687-136">Register the Adapter in Machine.config</span></span>  
 <span data-ttu-id="54687-137">使用して、アダプターの開発、 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF バインドとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="54687-137">An adapter developed using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] is surfaced as a WCF binding.</span></span>  <span data-ttu-id="54687-138">詳細については、Microsoft.ServiceModel.Channels.Common.AdapterBinding を参照してください。</span><span class="sxs-lookup"><span data-stu-id="54687-138">See Microsoft.ServiceModel.Channels.Common.AdapterBinding for more information.</span></span>  <span data-ttu-id="54687-139">Wcf アダプター バインドが登録されているを使用して\<bindingExtensions\>セクション内\<システム。ServiceModel\> wcf アダプターのトランスポート バインド要素が登録されているとを使用して\<bindingElementExtensions\>セクション内\<システム。ServiceModel\>します。</span><span class="sxs-lookup"><span data-stu-id="54687-139">The adapter binding is registered with WCF using \<bindingExtensions\> section within \<system.ServiceModel\> and the adapter transport binding element is registered with WCF using \<bindingElementExtensions\> section within \<system.ServiceModel\>.</span></span>  
  
 <span data-ttu-id="54687-140">テキスト エディターを使用して、machine.config ファイルを手動で編集することができます。</span><span class="sxs-lookup"><span data-stu-id="54687-140">You can manually edit the machine.config file using a text editor.</span></span>  
  
#### <a name="manually-edit-the-machineconfig-file"></a><span data-ttu-id="54687-141">Machine.config ファイルを手動で編集します。</span><span class="sxs-lookup"><span data-stu-id="54687-141">Manually edit the machine.config file</span></span>  
  
1. <span data-ttu-id="54687-142">Microsoft .NET の構成フォルダーにある machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="54687-142">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="54687-143">これを行うには、次のようにクリックします**開始**、 をクリック**実行**、「notepad \<Windows インストール パス\>\Microsoft.NET\Framework\\< バージョン\>\CONFIG\。クリックして、machine.config **OK**します。</span><span class="sxs-lookup"><span data-stu-id="54687-143">To do this, click **Start**, click **Run**, type notepad \<Windows install path\>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="54687-144">Machine.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="54687-144">Update the machine.config file.</span></span> <span data-ttu-id="54687-145">ファイルに system.serviceModel セクションが含まれていない場合は、終了タグをルートする前に、構成ファイルの末尾に次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="54687-145">If the file does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="54687-146">"MyAdapterBinding"、バージョン、カルチャ、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="54687-146">Replace "myAdapterBinding", version, culture and other assembly-specific information with your adapter's information.</span></span>  
  
   ```  
   <system.serviceModel>  
     <extensions>  
       <bindingExtensions>  
           <add name="myAdapterBinding" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingCollectionElement,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken= fafafafafafafafa" />  
       </bindingExtensions>      <bindingElementExtensions>  
           <add name="echoAdapter" type="Microsoft.Adapters.Samples.Echo.EchoAdapterBindingElementExtension,EchoAdapter, Version=0.0.0.0, Culture=neutral, PublicKeyToken=37f23b4adb996dcf" />  
         </bindingElementExtensions>  
     </extensions>  
   </system.serviceModel>  
   ```  
  
   - <span data-ttu-id="54687-147">または -</span><span class="sxs-lookup"><span data-stu-id="54687-147">OR -</span></span>  
  
     <span data-ttu-id="54687-148">Machine.config ファイルに system.serviceModel セクションが含まれている場合は、要素が不足しているとアダプターの情報に置き換えて"MyAdapter"その他の情報を追加を決定します。</span><span class="sxs-lookup"><span data-stu-id="54687-148">If your machine.config file contains a system.serviceModel section, determine which elements are missing and add them, replacing "MyAdapter" and other information with your adapter's information.</span></span>  
  
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
  
3. <span data-ttu-id="54687-149">Machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="54687-149">Close and save the machine.config file.</span></span>  
  
   <span data-ttu-id="54687-150">使用することも、[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx) machine.config ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="54687-150">You can also use the [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) to modify the machine.config file.</span></span>
  
#### <a name="edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="54687-151">サービス構成エディターを使用して、machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="54687-151">Edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="54687-152">開く、**サービス構成エディター**します。</span><span class="sxs-lookup"><span data-stu-id="54687-152">Open the **Service Configuration Editor**.</span></span> <span data-ttu-id="54687-153">参照してください[サービス構成エディター](https://msdn.microsoft.com/library/ms732009.aspx)詳細についてはします。</span><span class="sxs-lookup"><span data-stu-id="54687-153">See [Service Configuration Editor](https://msdn.microsoft.com/library/ms732009.aspx) for  more information.</span></span>
  
2.  <span data-ttu-id="54687-154">ツリー ビュー ペインで (というラベルの付いた**構成**)、ノード ツリーを展開します。</span><span class="sxs-lookup"><span data-stu-id="54687-154">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="54687-155">をクリックして、 **詳細設定**フォルダー、 をクリックして、**拡張**フォルダー、およびバインド拡張機能の要素を選択します。</span><span class="sxs-lookup"><span data-stu-id="54687-155">Click the **Advanced** folder, click the **Extensions** folder, and then select the binding extensions element.</span></span>  
  
     <span data-ttu-id="54687-156">![サービス構成エディター。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")</span><span class="sxs-lookup"><span data-stu-id="54687-156">![Service configuration editor.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/0a44a070-b788-4287-bd9e-c946fafcf11c.gif "0a44a070-b788-4287-bd9e-c946fafcf11c")</span></span>  
  
3.  <span data-ttu-id="54687-157">新しいバインディング拡張機能を作成します。</span><span class="sxs-lookup"><span data-stu-id="54687-157">Create a new binding extension.</span></span> <span data-ttu-id="54687-158">をクリックして、**新規**、拡張機能を開くにはボタン**構成要素エディタ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="54687-158">Click the **New** button to open the Extension **Configuration Element Editor** dialog box.</span></span> <span data-ttu-id="54687-159">**構成名**、たとえば、拡張機能の一意の名前を入力*MyAdapterExtension*します。</span><span class="sxs-lookup"><span data-stu-id="54687-159">In **Configuration Name**, enter a unique name for the extensions, for example *MyAdapterExtension*.</span></span>  
  
     <span data-ttu-id="54687-160">![Extension 構成要素エディタ](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")</span><span class="sxs-lookup"><span data-stu-id="54687-160">![Extension configuration element editor](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/1398a256-00fa-4591-99ee-54298a8cf6e3.gif "1398a256-00fa-4591-99ee-54298a8cf6e3")</span></span>  
  
4.  <span data-ttu-id="54687-161">をクリックして、**型**フィールドし、省略記号ボタンをクリックして (**.**) を開く、**バインド拡張型ブラウザ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="54687-161">Click the **Type** field, and then click the ellipsis button (**...**) to open the **Binding Extension Type Browser** dialog box.</span></span>  
  
5.  <span data-ttu-id="54687-162">GAC に Dll を一覧表示する、グローバル アセンブリ キャッシュ (GAC) アイコンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54687-162">Click the global assembly cache (GAC) icon to list the DLLs in the GAC.</span></span>  
  
6.  <span data-ttu-id="54687-163">アダプターのアセンブリをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54687-163">Click your adapter assembly.</span></span>  
  
     <span data-ttu-id="54687-164">![拡張型ブラウザーの構築。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")</span><span class="sxs-lookup"><span data-stu-id="54687-164">![Building extension type browser.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7528e218-8930-4b01-b29d-8ec125a9b818.gif "7528e218-8930-4b01-b29d-8ec125a9b818")</span></span>  
  
7.  <span data-ttu-id="54687-165">をクリックして、**オープン**ボタンをクリックして、アセンブリを選択します。</span><span class="sxs-lookup"><span data-stu-id="54687-165">Click the **Open** button to select the assembly.</span></span>  
  
8.  <span data-ttu-id="54687-166">**バインディング拡張型ブラウザ** ダイアログ ボックスで、バインディング コレクションの要素を実装する型名をクリックします。</span><span class="sxs-lookup"><span data-stu-id="54687-166">In the **Binding Extension Type Browser** dialog box, click the type name that implements the binding collection element.</span></span>  
  
     <span data-ttu-id="54687-167">![拡張型ブラウザーの構築。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")</span><span class="sxs-lookup"><span data-stu-id="54687-167">![Building extension type browser.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce.gif "a5db2c6b-cdf7-4cd9-8cc4-6b0fb960b1ce")</span></span>  
  
9. <span data-ttu-id="54687-168">をクリックして、**オープン**種類を選択するボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="54687-168">Click the **Open** button to select the type.</span></span>  
  
10. <span data-ttu-id="54687-169">をクリックして**OK**を閉じる、 **Extension 構成要素エディタ** ダイアログ ボックス。</span><span class="sxs-lookup"><span data-stu-id="54687-169">Click **OK** to close the **Extension Configuration Element Editor** dialog box.</span></span>  
  
11. <span data-ttu-id="54687-170">詳細ウィンドウで、**バインディング拡張エディター**、バインド拡張機能が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="54687-170">In the details pane of the **Binding Extensions Editor**, verify that your binding extension appears.</span></span> <span data-ttu-id="54687-171">MyAdapterExtension は次の図で強調表示されます。</span><span class="sxs-lookup"><span data-stu-id="54687-171">In the following figure, MyAdapterExtension is highlighted.</span></span>  
  
     <span data-ttu-id="54687-172">![拡張機能が追加されたサービス構成エディター。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span><span class="sxs-lookup"><span data-stu-id="54687-172">![Service configuration editor with added extension.](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/955d37ea-cba5-49db-90de-0f8feb49c0e0.gif "955d37ea-cba5-49db-90de-0f8feb49c0e0")</span></span>  
  
12. <span data-ttu-id="54687-173">閉じる、**サービス構成エディター**します。</span><span class="sxs-lookup"><span data-stu-id="54687-173">Close the **Service Configuration Editor**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54687-174">参照</span><span class="sxs-lookup"><span data-stu-id="54687-174">See Also</span></span>  
 [<span data-ttu-id="54687-175">WCF LOB アダプター SDK を使用して、アダプターを展開します。</span><span class="sxs-lookup"><span data-stu-id="54687-175">Deploy an adapter using the WCF LOB adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)