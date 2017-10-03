---
title: "SQl アダプタでのインストールに関する問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48778158-6064-4731-be72-1af855ebe373
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07a160c428ac9df0f75b219af5bafb0727205cbd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshoot-installation-issues-with-the-sql-adapter"></a><span data-ttu-id="96b8e-102">SQl アダプタでのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-102">Troubleshoot Installation Issues with the SQl adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="96b8e-103">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]として使用できますがの一部、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]別個のアダプターとします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-103">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is available as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] as well as a separate adapter.</span></span> <span data-ttu-id="96b8e-104">インストールに関する問題は次のトピックに、このトピックにアクセスするかどうか、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]とは別の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、すべての参照を[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]としてセットアップを解釈する必要があります[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]セットアップします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-104">If you are accessing this topic to know about installation issues with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] that is separate from the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], all references to the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Setup must be interpreted as [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] Setup.</span></span>  
  
 <span data-ttu-id="96b8e-105">Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-105">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="96b8e-106">このセクションでは、インストール エラーを解決するのには、トラブルシューティングの手法を使用してについて説明します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-106">This section discusses using troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="96b8e-107">セットアップ操作のログ メッセージ</span><span class="sxs-lookup"><span data-stu-id="96b8e-107">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="96b8e-108">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="96b8e-108">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="96b8e-109">さらに、セットアップでは、アダプターのバインドの登録などの特定のカスタム アクションも実行します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-109">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="96b8e-110">セットアップを実行する標準的なだけでなくカスタムの操作のメッセージをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="96b8e-110">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="96b8e-111">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] MSI を使用してアダプターに固有のファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-111">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="96b8e-112">したがって、セットアップのログ記録は、標準の MSI ログです。</span><span class="sxs-lookup"><span data-stu-id="96b8e-112">Therefore, the logging for the setup is the standard MSI logging.</span></span>  
  
-   <span data-ttu-id="96b8e-113">セットアップ プログラムを実行するカスタム アクションのすべてのログは %temp%\adaptersetup.log です。</span><span class="sxs-lookup"><span data-stu-id="96b8e-113">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="96b8e-114">ログ ファイルにトレースが失敗した場合、トレースもイベント ログにできます。</span><span class="sxs-lookup"><span data-stu-id="96b8e-114">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="96b8e-115">既知の問題</span><span class="sxs-lookup"><span data-stu-id="96b8e-115">Known Issues</span></span>  
 <span data-ttu-id="96b8e-116">インストールするときに発生する可能性が最も一般的なエラーは、次のとおり、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、およびその考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-116">The following are the most common errors you might encounter when installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <span data-ttu-id="96b8e-117"><a name="BKMK_SQLSetupBinding"></a>アダプターのバインドの登録に失敗します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-117"><a name="BKMK_SQLSetupBinding"></a> Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="96b8e-118">**問題**</span><span class="sxs-lookup"><span data-stu-id="96b8e-118">**Problem**</span></span>  
  
 <span data-ttu-id="96b8e-119">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドの登録に失敗するが、アダプターのインストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="96b8e-119">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] Setup Wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="96b8e-120">**原因**</span><span class="sxs-lookup"><span data-stu-id="96b8e-120">**Cause**</span></span>  
  
 <span data-ttu-id="96b8e-121">問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。</span><span class="sxs-lookup"><span data-stu-id="96b8e-121">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="96b8e-122">アダプターのバインドは、machine.config ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="96b8e-122">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="96b8e-123">**解決策**</span><span class="sxs-lookup"><span data-stu-id="96b8e-123">**Resolution**</span></span>  
  
 <span data-ttu-id="96b8e-124">手動で登録する必要があります、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-124">You should manually register the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span>  
  
##### <a name="to-register-the-adapter-binding"></a><span data-ttu-id="96b8e-125">アダプターのバインドを登録するには</span><span class="sxs-lookup"><span data-stu-id="96b8e-125">To register the adapter binding</span></span>  
  
1.  <span data-ttu-id="96b8e-126">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-126">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="96b8e-127">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ >: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="96b8e-127">For example, on a 32-bit platform, the machine.config is available under \<system drive>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="96b8e-128">このパスに\<バージョン > は .NET Framework のバージョン。</span><span class="sxs-lookup"><span data-stu-id="96b8e-128">In this path, \<version> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="96b8e-129">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="96b8e-129">Open the file by using a text editor.</span></span>  
  
