---
title: '手順 9: ビルド アダプターおよび展開エコー |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1ead10ab-1acf-47c5-ad16-dc6938601906
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b9a4985629427e44b8ca85f324c89ab719cf249
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967240"
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a><span data-ttu-id="48e84-102">手順 9: ビルドをエコー アダプターの展開</span><span class="sxs-lookup"><span data-stu-id="48e84-102">Step 9: Build and Deploy the Echo Adapter</span></span>
<span data-ttu-id="48e84-103">![手順 9 の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="48e84-103">![Step 9 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="48e84-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="48e84-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="48e84-105">このステップでは、エコー アダプターの展開に必要なタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="48e84-105">In this step, you will perform the tasks necessary to deploy the Echo Adapter.</span></span> <span data-ttu-id="48e84-106">次のすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="48e84-106">This involves all of the following:</span></span>  
  
-   <span data-ttu-id="48e84-107">厳密な名前のファイルを作成し、エコー アダプターのアセンブリに割り当てます</span><span class="sxs-lookup"><span data-stu-id="48e84-107">Create a strong name file and assign it to the Echo Adapter assembly</span></span>  
  
-   <span data-ttu-id="48e84-108">エコー アダプターをビルドします。</span><span class="sxs-lookup"><span data-stu-id="48e84-108">Build the Echo Adapter</span></span>  
  
-   <span data-ttu-id="48e84-109">GAC にアセンブリを公開します。</span><span class="sxs-lookup"><span data-stu-id="48e84-109">Publish the assembly into the GAC</span></span>  
  
-   <span data-ttu-id="48e84-110">エコー アダプターを登録します[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48e84-110">Register the Echo Adapter with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="48e84-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="48e84-111">Prerequisites</span></span>  
 <span data-ttu-id="48e84-112">この手順を正常に完了するには、厳密な名前のファイルと、GAC に精通しての操作をおく必要があります。</span><span class="sxs-lookup"><span data-stu-id="48e84-112">To successfully complete this step, you should be familiar with strong name files and the GAC.</span></span> <span data-ttu-id="48e84-113">基本的な知識[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]構成は役立ちますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="48e84-113">A basic understanding of [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] configuration is helpful but not required.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="48e84-114">アセンブリに厳密な名前を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="48e84-114">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="48e84-115">ソリューション エクスプ ローラーで右クリックし、 **EchoAdapter**プロジェクトをクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="48e84-115">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="48e84-116">EchoAdapter プロパティ ページ ダイアログ ボックスで、次のように選択します。**署名**左側のペインからです。</span><span class="sxs-lookup"><span data-stu-id="48e84-116">In the EchoAdapter Property Pages dialog box, select **Signing** from the left pane.</span></span>  
  
3.  <span data-ttu-id="48e84-117">クリックして、**アセンブリに署名**タブです。</span><span class="sxs-lookup"><span data-stu-id="48e84-117">Click the **Sign the assembly** tab.</span></span>  
  
4.  <span data-ttu-id="48e84-118">選択**\<新規作成しています.\>** 厳密な名前のファイルです。</span><span class="sxs-lookup"><span data-stu-id="48e84-118">Choose **\<new…\>** for the strong name file.</span></span> <span data-ttu-id="48e84-119">ファイル名の入力を求め、入力**EchoAdapter.snk**保護するオプションでは、パスワード、キー ファイルの選択を解除し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="48e84-119">When prompted for a file name, type **EchoAdapter.snk**,deselect the protect my key file with a password option, then click **OK**.</span></span>  
  
5.  <span data-ttu-id="48e84-120">クリックして、**アプリケーション**タブです。</span><span class="sxs-lookup"><span data-stu-id="48e84-120">Click the **Application** tab.</span></span>  
  
6.  <span data-ttu-id="48e84-121">アセンブリ名に変更**Microsoft.Adapters.Samples.EchoV2**です。</span><span class="sxs-lookup"><span data-stu-id="48e84-121">Change the assembly name to **Microsoft.Adapters.Samples.EchoV2**.</span></span>  
  
7.  <span data-ttu-id="48e84-122">をクリックして**ファイル**、Visual Studio のメニューをクリックし**すべて保存**です。</span><span class="sxs-lookup"><span data-stu-id="48e84-122">Click **File** on the Visual Studio menu then choose **Save All**.</span></span>  
  
### <a name="to-build-and-deploy-echo-adapter"></a><span data-ttu-id="48e84-123">構築およびデプロイ エコー アダプター</span><span class="sxs-lookup"><span data-stu-id="48e84-123">To build and deploy Echo Adapter</span></span>  
  
1.  <span data-ttu-id="48e84-124">ソリューション エクスプ ローラーで右クリックし、 **EchoAdapter**プロジェクトをクリックして**ビルド**です。</span><span class="sxs-lookup"><span data-stu-id="48e84-124">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Build**.</span></span> <span data-ttu-id="48e84-125">ビルドが成功しなかった場合は、エラーを修正して、エコー アダプターを再構築してください。</span><span class="sxs-lookup"><span data-stu-id="48e84-125">If the build does not succeed, fix any errors and try rebuilding the Echo Adapter.</span></span>  
  
2.  <span data-ttu-id="48e84-126">Visual Studio コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="48e84-126">Open a Visual Studio command prompt.</span></span>  
  
3.  <span data-ttu-id="48e84-127">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="48e84-127">Type the following command:</span></span>  
  
     <span data-ttu-id="48e84-128">**gacutil.exe/if"\<**  *assembly\Microsoft.Adapters.Samples.EchoV2.dll へのパス*  **\>"**</span><span class="sxs-lookup"><span data-stu-id="48e84-128">**gacutil.exe /if "\<** *path to assembly\Microsoft.Adapters.Samples.EchoV2.dll* **\>"**</span></span>  
  
     <span data-ttu-id="48e84-129">これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="48e84-129">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a><span data-ttu-id="48e84-130">Windows Communication Foundation にエコー アダプターを登録するには</span><span class="sxs-lookup"><span data-stu-id="48e84-130">To register the Echo Adapter with Windows Communication Foundation</span></span>  
  
1.  <span data-ttu-id="48e84-131">Microsoft .NET 構成フォルダ内にある machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="48e84-131">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="48e84-132">これを行うには、をクリックして**開始**をクリックして**実行**、型**メモ帳\<Windows のインストール パス\>\Microsoft.NET\Framework\\< バージョン\>\CONFIG\machine.config**、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="48e84-132">To do this, click **Start**, click **Run**, type **notepad \<Windows install path\>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config**, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="48e84-133">Machine.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="48e84-133">Update the machine.config file.</span></span> <span data-ttu-id="48e84-134">Machine.config に system.serviceModel セクションが含まれていない場合は、ルート タグの終わりの前に、構成ファイルの末尾に次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="48e84-134">If your machine.config does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48e84-135">バージョン、カルチャ、公開キー トークン、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="48e84-135">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
    ```  
    <system.serviceModel>  
      <client>  
        <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
          name="echov2" />  
      </client>  
      <extensions>  
        <bindingElementExtensions>  
          <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
        </bindingElementExtensions>  
        <bindingExtensions>  
          <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
        </bindingExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
     - <span data-ttu-id="48e84-136">または -</span><span class="sxs-lookup"><span data-stu-id="48e84-136">OR -</span></span>  
  
     <span data-ttu-id="48e84-137">Machine.config system.serviceModel セクションが含まれている場合は、のどの要素が見つからないと追加を決定します。</span><span class="sxs-lookup"><span data-stu-id="48e84-137">If your machine.config contains a system.serviceModel section, determine which elements are missing and add them.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="48e84-138">バージョン、カルチャ、公開キー トークン、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="48e84-138">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
    ```  
    <client>  
      <endpoint binding="echoAdapterBindingV2" contract="IMetadataExchange"  
        name="echov2" />  
    </client>  
    <extensions>  
      <bindingElementExtensions>  
        <add name="echoAdapterV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingElementExtensionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
      </bindingElementExtensions>  
      <bindingExtensions>  
        <add name="echoAdapterBindingV2" type="Microsoft.Adapters.Samples.EchoV2.EchoAdapterBindingCollectionElement,Microsoft.Adapters.Samples.EchoV2, Version=1.0.0.0, Culture=neutral, PublicKeyToken=xxxxxxxxxxxxxxxx" />  
      </bindingExtensions>  
    </extensions>  
    ```  
  
3.  <span data-ttu-id="48e84-139">Machine.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="48e84-139">Save the machine.config file.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="48e84-140">でしただけは何ですか。</span><span class="sxs-lookup"><span data-stu-id="48e84-140">What Did I Just Do?</span></span>  
 <span data-ttu-id="48e84-141">エコー アダプター チュートリアルの最後の手順で、エコー アダプターに厳密な名前を追加、構築して、アダプターを展開し、するアダプターに関する情報が含まれる Machine.config を変更します。</span><span class="sxs-lookup"><span data-stu-id="48e84-141">In this final step of the Echo Adapter tutorial, you added a strong name to the Echo Adapter, built and deployed the adapter, then modified Machine.config to include information about the adapter.</span></span> <span data-ttu-id="48e84-142">この時点では、エコー アダプターはアプリケーションの処理に使用できるはずです。</span><span class="sxs-lookup"><span data-stu-id="48e84-142">At this point, the Echo Adapter should be available to consuming applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="48e84-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="48e84-143">Next Steps</span></span>  
 <span data-ttu-id="48e84-144">このチュートリアルが完了しました。</span><span class="sxs-lookup"><span data-stu-id="48e84-144">This tutorial is complete.</span></span> <span data-ttu-id="48e84-145">.NET プロジェクトでエコー アダプターの機能をテストする場合は、「[チュートリアル 2: .NET からエコー アダプターを使用する](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)です。</span><span class="sxs-lookup"><span data-stu-id="48e84-145">If you want to test Echo Adapter functionality in a .NET project, see [Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e84-146">参照</span><span class="sxs-lookup"><span data-stu-id="48e84-146">See Also</span></span>  
 <span data-ttu-id="48e84-147">[手順 8: エコー アダプターの同期受信ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="48e84-147">[Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="48e84-148">チュートリアル 2: .NET からエコー アダプターを使用する</span><span class="sxs-lookup"><span data-stu-id="48e84-148">Tutorial 2: Consume the Echo Adapter from .NET</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)