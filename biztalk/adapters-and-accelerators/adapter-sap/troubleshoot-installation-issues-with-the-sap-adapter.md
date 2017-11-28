---
title: "SAP アダプターでのインストールに関する問題のトラブルシューティング |Microsoft ドキュメント"
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
ms.assetid: fdfdaf44-c32d-43a5-998d-02032c0b9211
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf06cc866249e929c9ddf368f4594af58af1d6fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-installation-issues-with-the-sap-adapter"></a><span data-ttu-id="43bbf-102">SAP アダプターでのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-102">Troubleshoot Installation Issues with the SAP adapter</span></span>
<span data-ttu-id="43bbf-103">Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="43bbf-104">このセクションでは、インストール エラーを解決するのには、トラブルシューティングの手法について説明します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-104">This section discusses troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="43bbf-105">セットアップ操作のログ メッセージ</span><span class="sxs-lookup"><span data-stu-id="43bbf-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="43bbf-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="43bbf-107">さらに、セットアップでは、アダプターのバインドの登録などの特定のカスタム アクションも実行します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="43bbf-108">セットアップを実行する標準的なだけでなくカスタムの操作のメッセージをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="43bbf-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="43bbf-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] MSI を使用してアダプターの特定ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter specific files using an MSI.</span></span> <span data-ttu-id="43bbf-110">したがって、セットアップのログ記録は、標準の MSI ログです。</span><span class="sxs-lookup"><span data-stu-id="43bbf-110">Hence, the logging for the setup is the standard MSI logging.</span></span>  
  
