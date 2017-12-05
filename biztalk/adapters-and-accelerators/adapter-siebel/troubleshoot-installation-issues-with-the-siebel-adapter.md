---
title: "Siebel アダプターのインストールに関する問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting, installation
- installation, troubleshooting
ms.assetid: f9f066d9-37b6-4a18-9f60-d0931ea91a18
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff49285df7e43103f2ad7441cbc82b96bb59eaa4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshoot-installation-issues-with-the-siebel-adapter"></a><span data-ttu-id="89e98-102">Siebel アダプターのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="89e98-102">Troubleshoot Installation Issues with the Siebel adapter</span></span>
<span data-ttu-id="89e98-103">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]インストールは、コンピューター上の製品バイナリをコピーし、各アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="89e98-103">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="89e98-104">このセクションでは、インストール エラーを解決するのには、トラブルシューティングの手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="89e98-104">This section discusses troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="setup-logging"></a><span data-ttu-id="89e98-105">セットアップのログ</span><span class="sxs-lookup"><span data-stu-id="89e98-105">Setup Logging</span></span>  
 <span data-ttu-id="89e98-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="89e98-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="89e98-107">さらに、セットアップでは、アダプターのバインドの登録などの特定のカスタム アクションも実行します。</span><span class="sxs-lookup"><span data-stu-id="89e98-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="89e98-108">セットアップで行われた標準とカスタム操作の両方のメッセージをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="89e98-108">You can log messages for both the standard as well as custom actions performed by the setup.</span></span>  
  
-   <span data-ttu-id="89e98-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] MSI を使用してアダプターの特定ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="89e98-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter specific files using an MSI.</span></span> <span data-ttu-id="89e98-110">そのため、セットアップのログ記録は、標準の MSI ログになります。</span><span class="sxs-lookup"><span data-stu-id="89e98-110">Hence, the logging for the setup will be the standard MSI logging.</span></span>  
  
-   <span data-ttu-id="89e98-111">セットアップ プログラムによって実行されるカスタム動作のログは %temp%\adaptersetup.log 使用です。</span><span class="sxs-lookup"><span data-stu-id="89e98-111">Logs for the custom actions performed by the setup program are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="89e98-112">ログ ファイルにトレースが失敗した場合、トレースもイベント ログにできます。</span><span class="sxs-lookup"><span data-stu-id="89e98-112">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="89e98-113">既知の問題</span><span class="sxs-lookup"><span data-stu-id="89e98-113">Known Issues</span></span>  
  
### <a name="setup-fails-to-register-adapter-bindings"></a><span data-ttu-id="89e98-114">アダプターのバインドの登録に失敗します。</span><span class="sxs-lookup"><span data-stu-id="89e98-114">Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="89e98-115">**問題**</span><span class="sxs-lookup"><span data-stu-id="89e98-115">**Problem**</span></span>  
  
 <span data-ttu-id="89e98-116">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、登録に失敗する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドまたは[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]アダプターのインストールが続行されますが、します。</span><span class="sxs-lookup"><span data-stu-id="89e98-116">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding or the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="89e98-117">**原因**</span><span class="sxs-lookup"><span data-stu-id="89e98-117">**Cause**</span></span>  
  
 <span data-ttu-id="89e98-118">WCF のインストールに問題があります[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config です。</span><span class="sxs-lookup"><span data-stu-id="89e98-118">This might result due to problems with WCF installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config being corrupt.</span></span> <span data-ttu-id="89e98-119">アダプターのバインドは、machine.config ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="89e98-119">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="89e98-120">**解決策**</span><span class="sxs-lookup"><span data-stu-id="89e98-120">**Resolution**</span></span>  
  
<span data-ttu-id="89e98-121">手動で登録、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドと[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="89e98-121">Manually register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding and [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] using the following steps:</span></span> 
  
1.  <span data-ttu-id="89e98-122">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="89e98-122">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="89e98-123">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="89e98-123">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="89e98-124">このパスに\<バージョン\>.NET Framework のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="89e98-124">In this path, \<version\> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="89e98-125">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="89e98-125">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="89e98-126">登録する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインド。</span><span class="sxs-lookup"><span data-stu-id="89e98-126">To register the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="89e98-127">要素"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="89e98-127">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="89e98-128">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="89e98-128">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="89e98-129">不足している検索[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="89e98-129">Look for the missing [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding.</span></span> <span data-ttu-id="89e98-130">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="89e98-130">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="89e98-131">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="89e98-131">For [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="89e98-132">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="89e98-132">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="89e98-133">不足している検索[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="89e98-133">Look for the missing [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding.</span></span> <span data-ttu-id="89e98-134">"BindingExtensions"ノードの下に、次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="89e98-134">Add the following sections under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="89e98-135">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="89e98-135">For [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="89e98-136">公開キーを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。</span><span class="sxs-lookup"><span data-stu-id="89e98-136">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="89e98-137">登録する、 [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="89e98-137">To register the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="89e98-138">DbProviderFactories system.data ノードの下の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="89e98-138">Search for the element DbProviderFactories under the system.data node.</span></span>  
  
    2.  <span data-ttu-id="89e98-139">不足している検索[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="89e98-139">Look for the missing [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span> <span data-ttu-id="89e98-140">DbProviderFactories ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="89e98-140">Add the following section under the DbProviderFactories node.</span></span>  
  
         <span data-ttu-id="89e98-141">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="89e98-141">For [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="89e98-142">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="89e98-142">Save and close the machine.config file.</span></span>  
  
####  <a name="BKMK_PubKey"></a><span data-ttu-id="89e98-143">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="89e98-143">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="89e98-144">公開キーを確認するには、次の手順を実行[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]または[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="89e98-144">Perform the following steps to determine the public key for [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] or [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)].</span></span>  
  
###### <a name="to-determine-the-public-key"></a><span data-ttu-id="89e98-145">公開キーを確認するには</span><span class="sxs-lookup"><span data-stu-id="89e98-145">To determine the public key</span></span>  
  
1.  <span data-ttu-id="89e98-146">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="89e98-146">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="89e98-147">対象となる公開キーを押し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="89e98-147">Right-click the DLL for which you want the public key and select **Properties**.</span></span> <span data-ttu-id="89e98-148">次の表は、各アダプターおよびプロバイダーの Dll の名前を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="89e98-148">The following table lists the name of the DLLs for each adapter and provider.</span></span>  
  
    |<span data-ttu-id="89e98-149">アダプター/ADO プロバイダー</span><span class="sxs-lookup"><span data-stu-id="89e98-149">Adapter/ADO Provider</span></span>|<span data-ttu-id="89e98-150">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="89e98-150">Name of the DLL</span></span>|  
    |---------------------------|---------------------|  
    |[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="89e98-151">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="89e98-151">Microsoft.Adapters.Siebel</span></span>|  
    |[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="89e98-152">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="89e98-152">Microsoft.Data.SiebelClient</span></span>|  
  
3.  <span data-ttu-id="89e98-153">**全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="89e98-153">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="89e98-154">同様に、値のに対して、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="89e98-154">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="89e98-155">公開キーをコピーし、をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="89e98-155">Copy the public key, and then click **Cancel**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89e98-156">参照</span><span class="sxs-lookup"><span data-stu-id="89e98-156">See Also</span></span>  
[<span data-ttu-id="89e98-157">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="89e98-157">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)