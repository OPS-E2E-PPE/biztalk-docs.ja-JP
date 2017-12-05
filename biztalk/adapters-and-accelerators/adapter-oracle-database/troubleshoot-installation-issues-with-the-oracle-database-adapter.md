---
title: "Oracle データベース アダプターのインストールに関するトラブルシューティング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation issues, troubleshooting
- troubleshooting, installation issues
ms.assetid: 2054b725-d657-4039-b83b-119571935f62
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dc2603a2e86d29797919fb51c3985c384ff9580
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="troubleshoot-installation-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="da333-102">Oracle データベース アダプターのインストールに関するをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="da333-102">Troubleshoot installation issues with the Oracle Database adapter</span></span>
<span data-ttu-id="da333-103">Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="da333-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="da333-104">このセクションでは、インストール エラーを解決するのにはトラブルシューティングの手法の使用について説明しもいくつかの既知の問題を示します。</span><span class="sxs-lookup"><span data-stu-id="da333-104">This section discusses using troubleshooting techniques to resolve installation errors, and also lists some known issues.</span></span>  
  
## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="da333-105">セットアップ操作のログ メッセージ</span><span class="sxs-lookup"><span data-stu-id="da333-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="da333-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="da333-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="da333-107">さらに、セットアップでは、アダプターのバインドの登録などの特定のカスタム アクションも実行します。</span><span class="sxs-lookup"><span data-stu-id="da333-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="da333-108">セットアップを実行する標準的なだけでなくカスタムの操作のメッセージをログに記録できます。</span><span class="sxs-lookup"><span data-stu-id="da333-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  
  
-   <span data-ttu-id="da333-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] MSI を使用してアダプターに固有のファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da333-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="da333-110">したがって、セットアップのログ記録は、標準の MSI ログです。</span><span class="sxs-lookup"><span data-stu-id="da333-110">Therefore, the logging for the setup is the standard MSI logging.</span></span> 
  
-   <span data-ttu-id="da333-111">セットアップ プログラムを実行するカスタム アクションのすべてのログは %temp%\adaptersetup.log です。</span><span class="sxs-lookup"><span data-stu-id="da333-111">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="da333-112">ログ ファイルにトレースが失敗した場合、トレースもイベント ログにできます。</span><span class="sxs-lookup"><span data-stu-id="da333-112">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  
  
##  <a name="BKMK_OraDBBinding"></a><span data-ttu-id="da333-113">アダプターのバインドの登録に失敗します。</span><span class="sxs-lookup"><span data-stu-id="da333-113">Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="da333-114">**問題**</span><span class="sxs-lookup"><span data-stu-id="da333-114">**Problem**</span></span>  
  
 <span data-ttu-id="da333-115">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドの登録に失敗するが、アダプターのインストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="da333-115">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  
  
 <span data-ttu-id="da333-116">**原因**</span><span class="sxs-lookup"><span data-stu-id="da333-116">**Cause**</span></span>  
  
 <span data-ttu-id="da333-117">問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。</span><span class="sxs-lookup"><span data-stu-id="da333-117">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="da333-118">アダプターのバインドは、machine.config ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="da333-118">The adapter bindings are written to the machine.config file.</span></span>  
  
 <span data-ttu-id="da333-119">**解決策**</span><span class="sxs-lookup"><span data-stu-id="da333-119">**Resolution**</span></span>  
  
<span data-ttu-id="da333-120">手動で登録、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド。</span><span class="sxs-lookup"><span data-stu-id="da333-120">Manually register the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding:</span></span> 
  
1.  <span data-ttu-id="da333-121">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="da333-121">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="da333-122">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG です。</span><span class="sxs-lookup"><span data-stu-id="da333-122">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
     <span data-ttu-id="da333-123">このパスに\<バージョン\>.NET Framework のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="da333-123">In this path, \<version\> is the version of the .NET Framework.</span></span>  
  
2.  <span data-ttu-id="da333-124">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="da333-124">Open the file by using a text editor.</span></span>  
  
