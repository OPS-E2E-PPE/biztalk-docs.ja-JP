---
title: Oracle E-business Suite アダプターを使用したインストールの問題のトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 09b3af20-ab87-44e8-8ded-c19432552be7
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fb1d5f0e1f17870c9824b30e5da55a2740cb81b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968131"
---
# <a name="troubleshoot-installation-issues-with-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="d8368-102">Oracle E-business Suite アダプターを使用したインストールの問題のトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="d8368-102">Troubleshoot Installation Issues with the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="d8368-103">Microsoft のインストール[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]コンピューターで、製品バイナリをコピーし、各アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="d8368-103">Installation of the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] copies the product binaries on the computer and registers the bindings for each adapter.</span></span> <span data-ttu-id="d8368-104">このセクションでは、インストール エラーを解決するトラブルシューティングの手法を使用して説明します。</span><span class="sxs-lookup"><span data-stu-id="d8368-104">This section discusses using troubleshooting techniques to resolve installation errors.</span></span>  

## <a name="logging-messages-for-setup-actions"></a><span data-ttu-id="d8368-105">セットアップ操作ではログ メッセージ</span><span class="sxs-lookup"><span data-stu-id="d8368-105">Logging Messages for Setup Actions</span></span>  
 <span data-ttu-id="d8368-106">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ プログラムをインストールする標準的なタスクを実行する、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d8368-106">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup program performs the standard task of installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d8368-107">さらに、セットアップには、アダプターのバインドを登録するなどの特定のカスタム アクションも実行します。</span><span class="sxs-lookup"><span data-stu-id="d8368-107">Additionally, the setup also performs certain custom actions such as registering the adapter bindings.</span></span> <span data-ttu-id="d8368-108">セットアップを実行する標準とカスタムの操作のメッセージを記録できます。</span><span class="sxs-lookup"><span data-stu-id="d8368-108">You can log messages for both the standard as well as custom actions that the setup performs.</span></span>  

- <span data-ttu-id="d8368-109">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ MSI を使用してアダプターに固有のファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d8368-109">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup installs the adapter-specific files using an MSI.</span></span> <span data-ttu-id="d8368-110">したがって、セットアップのログ記録は、標準の MSI ログです。</span><span class="sxs-lookup"><span data-stu-id="d8368-110">Therefore, the logging for the setup is the standard MSI logging.</span></span> <span data-ttu-id="d8368-111">[Windows インストーラーのログ記録](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx)について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="d8368-111">[Windows Installer Logging](https://msdn.microsoft.com/library/windows/desktop/aa372847.aspx) provides more details.</span></span> 

- <span data-ttu-id="d8368-112">セットアップ プログラムを実行するカスタム アクションのすべてのログは %temp%\adaptersetup.log でご利用いただけます。</span><span class="sxs-lookup"><span data-stu-id="d8368-112">All logs for the custom actions that the setup program performs are available at %TEMP%\adaptersetup.log.</span></span> <span data-ttu-id="d8368-113">ログ ファイルにトレースが失敗した場合、トレースはイベント ログで使用できるもします。</span><span class="sxs-lookup"><span data-stu-id="d8368-113">If the tracing to the log file fails, the traces are also available in the event log.</span></span>  

## <a name="known-issues"></a><span data-ttu-id="d8368-114">既知の問題</span><span class="sxs-lookup"><span data-stu-id="d8368-114">Known Issues</span></span>  
 <span data-ttu-id="d8368-115">インストールするときに発生する可能性が最も一般的なエラーを次に、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]と共に、考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="d8368-115">The following are the most common errors you might encounter when installing the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], along with their probable cause and resolution.</span></span>  