3.  <span data-ttu-id="96b8e-130">登録する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインド。</span><span class="sxs-lookup"><span data-stu-id="96b8e-130">To register the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="96b8e-131">要素"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-131">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="96b8e-132">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-132">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="96b8e-133">不足している検索[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-133">Look for the missing [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span> <span data-ttu-id="96b8e-134">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-134">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="96b8e-135">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-135">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="96b8e-136">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-136">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="96b8e-137">不足している検索[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-137">Look for the missing [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] binding.</span></span> <span data-ttu-id="96b8e-138">"BindingExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-138">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="96b8e-139">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-139">For [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="96b8e-140">公開キーとバージョンを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。</span><span class="sxs-lookup"><span data-stu-id="96b8e-140">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="96b8e-141">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="96b8e-141">Save and close the machine.config file.</span></span>  
  
####  <span data-ttu-id="96b8e-142"><a name="BKMK_PubKey"></a>公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-142"><a name="BKMK_PubKey"></a> Determining the Public Key and Version</span></span>  
 <span data-ttu-id="96b8e-143">公開キーを確認するには、次の手順を実行[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="96b8e-143">Perform the following steps to determine the public key for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
###### <a name="to-determine-the-public-key"></a><span data-ttu-id="96b8e-144">公開キーを確認するには</span><span class="sxs-lookup"><span data-stu-id="96b8e-144">To determine the public key</span></span>  
  
1.  <span data-ttu-id="96b8e-145">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-145">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="96b8e-146">公開キーと、バージョンを対象し、なるを選択し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="96b8e-146">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="96b8e-147">次の表に、dll の名前[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="96b8e-147">The following table lists the name of the DLL for [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
    |<span data-ttu-id="96b8e-148">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="96b8e-148">Adapter</span></span>|<span data-ttu-id="96b8e-149">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="96b8e-149">Name of the DLL</span></span>|  
    |-------------|---------------------|  
    |[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]|<span data-ttu-id="96b8e-150">Microsoft.Adapters.Sql</span><span class="sxs-lookup"><span data-stu-id="96b8e-150">Microsoft.Adapters.Sql</span></span>|  
  
3.  <span data-ttu-id="96b8e-151">**全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-151">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="96b8e-152">同様に、値のに対して、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-152">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="96b8e-153">公開キーをコピーし、をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="96b8e-153">Copy the public key, and then click **Cancel**.</span></span>  
  
###  <span data-ttu-id="96b8e-154"><a name="BKMK_SQLConsumeBinding"></a>64 ビット インストールで アダプター サービスのアドインまたはアダプター サービス参照の追加プラグインを使用しているときにエラー</span><span class="sxs-lookup"><span data-stu-id="96b8e-154"><a name="BKMK_SQLConsumeBinding"></a> Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="96b8e-155">**問題**</span><span class="sxs-lookup"><span data-stu-id="96b8e-155">**Problem**</span></span>  
  
 <span data-ttu-id="96b8e-156">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-156">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="96b8e-157">**原因**</span><span class="sxs-lookup"><span data-stu-id="96b8e-157">**Cause**</span></span>  
  
 <span data-ttu-id="96b8e-158">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-158">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="96b8e-159">64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。</span><span class="sxs-lookup"><span data-stu-id="96b8e-159">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="96b8e-160">そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-160">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="96b8e-161">ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、そのため起動、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグイン、machine.config ファイルの 32 ビット バージョンのバインドをチェックし、エラーが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="96b8e-161">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="96b8e-162">**解決策**</span><span class="sxs-lookup"><span data-stu-id="96b8e-162">**Resolution**</span></span>  
  
 <span data-ttu-id="96b8e-163">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-163">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="96b8e-164">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-164">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="96b8e-165">32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="96b8e-165">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
###  <span data-ttu-id="96b8e-166"><a name="BKMK_SQLInvalidBinding"></a>BizTalk Server 管理コンソールで、64 ビット インストールでの SQL アダプタ ポートを構成中に無効なバインド エラー</span><span class="sxs-lookup"><span data-stu-id="96b8e-166"><a name="BKMK_SQLInvalidBinding"></a> Invalid binding error while configuring SQL adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="96b8e-167">**問題**</span><span class="sxs-lookup"><span data-stu-id="96b8e-167">**Problem**</span></span>  
  
 <span data-ttu-id="96b8e-168">アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-168">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "sqlBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="96b8e-169">**原因**</span><span class="sxs-lookup"><span data-stu-id="96b8e-169">**Cause**</span></span>  
  
 <span data-ttu-id="96b8e-170">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-170">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="96b8e-171">64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。</span><span class="sxs-lookup"><span data-stu-id="96b8e-171">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="96b8e-172">そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-172">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="96b8e-173">ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、32 ビット プロセスとして実行されるされため、アダプターのポートを構成するときに、machine.config ファイルの 32 ビット バージョンのバインドを確認エラーは失敗します。</span><span class="sxs-lookup"><span data-stu-id="96b8e-173">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="96b8e-174">**解決策**</span><span class="sxs-lookup"><span data-stu-id="96b8e-174">**Resolution**</span></span>  
  
 <span data-ttu-id="96b8e-175">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-175">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="96b8e-176">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-176">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="96b8e-177">32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="96b8e-177">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96b8e-178">参照</span><span class="sxs-lookup"><span data-stu-id="96b8e-178">See Also</span></span>  
 [<span data-ttu-id="96b8e-179">SQL アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="96b8e-179">Troubleshoot the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/troubleshoot-the-sql-adapter.md)