3.  <span data-ttu-id="da333-125">登録する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド。</span><span class="sxs-lookup"><span data-stu-id="da333-125">To register the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding:</span></span>  
  
    1.  <span data-ttu-id="da333-126">要素"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="da333-126">Search for the element "system.serviceModel" and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="da333-127">"BindingElementExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="da333-127">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="da333-128">不足している検索[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="da333-128">Look for the missing [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding.</span></span> <span data-ttu-id="da333-129">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="da333-129">Add the following section under the "bindingElementExtensions" node.</span></span>  
  
         <span data-ttu-id="da333-130">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="da333-130">For [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="da333-131">"BindingExtensions"system.serviceModel\extensions 下にある要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="da333-131">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="da333-132">不足している検索[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="da333-132">Look for the missing [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding.</span></span> <span data-ttu-id="da333-133">"BindingExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="da333-133">Add the following section under the "bindingExtensions" node.</span></span>  
  
         <span data-ttu-id="da333-134">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="da333-134">For [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="da333-135">公開キーとバージョンを確認する方法については、次を参照してください。[公開キーとバージョンを決定する](#BKMK_PubKey)です。</span><span class="sxs-lookup"><span data-stu-id="da333-135">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  
  
4.  <span data-ttu-id="da333-136">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="da333-136">Save and close the machine.config file.</span></span>  
  
####  <a name="BKMK_PubKey"></a><span data-ttu-id="da333-137">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="da333-137">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="da333-138">公開キーを確認するには、次の手順を実行[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="da333-138">Perform the following steps to determine the public key for [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
1.  <span data-ttu-id="da333-139">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="da333-139">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  
  
2.  <span data-ttu-id="da333-140">公開キーと、バージョンを対象し、なるを選択し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="da333-140">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="da333-141">次の表に、dll の名前[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="da333-141">The following table lists the name of the DLL for [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
    |<span data-ttu-id="da333-142">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="da333-142">Adapter</span></span>|<span data-ttu-id="da333-143">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="da333-143">Name of the DLL</span></span>|  
    |-------------|---------------------|  
    |[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]|<span data-ttu-id="da333-144">Microsoft.Adapters.OracleDB</span><span class="sxs-lookup"><span data-stu-id="da333-144">Microsoft.Adapters.OracleDB</span></span>|  
  
3.  <span data-ttu-id="da333-145">**全般** タブの値と比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="da333-145">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="da333-146">同様に、値のに対して、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="da333-146">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="da333-147">公開キーをコピーし、をクリックして**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="da333-147">Copy the public key, and then click **Cancel**.</span></span>  
  
##  <a name="BKMK_ConsumeBinding"></a><span data-ttu-id="da333-148">64 ビット インストールで アダプター サービスのアドインまたはアダプター サービス参照の追加プラグインを使用しているときにエラー</span><span class="sxs-lookup"><span data-stu-id="da333-148">Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="da333-149">**問題**</span><span class="sxs-lookup"><span data-stu-id="da333-149">**Problem**</span></span>  
  
 <span data-ttu-id="da333-150">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="da333-150">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  
  
```  
No valid adapters are installed on this machine  
```  
  
 <span data-ttu-id="da333-151">**原因**</span><span class="sxs-lookup"><span data-stu-id="da333-151">**Cause**</span></span>  
  
 <span data-ttu-id="da333-152">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。</span><span class="sxs-lookup"><span data-stu-id="da333-152">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="da333-153">64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。</span><span class="sxs-lookup"><span data-stu-id="da333-153">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="da333-154">そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="da333-154">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="da333-155">ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、そのため起動、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグイン、machine.config ファイルの 32 ビット バージョンのバインドをチェックし、エラーが失敗しました。</span><span class="sxs-lookup"><span data-stu-id="da333-155">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="da333-156">**解決策**</span><span class="sxs-lookup"><span data-stu-id="da333-156">**Resolution**</span></span>  
  
-   <span data-ttu-id="da333-157">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="da333-157">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="da333-158">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="da333-158">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="da333-159">32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="da333-159">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="da333-160">Oracle クライアント 11.1.0.6 パッチ セット 11.1.0.7 に Oracle Data Access Components の 32 ビットおよび 64 ビット両方のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da333-160">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="da333-161">アプリケーションは ODP.NET の最新のバージョンで動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="da333-161">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="da333-162">詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイトです。</span><span class="sxs-lookup"><span data-stu-id="da333-162">For more information, see [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) on Oracle's website.</span></span>  
  
##  <a name="BKMK_InvalidBinding"></a><span data-ttu-id="da333-163">BizTalk Server 管理コンソールで、64 ビット インストールでの Oracle データベース アダプターのポートの構成中に無効なバインド エラー</span><span class="sxs-lookup"><span data-stu-id="da333-163">Invalid binding error while configuring Oracle database adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="da333-164">**問題**</span><span class="sxs-lookup"><span data-stu-id="da333-164">**Problem**</span></span>  
  
 <span data-ttu-id="da333-165">アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="da333-165">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  
  
```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleDBBinding".  
Verify the binding extension is registered in machine.config."  
```  
  
 <span data-ttu-id="da333-166">**原因**</span><span class="sxs-lookup"><span data-stu-id="da333-166">**Cause**</span></span>  
  
 <span data-ttu-id="da333-167">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] System.ServiceModel、machine.config ファイルには登録されている WCF カスタム バインドは、します。</span><span class="sxs-lookup"><span data-stu-id="da333-167">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="da333-168">64 ビット プラットフォームに 2 つの machine.config ファイル、32 ビット アプリケーションで使用されるものと、他の 64 ビット アプリケーションで使用されるあります。</span><span class="sxs-lookup"><span data-stu-id="da333-168">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="da333-169">そのため、64 ビット バージョンをインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="da333-169">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="da333-170">ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、32 ビット プロセスとして実行されるされため、アダプターのポートを構成するときに、machine.config ファイルの 32 ビット バージョンのバインドを確認エラーは失敗します。</span><span class="sxs-lookup"><span data-stu-id="da333-170">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  
  
 <span data-ttu-id="da333-171">**解決策**</span><span class="sxs-lookup"><span data-stu-id="da333-171">**Resolution**</span></span>  
  
-   <span data-ttu-id="da333-172">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="da333-172">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="da333-173">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="da333-173">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="da333-174">32 ビットおよび 64 ビットのサイド バイ サイド インストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされません。</span><span class="sxs-lookup"><span data-stu-id="da333-174">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  
  
-   <span data-ttu-id="da333-175">Oracle クライアント 11.1.0.6 パッチ セット 11.1.0.7 に Oracle Data Access Components の 32 ビットおよび 64 ビット両方のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="da333-175">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="da333-176">アプリケーションは ODP.NET の最新のバージョンで動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="da333-176">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="da333-177">詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイトです。</span><span class="sxs-lookup"><span data-stu-id="da333-177">For more information, see [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) on Oracle website.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="da333-178">参照</span><span class="sxs-lookup"><span data-stu-id="da333-178">See Also</span></span>  
[<span data-ttu-id="da333-179">Oracle データベース アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="da333-179">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)