###  <a name="BKMK_OraAppBinding"></a> <span data-ttu-id="d8368-116">セットアップが失敗するアダプターのバインドを登録するには</span><span class="sxs-lookup"><span data-stu-id="d8368-116">Setup fails to register adapter bindings</span></span>  
 <span data-ttu-id="d8368-117">**問題**</span><span class="sxs-lookup"><span data-stu-id="d8368-117">**Problem**</span></span>  

 <span data-ttu-id="d8368-118">Microsoft[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ ウィザードは、アダプターのバインドを登録に失敗するが、アダプターのインストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="d8368-118">The Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup wizard fails to register the adapter bindings, but proceeds with the adapter installation.</span></span>  

 <span data-ttu-id="d8368-119">**原因**</span><span class="sxs-lookup"><span data-stu-id="d8368-119">**Cause**</span></span>  

 <span data-ttu-id="d8368-120">問題があります[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストール、[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]インストール、または壊れている machine.config ファイル。</span><span class="sxs-lookup"><span data-stu-id="d8368-120">This might result due to problems with [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] installation, [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span> <span data-ttu-id="d8368-121">アダプターのバインドは、machine.config ファイルに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="d8368-121">The adapter bindings are written to the machine.config file.</span></span>  

 <span data-ttu-id="d8368-122">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="d8368-122">**Resolution**</span></span>  

 <span data-ttu-id="d8368-123">手動で登録する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="d8368-123">You should manually register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span>  

##### <a name="to-register-the-adapter-binding"></a><span data-ttu-id="d8368-124">アダプターのバインドを登録するには</span><span class="sxs-lookup"><span data-stu-id="d8368-124">To register the adapter binding</span></span>  

1. <span data-ttu-id="d8368-125">コンピューターの machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="d8368-125">Navigate to the machine.config file on the computer.</span></span> <span data-ttu-id="d8368-126">たとえば、32 ビット プラットフォームで、machine.config はで使用可能な\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG します。</span><span class="sxs-lookup"><span data-stu-id="d8368-126">For example, on a 32-bit platform, the machine.config is available under \<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  

    <span data-ttu-id="d8368-127">このパスで\<*バージョン*\>は .NET Framework のバージョンです。</span><span class="sxs-lookup"><span data-stu-id="d8368-127">In this path, \<*version*\> is the version of the .NET Framework.</span></span>  

2. <span data-ttu-id="d8368-128">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="d8368-128">Open the file by using a text editor.</span></span>  

3. <span data-ttu-id="d8368-129">登録する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインド。</span><span class="sxs-lookup"><span data-stu-id="d8368-129">To register the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding:</span></span>  

   1. <span data-ttu-id="d8368-130">要素の"system.serviceModel"を検索し、その下にある、次を追加します。</span><span class="sxs-lookup"><span data-stu-id="d8368-130">Search for the element "system.serviceModel" and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleebs" />  
      </client>  
      ```  

   2. <span data-ttu-id="d8368-131">"BindingElementExtensions"system.serviceModel\extensions 下の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="d8368-131">Search for the element "bindingElementExtensions" under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="d8368-132">不足している検索[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="d8368-132">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="d8368-133">"BindingElementExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="d8368-133">Add the following section under the "bindingElementExtensions" node.</span></span>  

       <span data-ttu-id="d8368-134">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="d8368-134">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="oracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="d8368-135">"BindingExtensions"system.serviceModel\extensions 下の要素を検索します。</span><span class="sxs-lookup"><span data-stu-id="d8368-135">Search for the element "bindingExtensions" under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="d8368-136">不足している検索[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]バインドします。</span><span class="sxs-lookup"><span data-stu-id="d8368-136">Look for the missing [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] binding.</span></span> <span data-ttu-id="d8368-137">"BindingExtensions"ノードの下の次のセクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="d8368-137">Add the following section under the "bindingExtensions" node.</span></span>  

       <span data-ttu-id="d8368-138">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="d8368-138">For [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="oracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  <span data-ttu-id="d8368-139">公開キーとバージョンを確認する方法については、[公開キーとバージョンを決定する](#BKMK_PubKey)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d8368-139">For information about how to determine the public key and the version, see [Determining the Public Key and Version](#BKMK_PubKey).</span></span>  

4. <span data-ttu-id="d8368-140">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="d8368-140">Save and close the machine.config file.</span></span>  

####  <a name="BKMK_PubKey"></a> <span data-ttu-id="d8368-141">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="d8368-141">Determining the Public Key and Version</span></span>  
 <span data-ttu-id="d8368-142">公開キーを確認するには、次の手順を実行[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d8368-142">Perform the following steps to determine the public key for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  

###### <a name="to-determine-the-public-key"></a><span data-ttu-id="d8368-143">公開キーを確認するには</span><span class="sxs-lookup"><span data-stu-id="d8368-143">To determine the public key</span></span>  

1. <span data-ttu-id="d8368-144">Windows ディレクトリの通常 C:\WINDOWS\assembly に移動します。</span><span class="sxs-lookup"><span data-stu-id="d8368-144">Navigate to the Windows directory, typically C:\WINDOWS\assembly.</span></span>  

2. <span data-ttu-id="d8368-145">対象の公開キーと、バージョンを選び、DLL を右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="d8368-145">Right-click the DLL for which you want the public key and the version, and then select **Properties**.</span></span> <span data-ttu-id="d8368-146">次の表に、DLL の名前[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d8368-146">The following table lists the name of the DLL for [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  


   |                                         <span data-ttu-id="d8368-147">[アダプター]</span><span class="sxs-lookup"><span data-stu-id="d8368-147">Adapter</span></span>                                         |       <span data-ttu-id="d8368-148">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="d8368-148">Name of the DLL</span></span>        |
   |-----------------------------------------------------------------------------------------|------------------------------|
   | [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] | <span data-ttu-id="d8368-149">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="d8368-149">Microsoft.Adapters.OracleEBS</span></span> |


3. <span data-ttu-id="d8368-150">**全般**タブの値を比較、**公開キー トークンの**ラベルは、DLL の公開キーを指定します。</span><span class="sxs-lookup"><span data-stu-id="d8368-150">On the **General** tab, the value against the **Public Key Token** label specifies the public key for the DLL.</span></span> <span data-ttu-id="d8368-151">同様に、値、**バージョン**ラベルは、DLL のバージョン番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="d8368-151">Similarly, value against the **Version** label specifies the version number for the DLL.</span></span>  

4. <span data-ttu-id="d8368-152">クリックして、公開キーをコピー**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="d8368-152">Copy the public key, and then click **Cancel**.</span></span>  

###  <a name="BKMK_ConsumeOraApp"></a> <span data-ttu-id="d8368-153">Consume Adapter Service アドインまたはアダプター サービス参照の追加プラグインを使用して、64 ビットのインストール中にエラー</span><span class="sxs-lookup"><span data-stu-id="d8368-153">Error while using the Consume Adapter Service add-in or Add Adapter Service Reference plug-in on a 64-bit installation</span></span>  
 <span data-ttu-id="d8368-154">**問題**</span><span class="sxs-lookup"><span data-stu-id="d8368-154">**Problem**</span></span>  

 <span data-ttu-id="d8368-155">使用して、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]の 64 ビット バージョンを実行する 64 ビット コンピューターで、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]次のエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8368-155">Using the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] on a 64-bit computer running 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] results in the following error:</span></span>  

```  
No valid adapters are installed on this machine  
```  

 <span data-ttu-id="d8368-156">**原因**</span><span class="sxs-lookup"><span data-stu-id="d8368-156">**Cause**</span></span>  

 <span data-ttu-id="d8368-157">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]が machine.config ファイルの System.ServiceModel で登録されている、WCF カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="d8368-157">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="d8368-158">64 ビット プラットフォームには、2 つの machine.config ファイル、64 ビット アプリケーションで使用されるその他および 32 ビット アプリケーションによって使用されるものです。</span><span class="sxs-lookup"><span data-stu-id="d8368-158">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="d8368-159">そのため、64 ビット版をインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="d8368-159">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="d8368-160">ただし、 [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 32 ビット プロセスとして実行し、起動したときにそのため、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]から[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]、プラグインのバインディングは、machine.config ファイルの 32 ビット バージョンをチェックし、失敗エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8368-160">However, [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] runs as a 32-bit process and hence when you launch the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], the plug-in checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  

 <span data-ttu-id="d8368-161">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="d8368-161">**Resolution**</span></span>  

- <span data-ttu-id="d8368-162">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="d8368-162">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="d8368-163">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="d8368-163">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="d8368-164">32 ビットおよび 64 ビットのサイド バイ サイドでインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d8368-164">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  

- <span data-ttu-id="d8368-165">更新プログラム セット 11.1.0.7 で Oracle クライアント 11.1.0.6 の Oracle のデータ アクセス コンポーネントの 32 ビットおよび 64 ビット両方のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d8368-165">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="d8368-166">ODP.NET の最新バージョンで、アプリケーションの動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8368-166">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="d8368-167">詳細についてを参照してください"Oracle データ プロバイダーの .NET FAQ" [ http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)します。</span><span class="sxs-lookup"><span data-stu-id="d8368-167">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  

###  <a name="BKMK_OraAppInvalidBinding"></a> <span data-ttu-id="d8368-168">64 ビット インストールで BizTalk Server 管理コンソールでの Oracle E-business Suite アダプターのポートを構成するときに無効なバインド エラー</span><span class="sxs-lookup"><span data-stu-id="d8368-168">Invalid binding error while configuring Oracle E-Business Suite adapter ports in BizTalk Server Administration Console on a 64-bit installation</span></span>  
 <span data-ttu-id="d8368-169">**問題**</span><span class="sxs-lookup"><span data-stu-id="d8368-169">**Problem**</span></span>  

 <span data-ttu-id="d8368-170">アダプターのポートを構成しようとすると[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、次のエラーを取得します。</span><span class="sxs-lookup"><span data-stu-id="d8368-170">When you try to configure a port for the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you get the following error:</span></span>  

```  
"Unable to create binding configuration element for editing. Check the values of the BindingType and BindingConfiguration properties.  
(Microsoft.Biztalk.Adapter.Wcf.Converters.CreateBindingException) Unable to get binding type for binding extension "oracleEBSBinding".  
Verify the binding extension is registered in machine.config."  
```  

 <span data-ttu-id="d8368-171">**原因**</span><span class="sxs-lookup"><span data-stu-id="d8368-171">**Cause**</span></span>  

 <span data-ttu-id="d8368-172">[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]が machine.config ファイルの System.ServiceModel で登録されている、WCF カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="d8368-172">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] is a WCF custom binding, which is registered under System.ServiceModel in the machine.config file.</span></span> <span data-ttu-id="d8368-173">64 ビット プラットフォームには、2 つの machine.config ファイル、64 ビット アプリケーションで使用されるその他および 32 ビット アプリケーションによって使用されるものです。</span><span class="sxs-lookup"><span data-stu-id="d8368-173">A 64-bit platform has two machine.config files, one used by the 32-bit applications and the other used by the 64-bit applications.</span></span> <span data-ttu-id="d8368-174">そのため、64 ビット版をインストールするときに、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]、セットアップ ウィザードは、machine.config ファイルの 64 ビット バージョンのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="d8368-174">So, when you install the 64-bit version of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)], the setup wizard registers the bindings in the 64-bit version of the machine.config file.</span></span> <span data-ttu-id="d8368-175">ただし、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールは、32 ビット プロセスとして実行され、そのため、アダプターのポートを構成するときにチェック、machine.config ファイルの 32 ビット バージョンにバインドし失敗エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="d8368-175">However, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console runs as a 32-bit process and hence when you configure a port for the adapter, it checks for the bindings in the 32-bit version of the machine.config file and fails giving an error.</span></span>  

 <span data-ttu-id="d8368-176">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="d8368-176">**Resolution**</span></span>  

- <span data-ttu-id="d8368-177">32 ビットおよび 64 ビット バージョンの両方をインストール、 [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] 64 ビット[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="d8368-177">Install both the 32-bit and 64-bit versions of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] on a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span>  

  > [!IMPORTANT]
  >  <span data-ttu-id="d8368-178">64 ビットのみが必要[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]インストールします。</span><span class="sxs-lookup"><span data-stu-id="d8368-178">You must only have a 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] installation.</span></span> <span data-ttu-id="d8368-179">32 ビットおよび 64 ビットのサイド バイ サイドでインストール[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]1 台のコンピューターではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="d8368-179">Side-by-side installation of 32-bit and 64-bit [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] on a single computer is not supported.</span></span>  

- <span data-ttu-id="d8368-180">更新プログラム セット 11.1.0.7 で Oracle クライアント 11.1.0.6 の Oracle のデータ アクセス コンポーネントの 32 ビットおよび 64 ビット両方のバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d8368-180">Install both the 32-bit and 64-bit versions of the Oracle Data Access Components for Oracle Client 11.1.0.6 with Patch Set 11.1.0.7.</span></span>  

  > [!NOTE]
  >  <span data-ttu-id="d8368-181">ODP.NET の最新バージョンで、アプリケーションの動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="d8368-181">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="d8368-182">詳細についてを参照してください"Oracle データ プロバイダーの .NET FAQ" [ http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834)します。</span><span class="sxs-lookup"><span data-stu-id="d8368-182">For more information, see "Oracle Data Provider for .NET FAQ" at [http://go.microsoft.com/fwlink/p/?LinkId=92834](http://go.microsoft.com/fwlink/p/?LinkId=92834).</span></span>  

## <a name="see-also"></a><span data-ttu-id="d8368-183">参照</span><span class="sxs-lookup"><span data-stu-id="d8368-183">See Also</span></span>  
[<span data-ttu-id="d8368-184">Oracle EBS アダプターのトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d8368-184">Troubleshooting the Oracle EBS adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/troubleshooting-the-oracle-ebs-adapter.md)