---
title: "Oracle E-business Suite アダプターでのインストールに関する問題のトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 09b3af20-ab87-44e8-8ded-c19432552be7
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29fbee54262f1b45e3cc9be67c057767a80b325f
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="84d02-102">Oracle E-business Suite アダプターでのインストールに関する問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="84d02-102">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="84d02-103">Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="84d02-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="84d02-104">このセクションでは、インストール エラーを解決するのには、トラブルシューティングの手法を使用してについて説明します。</span><span class="sxs-lookup"><span data-stu-id="84d02-104">This section discusses using troubleshooting techniques to resolve installation errors.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="84d02-105">セットアップ操作のログ メッセージ</span><span class="sxs-lookup"><span data-stu-id="84d02-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="84d02-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="84d02-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="84d02-107">さらに、セットアップでは、アダプターのバインドの登録などの特定のカスタム アクションも実行します。</span><span class="sxs-lookup"><span data-stu-id="84d02-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="84d02-108">セットアップを実行する標準的なだけでなくカスタムの操作のメッセージをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="84d02-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="84d02-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] MSI を使用してアダプターに固有のファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84d02-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="84d02-110">したがって、セットアップのログ記録は、標準の MSI ログです。</span><span class="sxs-lookup"><span data-stu-id="84d02-110">Therefore, the logging for the setup is the standard MSI logging.</span></span> <span data-ttu-id="84d02-111">[Windows インストーラーのログ記録](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx)詳細を示します。</span><span class="sxs-lookup"><span data-stu-id="84d02-111">[Windows Installer Logging](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx) provides more details.</span></span> 
  
-   <span data-ttu-id="84d02-112">セットアップ プログラムを実行するカスタム アクションのすべてのログは %temp%\adaptersetup.log です。</span><span class="sxs-lookup"><span data-stu-id="84d02-112">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="84d02-113">ログ ファイルにトレースが失敗した場合、トレースもイベント ログにできます。</span><span class="sxs-lookup"><span data-stu-id="84d02-113">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="84d02-114">既知の問題</span><span class="sxs-lookup"><span data-stu-id="84d02-114">Known Issues</span></span>  
 <span data-ttu-id="84d02-115">インストールするときに発生する可能性が最も一般的なエラーは、次のとおり、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、およびその考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="84d02-115">The following are the most common errors you might encounter when installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  
  
  
  
###  <a name="BKMK_OraAppBinding"></a><span data-ttu-id="84d02-116">アダプターのバインドの登録に失敗します。</span><span class="sxs-lookup"><span data-stu-id="84d02-116">Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="84d02-117">**問題**</span><span class="sxs-lookup"><span data-stu-id="84d02-117">**Problem**</span></span>  
  
 <span data-ttu-id="84d02-118">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドの登録に失敗するが、アダプターのインストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="84d02-118">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="84d02-119">**原因**</span><span class="sxs-lookup"><span data-stu-id="84d02-119">**Cause**</span></span>  
  
 <span data-ttu-id="84d02-120">問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。</span><span class="sxs-lookup"><span data-stu-id="84d02-120">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="84d02-121">アダプターのバインドは、machine.config ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="84d02-121">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="84d02-122">**解決策**</span><span class="sxs-lookup"><span data-stu-id="84d02-122">**Resolution**</span></span>  
  
 <span data-ttu-id="84d02-123">手動で登録する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="84d02-123">You should manually register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span>  
  
##### <a name="to-register-the-adapter-binding"></a><span data-ttu-id="84d02-124">アダプターのバインドを登録するには</span><span class="sxs-lookup"><span data-stu-id="84d02-124">To register the adapter binding</span></span>  
  
1.  <span data-ttu-id="84d02-125">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="84d02-125">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="84d02-126">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="84d02-126">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="84d02-127">このパスに\<*バージョン*\> .NET Framework のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="84d02-127">In this path, \<*version*\> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="84d02-128">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="84d02-128">Open the file by using a text editor.</span></span>  
  
