---
title: BizTalk Adapter Pack 2016 のインストール手順を投稿 |Microsoft Docs
description: BAP など 2016 をインストールした後に完了する手順は、BizTalk 管理コンソール、Oracle、更新プログラムおよびアダプターのバインドを登録するアダプターを追加します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b8946bfe-92bb-470d-bec4-9bc3a07ce0d2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43a454e1e6f1dc65d8a2e2c5493aacf9375374b2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997379"
---
# <a name="post-installation-steps-for-biztalk-adapter-pack-2016"></a><span data-ttu-id="0c420-103">BizTalk Adapter Pack 2016 のインストール後の手順</span><span class="sxs-lookup"><span data-stu-id="0c420-103">Post installation steps for BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="0c420-104">インストールした後、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、いくつかのインストール後の手順します。</span><span class="sxs-lookup"><span data-stu-id="0c420-104">After you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], there are some post-installation steps.</span></span> <span data-ttu-id="0c420-105">このトピックでは、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c420-105">This topic lists these steps.</span></span>   

## <a name="add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="0c420-106">アダプターを BizTalk 管理コンソールに追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-106">Add the adapter to BizTalk Administration</span></span>

1. <span data-ttu-id="0c420-107">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="0c420-107">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="0c420-108">展開、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="0c420-108">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  