-   <span data-ttu-id="43bbf-111">セットアップ プログラムを実行するカスタム動作のログは %temp%\adaptersetup.log 使用です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-111">Logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="43bbf-112">ログ ファイルにトレースが失敗した場合、トレースもイベント ログにできます。</span><span class="sxs-lookup"><span data-stu-id="43bbf-112">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
##  <span data-ttu-id="43bbf-113"><a name="BKMK_SAPSetupBinding"></a>アダプターのバインドまたはデータ プロバイダーの登録に失敗します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-113"><a name="BKMK_SAPSetupBinding"></a> Setup fails to register adapter bindings or data providers</span></span>  
 <span data-ttu-id="43bbf-114">**問題**</span><span class="sxs-lookup"><span data-stu-id="43bbf-114">**Problem**</span></span>  
  
 <span data-ttu-id="43bbf-115">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドを登録に失敗するか、[!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)]アダプターのインストールが続行されますが、します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-115">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings or the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)], but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="43bbf-116">**原因**</span><span class="sxs-lookup"><span data-stu-id="43bbf-116">**Cause**</span></span>  
  
 <span data-ttu-id="43bbf-117">問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。</span><span class="sxs-lookup"><span data-stu-id="43bbf-117">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="43bbf-118">アダプターのバインドは、machine.config ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="43bbf-118">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="43bbf-119">**解決策**</span><span class="sxs-lookup"><span data-stu-id="43bbf-119">**Resolution**</span></span>  
  
 <span data-ttu-id="43bbf-120">手動で登録する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドまたは[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-120">You should manually register the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding or the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
### <a name="register-the-adapter-bindings-or-the-data-provider"></a><span data-ttu-id="43bbf-121">アダプターのバインドまたはデータ プロバイダーを登録します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-121">Register the adapter bindings or the data provider</span></span>  
  
1.  <span data-ttu-id="43bbf-122">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-122">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="43bbf-123">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ >: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-123">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="43bbf-124">このパスに\<バージョン > は .NET Framework のバージョン。</span><span class="sxs-lookup"><span data-stu-id="43bbf-124">In this path, \<version> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="43bbf-125">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="43bbf-125">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="43bbf-126">登録する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド。</span><span class="sxs-lookup"><span data-stu-id="43bbf-126">To register the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="43bbf-127">要素"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-127">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="43bbf-128">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-128">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="43bbf-129">不足している検索[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-129">Look for the missing [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding.</span></span> <span data-ttu-id="43bbf-130">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-130">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="43bbf-131">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-131">For [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="43bbf-132">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-132">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="43bbf-133">不足している検索[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-133">Look for the missing [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding.</span></span> <span data-ttu-id="43bbf-134">"BindingExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-134">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="43bbf-135">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-135">For [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="43bbf-136">公開キーを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-136">For information about how to determine the public key, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="43bbf-137">登録する、 [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="43bbf-137">To register the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]:</span></span>  
  
    1.  <span data-ttu-id="43bbf-138">"DbProviderFactories"、"system.data"ノードの下の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-138">Search for the element "DbProviderFactories" under the "system.data" node.</span></span>  
  
    2.  <span data-ttu-id="43bbf-139">不足している検索[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-139">Look for the missing [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="43bbf-140">"DbProviderFactories"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-140">Add the following section under the "DbProviderFactories" node.</span></span>  
  
         <span data-ttu-id="43bbf-141">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-141">For [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient" description=".NET Framework Data Provider for mySAP Business Suite" type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="43bbf-142">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="43bbf-142">Save and close the machine.config file.</span></span>  
  
###  <span data-ttu-id="43bbf-143"><a name="BKMK_PubKey"></a>公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-143"><a name="BKMK_PubKey"></a> Determining the Public Key and Version</span></span>  
 <span data-ttu-id="43bbf-144">公開キーを確認するには、次の手順を実行[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]または[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-144">Perform the following steps to determine the public key for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] or [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
1.  <span data-ttu-id="43bbf-145">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-145">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="43bbf-146">対象の公開キーを指定してを選択し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-146">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="43bbf-147">次の表の Dll の名前を一覧表示[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]と[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-147">The following table lists the name of the DLLs for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] and [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span>  
  
    |<span data-ttu-id="43bbf-148">アダプター/データ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="43bbf-148">Adapter/Data Provider</span></span>|<span data-ttu-id="43bbf-149">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="43bbf-149">Name of the DLL</span></span>|  
    |----------------------------|---------------------|  
    |[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]|<span data-ttu-id="43bbf-150">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="43bbf-150">Microsoft.Adapters.SAP</span></span>|  
    |[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="43bbf-151">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="43bbf-151">Microsoft.Data.SAPClient</span></span>|  
  
3.  <span data-ttu-id="43bbf-152">**全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-152">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="43bbf-153">同様に、値のに対して、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-153">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="43bbf-154">公開キーをコピーし、をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-154">Copy the public key, and then click **Cancel**.</span></span>  
  
##  <span data-ttu-id="43bbf-155"><a name="BKMK_SAPConsumeBinding"></a>有効なアダプターにはインストールされているエラーがありません。</span><span class="sxs-lookup"><span data-stu-id="43bbf-155"><a name="BKMK_SAPConsumeBinding"></a> No valid adapters are installed error</span></span>

 <span data-ttu-id="43bbf-156">**問題**</span><span class="sxs-lookup"><span data-stu-id="43bbf-156">**Problem**</span></span>  
  
 <span data-ttu-id="43bbf-157">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-157">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="43bbf-158">**原因**</span><span class="sxs-lookup"><span data-stu-id="43bbf-158">**Cause**</span></span>  
  
 <span data-ttu-id="43bbf-159">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-159">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="43bbf-160">64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-160">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="43bbf-161">そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-161">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="43bbf-162">ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、そのため起動、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグイン、machine.config ファイルの 32 ビット バージョンのバインドをチェックし、エラーが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="43bbf-162">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="43bbf-163">**解決策**</span><span class="sxs-lookup"><span data-stu-id="43bbf-163">**Resolution**</span></span>  
  
-   <span data-ttu-id="43bbf-164">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-164">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="43bbf-165">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-165">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="43bbf-166">32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="43bbf-166">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="43bbf-167">クライアント Dll の 32 ビットおよび 64 ビット バージョンの両方を追加、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (librfc32u.dll) など、PATH 変数にします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-167">Add both the 32-bit and 64-bit versions of the client DLLs for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (such as librfc32u.dll) to the PATH variable.</span></span> <span data-ttu-id="43bbf-168">Dll の 32 ビット バージョンは、C:\Windows\SysWow64 フォルダーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-168">The 32-bit version of the DLLs must be added to C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="43bbf-169">Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-169">The 64-bit version of the DLLs must be added to C:\Windows\System32 folder.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="43bbf-170">(32 ビットまたは 64 ビット) のアダプターが、64 ビット オペレーティング システムをあるコンピューター上で実行されているアプリケーションを作成するアダプターを使用している場合は、アダプターと同じ種類 (32 ビットまたは 64 ビット) にアプリケーションをマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-170">If the adapter (32 or 64-bit) is running on a computer that has a 64-bit operating system, and you are using the adapter to write an application, you should mark the application to the same type (32 or 64-bit) as the adapter.</span></span> <span data-ttu-id="43bbf-171">また、(32 ビットまたは 64 ビット) の RFC SDK のバージョンはアダプター (32 ビットまたは 64 ビット) のバージョンと同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-171">Also, the version of the RFC SDK (32 or 64-bit) must be same as the version of the adapter (32 or 64-bit).</span></span>  
    >   
    >  <span data-ttu-id="43bbf-172">たとえば、32 ビット アダプターが 64 ビット オペレーティング システム搭載のコンピューターで実行されている場合、32 ビットとして、アダプターのクライアント アプリケーションを設定してください。</span><span class="sxs-lookup"><span data-stu-id="43bbf-172">For example, if a 32-bit adapter is running on a computer with a 64-bit operating system, the adapter client application must be marked as 32-bit.</span></span>  
  
     <span data-ttu-id="43bbf-173">SAP クライアント Dll の詳細については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-173">For more information about the SAP client DLLs, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>  
  
##  <span data-ttu-id="43bbf-174"><a name="BKMK_SAPInvalidBinding"></a>SAP アダプターのポートを構成中に無効なバインド エラー</span><span class="sxs-lookup"><span data-stu-id="43bbf-174"><a name="BKMK_SAPInvalidBinding"></a> Invalid binding error while configuring SAP adapter ports</span></span>  
 <span data-ttu-id="43bbf-175">**問題**</span><span class="sxs-lookup"><span data-stu-id="43bbf-175">**Problem**</span></span>  
  
 <span data-ttu-id="43bbf-176">アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-176">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sapBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="43bbf-177">**原因**</span><span class="sxs-lookup"><span data-stu-id="43bbf-177">**Cause**</span></span>  
  
 <span data-ttu-id="43bbf-178">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-178">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="43bbf-179">64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-179">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="43bbf-180">そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-180">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="43bbf-181">ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、32 ビット プロセスとして実行されるされため、アダプターのポートを構成するときに、machine.config ファイルの 32 ビット バージョンのバインドを確認エラーは失敗します。</span><span class="sxs-lookup"><span data-stu-id="43bbf-181">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="43bbf-182">**解決策**</span><span class="sxs-lookup"><span data-stu-id="43bbf-182">**Resolution**</span></span>  
  
-   <span data-ttu-id="43bbf-183">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-183">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="43bbf-184">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-184">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="43bbf-185">32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="43bbf-185">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="43bbf-186">クライアント Dll の 32 ビットおよび 64 ビット バージョンの両方を追加、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (librfc32u.dll) など、PATH 変数にします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-186">Add both the 32-bit and 64-bit versions of the client DLLs for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] (such as librfc32u.dll) to the PATH variable.</span></span> <span data-ttu-id="43bbf-187">Dll の 32 ビット バージョンは、C:\Windows\SysWow64 フォルダーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-187">The 32-bit version of the DLLs must be added to C:\Windows\SysWow64 folder.</span></span> <span data-ttu-id="43bbf-188">Dll の 64 ビット バージョンは、C:\Windows\System32 フォルダーに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-188">The 64-bit version of the DLLs must be added to C:\Windows\System32 folder.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="43bbf-189">(32 ビットまたは 64 ビット) のアダプターが、64 ビット オペレーティング システムをあるコンピューター上で実行されているアプリケーションを作成するアダプターを使用している場合は、アダプターと同じ種類 (32 ビットまたは 64 ビット) にアプリケーションをマークする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-189">If the adapter (32 or 64-bit) is running on a computer that has a 64-bit operating system, and you are using the adapter to write an application, you should mark the application to the same type (32 or 64-bit) as the adapter.</span></span> <span data-ttu-id="43bbf-190">また、(32 ビットまたは 64 ビット) の RFC SDK のバージョンはアダプター (32 ビットまたは 64 ビット) のバージョンと同じにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="43bbf-190">Also, the version of the RFC SDK (32 or 64-bit) must be same as the version of the adapter (32 or 64-bit).</span></span>  
    >   
    >  <span data-ttu-id="43bbf-191">たとえば、32 ビット アダプターが 64 ビット オペレーティング システム搭載のコンピューターで実行されている場合、32 ビットとして、アダプターのクライアント アプリケーションを設定してください。</span><span class="sxs-lookup"><span data-stu-id="43bbf-191">For example, if a 32-bit adapter is running on a computer with a 64-bit operating system, the adapter client application must be marked as 32-bit.</span></span>  
  
     <span data-ttu-id="43bbf-192">SAP クライアント Dll の詳細については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="43bbf-192">For more information about the SAP client DLLs, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="43bbf-193">参照</span><span class="sxs-lookup"><span data-stu-id="43bbf-193">See Also</span></span>  
[<span data-ttu-id="43bbf-194">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="43bbf-194">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)