3.  <span data-ttu-id="84d02-129">登録する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインド。</span><span class="sxs-lookup"><span data-stu-id="84d02-129">To register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="84d02-130">要素"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="84d02-130">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleebs" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="84d02-131">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="84d02-131">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="84d02-132">不足している検索[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="84d02-132">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="84d02-133">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="84d02-133">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="84d02-134">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="84d02-134">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="84d02-135">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="84d02-135">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="84d02-136">不足している検索[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="84d02-136">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="84d02-137">"BindingExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="84d02-137">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="84d02-138">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="84d02-138">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="84d02-139">公開キーとバージョンを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。</span><span class="sxs-lookup"><span data-stu-id="84d02-139">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="84d02-140">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="84d02-140">Save and close the machine.config file.</span></span>  
  
####  <a name="BKMK_PubKey"></a><span data-ttu-id="84d02-141">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="84d02-141">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="84d02-142">公開キーを確認するには、次の手順を実行[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="84d02-142">Perform the following steps to determine the public key for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
###### <a name="to-determine-the-public-key"></a><span data-ttu-id="84d02-143">公開キーを確認するには</span><span class="sxs-lookup"><span data-stu-id="84d02-143">To determine the public key</span></span>  
  
1.  <span data-ttu-id="84d02-144">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="84d02-144">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="84d02-145">公開キーと、バージョンを対象し、なるを選択し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="84d02-145">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="84d02-146">次の表に、dll の名前[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="84d02-146">The following table lists the name of the DLL for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
    |<span data-ttu-id="84d02-147">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="84d02-147">Adapter</span></span>|<span data-ttu-id="84d02-148">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="84d02-148">Name of the DLL</span></span>|  
    |-------------|---------------------|  
    |[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="84d02-149">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="84d02-149">Microsoft.Adapters.OracleEBS</span></span>|  
  
3.  <span data-ttu-id="84d02-150">**全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="84d02-150">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="84d02-151">同様に、値のに対して、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="84d02-151">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="84d02-152">公開キーをコピーし、をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="84d02-152">Copy the public key, and then click **Cancel**.</span></span>  
  
###  <a name="BKMK_ConsumeOraApp"></a><span data-ttu-id="84d02-153">64 ビット インストールで アダプター サービスのアドインまたはアダプター サービス参照の追加プラグインを使用しているときにエラー</span><span class="sxs-lookup"><span data-stu-id="84d02-153">Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="84d02-154">**問題**</span><span class="sxs-lookup"><span data-stu-id="84d02-154">**Problem**</span></span>  
  
 <span data-ttu-id="84d02-155">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="84d02-155">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="84d02-156">**原因**</span><span class="sxs-lookup"><span data-stu-id="84d02-156">**Cause**</span></span>  
  
 <span data-ttu-id="84d02-157">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。</span><span class="sxs-lookup"><span data-stu-id="84d02-157">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="84d02-158">64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。</span><span class="sxs-lookup"><span data-stu-id="84d02-158">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="84d02-159">そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="84d02-159">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="84d02-160">ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、そのため起動、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグイン、machine.config ファイルの 32 ビット バージョンのバインドをチェックし、エラーが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="84d02-160">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="84d02-161">**解決策**</span><span class="sxs-lookup"><span data-stu-id="84d02-161">**Resolution**</span></span>  
  
-   <span data-ttu-id="84d02-162">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="84d02-162">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="84d02-163">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="84d02-163">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="84d02-164">32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="84d02-164">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="84d02-165">Oracle クライアント 11.1.0.6 パッチ セット 11.1.0.7 に Oracle Data Access Components の 32 ビットおよび 64 ビット両方のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84d02-165">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84d02-166">アプリケーションは ODP.NET の最新のバージョンで動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="84d02-166">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="84d02-167">詳細についてで「Oracle データ プロバイダーの .NET よく寄せられる質問」を参照してください。 [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)です。</span><span class="sxs-lookup"><span data-stu-id="84d02-167">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  
  
###  <a name="BKMK_OraAppInvalidBinding"></a><span data-ttu-id="84d02-168">BizTalk Server 管理コンソールで、64 ビット インストールで Oracle E-business Suite アダプターのポートを構成中に無効なバインド エラー</span><span class="sxs-lookup"><span data-stu-id="84d02-168">Invalid binding error while configuring Oracle E-Business Suite adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="84d02-169">**問題**</span><span class="sxs-lookup"><span data-stu-id="84d02-169">**Problem**</span></span>  
  
 <span data-ttu-id="84d02-170">アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="84d02-170">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleEBSBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="84d02-171">**原因**</span><span class="sxs-lookup"><span data-stu-id="84d02-171">**Cause**</span></span>  
  
 <span data-ttu-id="84d02-172">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。</span><span class="sxs-lookup"><span data-stu-id="84d02-172">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="84d02-173">64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。</span><span class="sxs-lookup"><span data-stu-id="84d02-173">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="84d02-174">そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="84d02-174">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="84d02-175">ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、32 ビット プロセスとして実行されるされため、アダプターのポートを構成するときに、machine.config ファイルの 32 ビット バージョンのバインドを確認エラーは失敗します。</span><span class="sxs-lookup"><span data-stu-id="84d02-175">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="84d02-176">**解決策**</span><span class="sxs-lookup"><span data-stu-id="84d02-176">**Resolution**</span></span>  
  
-   <span data-ttu-id="84d02-177">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="84d02-177">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="84d02-178">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="84d02-178">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="84d02-179">32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="84d02-179">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="84d02-180">Oracle クライアント 11.1.0.6 パッチ セット 11.1.0.7 に Oracle Data Access Components の 32 ビットおよび 64 ビット両方のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="84d02-180">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="84d02-181">アプリケーションは ODP.NET の最新のバージョンで動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="84d02-181">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="84d02-182">詳細についてで「Oracle データ プロバイダーの .NET よく寄せられる質問」を参照してください。 [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)です。</span><span class="sxs-lookup"><span data-stu-id="84d02-182">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84d02-183">参照</span><span class="sxs-lookup"><span data-stu-id="84d02-183">See Also</span></span>  
[<span data-ttu-id="84d02-184">Oracle EBS アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="84d02-184">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)