3. <span data-ttu-id="0c420-109">右クリック**アダプター**を選択します**新規**、選び**アダプター**します。</span><span class="sxs-lookup"><span data-stu-id="0c420-109">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  

    <span data-ttu-id="0c420-110">![アダプターを追加する](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="0c420-110">![Add an adapter](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  

4. <span data-ttu-id="0c420-111">**アダプター プロパティ**などのボックスの一覧からアダプターを選択**WCF-SAP**など、名前を入力します**WCF-SAP**します。</span><span class="sxs-lookup"><span data-stu-id="0c420-111">In the **Adapter Properties**, select an adapter from the drop-down list, such as **WCF-SAP**, and then enter a name, such as **WCF-SAP**.</span></span>  

    <span data-ttu-id="0c420-112">![SAP アダプターを BizTalk に追加](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span><span class="sxs-lookup"><span data-stu-id="0c420-112">![Add SAP Adapter to BizTalk](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span></span>  

5. <span data-ttu-id="0c420-113">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="0c420-113">Select **OK**.</span></span>  

## <a name="use-a-newer-oracledataaccessdll-version"></a><span data-ttu-id="0c420-114">新しい Oracle.DataAccess.dll バージョンを使用して、</span><span class="sxs-lookup"><span data-stu-id="0c420-114">Use a newer Oracle.DataAccess.dll version</span></span>  

<span data-ttu-id="0c420-115">Wcf-oracledb アダプターを使用または生成されたアダプターを使用する Visual Studio を使用するポートを構成するときに、アダプターが Oracle.DataAccess.dll バージョン 2.111.7.0 必要があることをメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c420-115">When you configure a port to use the WCF-OracleDB adapter or use Visual Studio to consume a generated adapter, a message displays that the adapter needs Oracle.DataAccess.dll version 2.111.7.0.</span></span> <span data-ttu-id="0c420-116">このメッセージを解決するには、サポートされている Oracle.DataAccess.dll バージョンをインストールします (を参照してください[サポート対象バージョンの一覧](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))、し、更新、`bindingRedirect`次の手順を使用して OracleDB 構成ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="0c420-116">To resolve this message, install a supported Oracle.DataAccess.dll version (see [supported version list](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)), and then update the `bindingRedirect` element in the OracleDB configuration file using the following steps:</span></span>  

1.  <span data-ttu-id="0c420-117">BizTalk Server では、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c420-117">On the BizTalk Server, go to the following folders:</span></span>  

     <span data-ttu-id="0c420-118">*ドライブ*: \Program Files\Microsoft BizTalk Adapter Pack (x64) \bin</span><span class="sxs-lookup"><span data-stu-id="0c420-118">*drive*:\Program Files\Microsoft BizTalk Adapter Pack(x64)\bin</span></span>  

     <span data-ttu-id="0c420-119">*ドライブ*: \Program Files (x86) \Microsoft BizTalk Adapter Pack\bin</span><span class="sxs-lookup"><span data-stu-id="0c420-119">*drive*:\Program Files (x86)\Microsoft BizTalk Adapter Pack\bin</span></span>  

2.  <span data-ttu-id="0c420-120">Microsoft.Adapters.OracleDB.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c420-120">Open the Microsoft.Adapters.OracleDB.config file.</span></span>  

3.  <span data-ttu-id="0c420-121">次のセクションの検索とし、コピー/貼り付け、次の。</span><span class="sxs-lookup"><span data-stu-id="0c420-121">Find the following section, and then copy/paste the following:</span></span>  

    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  

    ```  

    > [!NOTE]
    >  <span data-ttu-id="0c420-122">この例では設定*newVersion* 2.112.1.00 にします。</span><span class="sxs-lookup"><span data-stu-id="0c420-122">In this example, we set *newVersion* to 2.112.1.00.</span></span> <span data-ttu-id="0c420-123">この値は、インストールしたバージョンに設定します。</span><span class="sxs-lookup"><span data-stu-id="0c420-123">Set this value to the version you have installed.</span></span>  

> [!IMPORTANT]
> - <span data-ttu-id="0c420-124">このグループに複数の BizTalk Server がある場合は、グループ内のすべての BizTalk サーバー上でこの変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="0c420-124">If there are multiple BizTalk Servers in this group, make this change on all the BizTalk servers in the group.</span></span>  
> - <span data-ttu-id="0c420-125">*NewVersion* Oracle.DataAccess.dll ファイルをコンピューターにインストールされているのバージョンに基づいて更新する値が必要です。</span><span class="sxs-lookup"><span data-stu-id="0c420-125">The *newVersion* value needs to be updated based on the version of the Oracle.DataAccess.dll file installed on the computer.</span></span>  <span data-ttu-id="0c420-126">Oracle.DataAccess.dll は、Oracle からインストールする Oracle クライアントと共に含まれます。</span><span class="sxs-lookup"><span data-stu-id="0c420-126">Oracle.DataAccess.dll is included with the Oracle Client you install from Oracle.</span></span>  <span data-ttu-id="0c420-127">Oracle クライアント バージョンをインストールする必要がありますのみ[BizTalk Adapter Pack でサポートされている](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="0c420-127">You must only install an Oracle Client version that is [supported by the BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).</span></span>  

## <a name="create-sql-server-database-objects-sap-adapter-only"></a><span data-ttu-id="0c420-128">SQL Server データベース オブジェクト (SAP アダプターのみ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="0c420-128">Create SQL Server Database objects (SAP adapter only)</span></span>  
 <span data-ttu-id="0c420-129">SAP システムで Trfc を呼び出すには、実行、 *SapAdapter-DbScript-Install.sql* SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="0c420-129">To invoke tRFCs in an SAP system, run the *SapAdapter-DbScript-Install.sql* SQL script.</span></span> <span data-ttu-id="0c420-130">このスクリプトがインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、SQL Server のデータベース オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="0c420-130">This script is installed with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, and creates database objects in SQL Server.</span></span> <span data-ttu-id="0c420-131">スクリプトは通常にインストールされて*\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]* します。</span><span class="sxs-lookup"><span data-stu-id="0c420-131">The script is typically installed at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span></span> <span data-ttu-id="0c420-132">Trfc を呼び出すため、アダプターを使用しているときにそのデータベース名を入力する場合に限り、任意の SQL Server データベースに対してこのスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="0c420-132">You can run this script against any SQL Server database, as long as you enter that database name while using the adapter to invoke tRFCs.</span></span>

## <a name="register-the-adapter-bindings"></a><span data-ttu-id="0c420-133">アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="0c420-133">Register the adapter bindings</span></span>
<span data-ttu-id="0c420-134">中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストール、セットアップ ウィザードがアダプター バインドまたは、.NET Framework Data Provider for mySAP Business Suite を登録に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c420-134">During the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, the setup wizard may fail to register the adapter bindings or the .NET Framework Data Provider for mySAP Business Suite.</span></span> <span data-ttu-id="0c420-135">アダプターのインストール、セットアップが続行されます。</span><span class="sxs-lookup"><span data-stu-id="0c420-135">And the setup proceeds with the adapter installation.</span></span> <span data-ttu-id="0c420-136">これは、Windows Communication Foundation (WCF) のインストールによって発生する可能性があります、[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]インストール、または壊れている machine.config ファイル。</span><span class="sxs-lookup"><span data-stu-id="0c420-136">This may be caused by the Windows Communication Foundation (WCF) installation, the [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="0c420-137">次の手順を完了*のみ*machine.config ファイルで、アダプターのバインド、または .NET Framework データ プロバイダーを登録するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="0c420-137">Complete the following steps *only* if the setup wizard fails to register the adapter bindings, or .NET Framework Data Providers in the machine.config file.</span></span>  

1. <span data-ttu-id="0c420-138">コンピューターの machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="0c420-138">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="0c420-139">たとえば、32 ビット プラットフォームで、machine.config はで使用可能な*\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG*します。</span><span class="sxs-lookup"><span data-stu-id="0c420-139">For example, on a 32-bit platform, the machine.config is available under *\<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG*.</span></span>  

2. <span data-ttu-id="0c420-140">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="0c420-140">Open the file using a text editor.</span></span>  

3. <span data-ttu-id="0c420-141">アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="0c420-141">Register the adapter bindings:</span></span>  

   1. <span data-ttu-id="0c420-142">検索、`system.serviceModel`要素、およびその下にある次の追加。</span><span class="sxs-lookup"><span data-stu-id="0c420-142">Search for the `system.serviceModel` element, and add the following under it:</span></span>  

      ```  
      <client>  
        <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
        <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
        <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
        <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
        <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
      </client>  
      ```  

   2. <span data-ttu-id="0c420-143">検索、 `bindingElementExtensions` system.serviceModel\extensions の下の要素。</span><span class="sxs-lookup"><span data-stu-id="0c420-143">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  

   3. <span data-ttu-id="0c420-144">不足しているアダプターのバインドを探します。</span><span class="sxs-lookup"><span data-stu-id="0c420-144">Look for the missing adapter binding.</span></span> <span data-ttu-id="0c420-145">次のセクションを追加、`bindingElementExtensions`ノード、不足しているアダプターのバインドによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0c420-145">Add the following sections under the `bindingElementExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="0c420-146">セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのバインドを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c420-146">You must register all the bindings if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="0c420-147">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-147">For the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-148">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-148">For the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  

      ```  
      <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-149">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-149">For the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  

      ```  
      <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-150">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-150">For the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-151">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-151">For the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   4. <span data-ttu-id="0c420-152">検索、 `bindingExtensions` system.serviceModel\extensions の下の要素。</span><span class="sxs-lookup"><span data-stu-id="0c420-152">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  

   5. <span data-ttu-id="0c420-153">不足しているアダプターのバインドを探します。</span><span class="sxs-lookup"><span data-stu-id="0c420-153">Look for the missing adapter binding.</span></span> <span data-ttu-id="0c420-154">次のセクションを追加、`bindingExtensions`ノード、不足しているアダプターのバインドによって異なります。</span><span class="sxs-lookup"><span data-stu-id="0c420-154">Add the following sections under the `bindingExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="0c420-155">セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのバインドを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c420-155">You must register all the bindings if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="0c420-156">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-156">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  

      ```  
      <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-157">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-157">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  

      ```  
      <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-158">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-158">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  

      ```  
      <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-159">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-159">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  

      ```  
      <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-160">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-160">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  

      ```  
      <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

   > [!NOTE]
   >  <span data-ttu-id="0c420-161">公開キーの値を取得するには、次を参照してください。**公開キーとバージョン特定**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="0c420-161">To get the public key value, see **Determine the public key and version** (in this topic).</span></span>  

4. <span data-ttu-id="0c420-162">.NET Framework データ プロバイダーを登録します。</span><span class="sxs-lookup"><span data-stu-id="0c420-162">Register the .NET Framework data providers:</span></span>  

   1. <span data-ttu-id="0c420-163">検索、 `DbProviderFactories` system.data ノードの下の要素。</span><span class="sxs-lookup"><span data-stu-id="0c420-163">Search for the `DbProviderFactories` element under the system.data node.</span></span>  

   2. <span data-ttu-id="0c420-164">不足している .NET Framework データ プロバイダーを探します。</span><span class="sxs-lookup"><span data-stu-id="0c420-164">Look for the missing .NET Framework Data Providers.</span></span> <span data-ttu-id="0c420-165">次のセクションを追加、`DbProviderFactories`不足しているプロバイダーによって、ノード。</span><span class="sxs-lookup"><span data-stu-id="0c420-165">Add the following sections under the `DbProviderFactories` node, depending on the missing provider.</span></span> <span data-ttu-id="0c420-166">セットアップ ウィザードは、いずれかの登録が失敗した場合は、すべてのプロバイダーを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c420-166">You must register all the providers if the setup wizard fails to register any.</span></span>  

       <span data-ttu-id="0c420-167">[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-167">For the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], add:</span></span>  

      ```  
      <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
          description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

       <span data-ttu-id="0c420-168">[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="0c420-168">For the [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], add:</span></span>  

      ```  
      <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
          description=".NET Framework Data Provider for Siebel eBusiness Applications"  
          type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
      ```  

5. <span data-ttu-id="0c420-169">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="0c420-169">Save and close the machine.config file.</span></span>  

## <a name="determine-the-public-key-and-version"></a><span data-ttu-id="0c420-170">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="0c420-170">Determine the public key and version</span></span>  
 <span data-ttu-id="0c420-171">公開キーと、アダプターまたは .NET Framework Data Provider のバージョンを確認するのには、次の手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="0c420-171">Complete the following steps to determine the public key and version for an adapter or the .NET Framework Data Provider.</span></span>  

1. <span data-ttu-id="0c420-172">通常、Windows ディレクトリに移動*C:\WINDOWS\assembly*します。</span><span class="sxs-lookup"><span data-stu-id="0c420-172">Go to the Windows directory, typically *C:\WINDOWS\assembly*.</span></span>  

2. <span data-ttu-id="0c420-173">DLL を公開キーを必要し、し、選択を右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="0c420-173">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="0c420-174">次の表では、各アダプターおよびプロバイダーの Dll の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="0c420-174">The following table lists the name of the DLLs for each adapter and provider:</span></span>  


   |                         <span data-ttu-id="0c420-175">アダプターおよび .NET Framework データ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="0c420-175">Adapter/.NET Framework Data Provider</span></span>                         |       <span data-ttu-id="0c420-176">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="0c420-176">Name of the DLL</span></span>        |
   |--------------------------------------------------------------------------------------|------------------------------|
   |           [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]           |    <span data-ttu-id="0c420-177">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="0c420-177">Microsoft.Adapters.SAP</span></span>    |
   |        [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]        |  <span data-ttu-id="0c420-178">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="0c420-178">Microsoft.Adapters.Siebel</span></span>   |
   |        [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]        | <span data-ttu-id="0c420-179">Microsoft.Adapters.OracleDB</span><span class="sxs-lookup"><span data-stu-id="0c420-179">Microsoft.Adapters.OracleDB</span></span>  |
   | [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)] | <span data-ttu-id="0c420-180">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="0c420-180">Microsoft.Adapters.OracleEBS</span></span> |
   |            [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]            |  <span data-ttu-id="0c420-181">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="0c420-181">Microsoft.Adapters.Sql.dll</span></span>  |
   |        [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]        |   <span data-ttu-id="0c420-182">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="0c420-182">Microsoft.Data.SAPClient</span></span>   |
   |     [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]     | <span data-ttu-id="0c420-183">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="0c420-183">Microsoft.Data.SiebelClient</span></span>  |


3. <span data-ttu-id="0c420-184">**全般** タブで、**公開キー トークンの**値は、DLL の公開キー。</span><span class="sxs-lookup"><span data-stu-id="0c420-184">On the **General** tab, the **Public Key Token** value is the public key for the DLL.</span></span> <span data-ttu-id="0c420-185">**バージョン**値は、DLL のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="0c420-185">The **Version** value is the version number for the DLL.</span></span>  

4. <span data-ttu-id="0c420-186">公開キーをコピーし、**キャンセル**します。</span><span class="sxs-lookup"><span data-stu-id="0c420-186">Copy the public key, and then select **Cancel**.</span></span>  

## <a name="install-the-custom-rfcs"></a><span data-ttu-id="0c420-187">カスタム Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0c420-187">Install the custom RFCs</span></span>  
<span data-ttu-id="0c420-188">必要なだけ*場合*を使用する、 [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0c420-188">Required only *if* you want to use the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="0c420-189">参照してください[インストールのカスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)で、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="0c420-189">See [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) in the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentation.</span></span> 

> [!IMPORTANT]
>  <span data-ttu-id="0c420-190">提供されるカスタム Rfc の以前のバージョンを使用しているかどうか、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、このリリースで提供する Rfc にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c420-190">If you are using an earlier version of the custom RFCs provided with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], then you must upgrade them to the RFCs provided with this release.</span></span> <span data-ttu-id="0c420-191">そうでは、以前の Rfc を削除し、このリリースに含まれている Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0c420-191">Do this by removing the earlier RFCs, and then installing the RFCs included with this release.</span></span>  

## <a name="install-the-enterprise-applications"></a><span data-ttu-id="0c420-192">エンタープライズ アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="0c420-192">Install the enterprise applications</span></span>  
<span data-ttu-id="0c420-193">手順と、さまざまなエンタープライズ LOB システムをインストールするためのガイダンスでは、エンタープライズ システムによって提供されるインストール ガイドの使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0c420-193">For the steps and guidance to install the different enterprise LOB systems, we recommend you use the installation guides provided by the enterprise system.</span></span> <span data-ttu-id="0c420-194">存在する場合は、特定の構成の変更は、アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c420-194">Also refer to its adapter documentation for specific configuration changes, if any.</span></span>   

## <a name="installation-and-post-installation-checklist"></a><span data-ttu-id="0c420-195">インストールとインストール後のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="0c420-195">Installation and post-installation checklist</span></span>  

- <span data-ttu-id="0c420-196">すべてをインストールすることを確認、[ソフトウェアの前提条件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)正しいインストール オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="0c420-196">Make sure you installed all the [software prerequisites](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) with the correct installation option.</span></span>

- <span data-ttu-id="0c420-197">インストールされているコンピューターにインストールされているエンタープライズ LOB アプリケーションのサポートされているバージョンがあるかどうかを確認、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="0c420-197">Make sure you have the supported version of the enterprise LOB applications installed on your computer where you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="0c420-198">参照してください[サポートされている基幹業務 (LOB) システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)します。</span><span class="sxs-lookup"><span data-stu-id="0c420-198">See [Supported Line-of-Business (LOB) systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx).</span></span>  

- <span data-ttu-id="0c420-199">エンタープライズに接続する LOB システムのアダプターのみをインストールすることをインストールしたことを確認して、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**カスタム**インストール オプションです。</span><span class="sxs-lookup"><span data-stu-id="0c420-199">To install only the adapter for the enterprise LOB system you want to connect, make sure you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the **Custom** installation option.</span></span> <span data-ttu-id="0c420-200">使用していないことを確認、**完了**インストール オプションです。</span><span class="sxs-lookup"><span data-stu-id="0c420-200">Make sure you did not use the **Complete** installation option.</span></span> <span data-ttu-id="0c420-201">参照してください[BizTalk Adapter Pack をインストールする](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c420-201">See [Installing the BizTalk Adapter Pack](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md).</span></span>  

- <span data-ttu-id="0c420-202">TRFC の呼び出しを使用して、SAP システムを作成するかどうか、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、SQL Server データベースで必要なテーブルを作成するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c420-202">If you want to make tRFC calls to the SAP system using the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], make sure you create the required tables in a SQL Server database.</span></span> <span data-ttu-id="0c420-203">参照してください**SQL Server データベースの作成オブジェクト**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="0c420-203">See **Create SQL Server Database objects** (in this topic).</span></span>

- <span data-ttu-id="0c420-204">実行中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードでは、バインドを登録できませんでしたというエラー メッセージが表示可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0c420-204">While running the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup wizard, you may get an error message that states the setup failed to register the bindings.</span></span> <span data-ttu-id="0c420-205">場合は、手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="0c420-205">If so, register them manually.</span></span> <span data-ttu-id="0c420-206">参照してください**アダプターのバインドを登録**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="0c420-206">See **Register the adapter bindings** (in this topic).</span></span>  

- <span data-ttu-id="0c420-207">インストールした場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールでは、SAP システムにカスタム Rfc をインストールするかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0c420-207">If you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure you install the custom RFCs on the SAP system.</span></span> <span data-ttu-id="0c420-208">参照してください[カスタム Rfc をインストール](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="0c420-208">See [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>

## <a name="more-good-info"></a><span data-ttu-id="0c420-209">詳細な情報</span><span class="sxs-lookup"><span data-stu-id="0c420-209">More good info</span></span>
[<span data-ttu-id="0c420-210">変更または削除する BizTalk Adapter Pack</span><span class="sxs-lookup"><span data-stu-id="0c420-210">Change or remove the BizTalk Adapter Pack</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="0c420-211">BizTalk Adapter Pack に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="0c420-211">BizTalk Adapter Pack FAQ</span></span>](../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)