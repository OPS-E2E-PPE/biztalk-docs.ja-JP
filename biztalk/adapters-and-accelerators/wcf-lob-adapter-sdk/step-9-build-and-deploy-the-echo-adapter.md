---
title: 手順 9:ビルドおよびエコー アダプターの展開 |Microsoft Docs
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
ms.openlocfilehash: 57cd647ebe8d8896a85c5a6a49cce95321da0bdb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363110"
---
# <a name="step-9-build-and-deploy-the-echo-adapter"></a><span data-ttu-id="4d311-102">手順 9:ビルドおよびエコー アダプターの展開</span><span class="sxs-lookup"><span data-stu-id="4d311-102">Step 9: Build and Deploy the Echo Adapter</span></span>
<span data-ttu-id="4d311-103">![手順 9 の 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span><span class="sxs-lookup"><span data-stu-id="4d311-103">![Step 9 of 9](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-9of9.gif "Step_9of9")</span></span>  
  
 <span data-ttu-id="4d311-104">**所要時間:** 10 分</span><span class="sxs-lookup"><span data-stu-id="4d311-104">**Time to complete:** 10 minutes</span></span>  
  
 <span data-ttu-id="4d311-105">この手順では、エコー アダプターの展開に必要なタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="4d311-105">In this step, you will perform the tasks necessary to deploy the Echo Adapter.</span></span> <span data-ttu-id="4d311-106">これは、次のすべてが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4d311-106">This involves all of the following:</span></span>  
  
- <span data-ttu-id="4d311-107">厳密な名前のファイルを作成し、エコー アダプターのアセンブリに割り当てる</span><span class="sxs-lookup"><span data-stu-id="4d311-107">Create a strong name file and assign it to the Echo Adapter assembly</span></span>  
  
- <span data-ttu-id="4d311-108">エコー アダプターをビルドします。</span><span class="sxs-lookup"><span data-stu-id="4d311-108">Build the Echo Adapter</span></span>  
  
- <span data-ttu-id="4d311-109">GAC にアセンブリを公開します。</span><span class="sxs-lookup"><span data-stu-id="4d311-109">Publish the assembly into the GAC</span></span>  
  
- <span data-ttu-id="4d311-110">エコー アダプターを登録します [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d311-110">Register the Echo Adapter with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4d311-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="4d311-111">Prerequisites</span></span>  
 <span data-ttu-id="4d311-112">この手順を正常に完了するには、厳密な名前のファイルと、GAC をよく理解します。</span><span class="sxs-lookup"><span data-stu-id="4d311-112">To successfully complete this step, you should be familiar with strong name files and the GAC.</span></span> <span data-ttu-id="4d311-113">基本的な理解[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]構成は役立ちますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="4d311-113">A basic understanding of [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] configuration is helpful but not required.</span></span>  
  
### <a name="to-assign-a-strong-name-to-your-assembly"></a><span data-ttu-id="4d311-114">アセンブリに厳密な名前を割り当てる</span><span class="sxs-lookup"><span data-stu-id="4d311-114">To assign a strong name to your assembly</span></span>  
  
1.  <span data-ttu-id="4d311-115">ソリューション エクスプ ローラーで右クリックし、 **EchoAdapter**プロジェクトをクリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="4d311-115">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="4d311-116">EchoAdapter プロパティ ページ] ダイアログ ボックスで、[**署名**左側のウィンドウ。</span><span class="sxs-lookup"><span data-stu-id="4d311-116">In the EchoAdapter Property Pages dialog box, select **Signing** from the left pane.</span></span>  
  
3.  <span data-ttu-id="4d311-117">をクリックして、**アセンブリに署名**タブ。</span><span class="sxs-lookup"><span data-stu-id="4d311-117">Click the **Sign the assembly** tab.</span></span>  
  
4.  <span data-ttu-id="4d311-118">選択 **\<新しい.\>** 厳密な名前のファイル。</span><span class="sxs-lookup"><span data-stu-id="4d311-118">Choose **\<new…\>** for the strong name file.</span></span> <span data-ttu-id="4d311-119">ファイル名を求められたら、入力**EchoAdapter.snk**保護ではパスワードのオプションでは、キー ファイルの選択を解除し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="4d311-119">When prompted for a file name, type **EchoAdapter.snk**,deselect the protect my key file with a password option, then click **OK**.</span></span>  
  
5.  <span data-ttu-id="4d311-120">をクリックして、**アプリケーション**タブ。</span><span class="sxs-lookup"><span data-stu-id="4d311-120">Click the **Application** tab.</span></span>  
  
6.  <span data-ttu-id="4d311-121">アセンブリ名を変更して**Microsoft.Adapters.Samples.EchoV2**します。</span><span class="sxs-lookup"><span data-stu-id="4d311-121">Change the assembly name to **Microsoft.Adapters.Samples.EchoV2**.</span></span>  
  
7.  <span data-ttu-id="4d311-122">クリックして**ファイル**、Visual Studio のメニューをクリックし**すべて保存**します。</span><span class="sxs-lookup"><span data-stu-id="4d311-122">Click **File** on the Visual Studio menu then choose **Save All**.</span></span>  
  
### <a name="to-build-and-deploy-echo-adapter"></a><span data-ttu-id="4d311-123">ビルドしてエコー アダプターをデプロイするには</span><span class="sxs-lookup"><span data-stu-id="4d311-123">To build and deploy Echo Adapter</span></span>  
  
1.  <span data-ttu-id="4d311-124">ソリューション エクスプ ローラーで右クリックし、 **EchoAdapter**プロジェクトをクリックして**ビルド**します。</span><span class="sxs-lookup"><span data-stu-id="4d311-124">In Solution Explorer, right-click the **EchoAdapter** project, and then click **Build**.</span></span> <span data-ttu-id="4d311-125">ビルドが成功しなかった場合は、エラーを修正してエコー アダプターをリビルドしてください。</span><span class="sxs-lookup"><span data-stu-id="4d311-125">If the build does not succeed, fix any errors and try rebuilding the Echo Adapter.</span></span>  
  
2.  <span data-ttu-id="4d311-126">Visual Studio コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="4d311-126">Open a Visual Studio command prompt.</span></span>  
  
3.  <span data-ttu-id="4d311-127">次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="4d311-127">Type the following command:</span></span>  
  
     <span data-ttu-id="4d311-128">**gacutil.exe /if "\<** *path to assembly\Microsoft.Adapters.Samples.EchoV2.dll* **\>"**</span><span class="sxs-lookup"><span data-stu-id="4d311-128">**gacutil.exe /if "\<** *path to assembly\Microsoft.Adapters.Samples.EchoV2.dll* **\>"**</span></span>  
  
     <span data-ttu-id="4d311-129">これにより、アセンブリが GAC にインストールされて、同じアセンブリ名を持つ既存のアセンブリは上書きされます。</span><span class="sxs-lookup"><span data-stu-id="4d311-129">This installs the assembly to the GAC, overwriting any existing assembly that has the same assembly name.</span></span>  
  
### <a name="to-register-the-echo-adapter-with-windows-communication-foundation"></a><span data-ttu-id="4d311-130">Windows Communication Foundation でエコー アダプターを登録するには</span><span class="sxs-lookup"><span data-stu-id="4d311-130">To register the Echo Adapter with Windows Communication Foundation</span></span>  
  
1. <span data-ttu-id="4d311-131">Microsoft .NET の構成フォルダーにある machine.config ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="4d311-131">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="4d311-132">これを行うには、次のようにクリックします**開始**、 をクリック**実行**、型**メモ帳\<Windows インストール パス\>\Microsoft.NET\Framework\\< バージョン\>。\CONFIG\machine.config**、 をクリックし、 **OK**します。</span><span class="sxs-lookup"><span data-stu-id="4d311-132">To do this, click **Start**, click **Run**, type **notepad \<Windows install path\>\Microsoft.NET\Framework\\<version\>\CONFIG\machine.config**, and then click **OK**.</span></span>  
  
2. <span data-ttu-id="4d311-133">Machine.config ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="4d311-133">Update the machine.config file.</span></span> <span data-ttu-id="4d311-134">Machine.config に system.serviceModel セクションが含まれていない場合は、終了タグをルートする前に、構成ファイルの末尾に次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="4d311-134">If your machine.config does not contain a system.serviceModel section, add the following section at the end of the configuration file but before the closing root tag.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4d311-135">バージョン、カルチャ、公開キー トークン、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4d311-135">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
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
  
   - <span data-ttu-id="4d311-136">または -</span><span class="sxs-lookup"><span data-stu-id="4d311-136">OR -</span></span>  
  
     <span data-ttu-id="4d311-137">Machine.config に system.serviceModel セクションが含まれている場合は、要素が見つからないと追加を決定します。</span><span class="sxs-lookup"><span data-stu-id="4d311-137">If your machine.config contains a system.serviceModel section, determine which elements are missing and add them.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4d311-138">バージョン、カルチャ、公開キー トークン、およびその他のアセンブリに固有の情報をアダプターの情報に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4d311-138">Replace the version, culture, public key token and other assembly-specific information with your adapter's information.</span></span>  
  
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
  
3. <span data-ttu-id="4d311-139">Machine.config ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="4d311-139">Save the machine.config file.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="4d311-140">でしただけ何か。</span><span class="sxs-lookup"><span data-stu-id="4d311-140">What Did I Just Do?</span></span>  
 <span data-ttu-id="4d311-141">エコー アダプターのチュートリアルの最後の手順でしてエコー アダプターに厳密な名前を追加、構築された、アダプターを展開し、アダプター情報を含めるように Machine.config の変更します。</span><span class="sxs-lookup"><span data-stu-id="4d311-141">In this final step of the Echo Adapter tutorial, you added a strong name to the Echo Adapter, built and deployed the adapter, then modified Machine.config to include information about the adapter.</span></span> <span data-ttu-id="4d311-142">この時点では、エコー アダプターは、アプリケーションを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4d311-142">At this point, the Echo Adapter should be available to consuming applications.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4d311-143">次の手順</span><span class="sxs-lookup"><span data-stu-id="4d311-143">Next Steps</span></span>  
 <span data-ttu-id="4d311-144">このチュートリアルが完了しました。</span><span class="sxs-lookup"><span data-stu-id="4d311-144">This tutorial is complete.</span></span> <span data-ttu-id="4d311-145">.NET プロジェクトでエコー アダプターの機能をテストする場合は、「[チュートリアル 2.NET からエコー アダプターを使用](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)します。</span><span class="sxs-lookup"><span data-stu-id="4d311-145">If you want to test Echo Adapter functionality in a .NET project, see [Tutorial 2: Consume the Echo Adapter from .NET](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d311-146">参照</span><span class="sxs-lookup"><span data-stu-id="4d311-146">See Also</span></span>  
 <span data-ttu-id="4d311-147">[手順 8:エコー アダプターの同期受信ハンドラーを実装します。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4d311-147">[Step 8: Implement the Synchronous Inbound Handler for the Echo Adapter](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-8-implement-the-synchronous-inbound-handler-for-the-echo-adapter.md) </span></span>  
 [<span data-ttu-id="4d311-148">チュートリアル 2: .NET からエコー アダプターを使用する</span><span class="sxs-lookup"><span data-stu-id="4d311-148">Tutorial 2: Consume the Echo Adapter from .NET</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-2-consume-the-echo-adapter-from-net.md)