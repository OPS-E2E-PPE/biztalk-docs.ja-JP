---
title: "BizTalk アダプター パック 2016 のインストールの手順を投稿 |Microsoft ドキュメント"
description: "BAP など 2016 をインストールした後に完了する手順については、BizTalk 管理コンソールで、更新 Oracle の場合、アダプターのバインドを登録するアダプターを追加します。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b8946bfe-92bb-470d-bec4-9bc3a07ce0d2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17bd0a76cacb35563448f31f79c2275c79b92ab8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="post-installation-steps-for-biztalk-adapter-pack-2016"></a><span data-ttu-id="8ab77-103">BizTalk アダプター パック 2016 のインストールの手順を投稿します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-103">Post installation steps for BizTalk Adapter Pack 2016</span></span>
<span data-ttu-id="8ab77-104">インストールした後、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、いくつかのインストール後の手順です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-104">After you install the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], there are some post-installation steps.</span></span> <span data-ttu-id="8ab77-105">このトピックでは、次の手順を示します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-105">This topic lists these steps.</span></span>   

## <a name="add-the-adapter-to-biztalk-administration"></a><span data-ttu-id="8ab77-106">BizTalk 管理コンソールに、アダプターを追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-106">Add the adapter to BizTalk Administration</span></span>
  
1.  <span data-ttu-id="8ab77-107">開く、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="8ab77-107">Open the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="8ab77-108">展開して、 **BizTalk グループ**、展開**プラットフォームの設定**、し、**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-108">Expand the **BizTalk Group**, expand **Platform Settings**, and then select **Adapters**.</span></span>  
  
3.  <span data-ttu-id="8ab77-109">右クリック**アダプター****新規**を選択して**アダプター**です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-109">Right-click **Adapters**, select **New**, and select **Adapter**.</span></span>  
  
     <span data-ttu-id="8ab77-110">![アダプタの追加](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span><span class="sxs-lookup"><span data-stu-id="8ab77-110">![Add an adapter](../adapters-and-accelerators/media/c9610d42-8465-4099-b403-87df6dcd0d99.gif "c9610d42-8465-4099-b403-87df6dcd0d99")</span></span>  
  
4.  <span data-ttu-id="8ab77-111">**アダプターのプロパティ**、ドロップダウン リストからアダプターを選択**WCF SAP**などの名前を入力し、 **WCF SAP**です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-111">In the **Adapter Properties**, select an adapter from the drop-down list, such as **WCF-SAP**, and then enter a name, such as **WCF-SAP**.</span></span>  
  
     <span data-ttu-id="8ab77-112">![BizTalk への SAP アダプターの追加](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span><span class="sxs-lookup"><span data-stu-id="8ab77-112">![Add SAP Adapter to BizTalk](../adapters-and-accelerators/media/a1235b38-ab93-4233-924d-42710540b951.gif "a1235b38-ab93-4233-924d-42710540b951")</span></span>  
  
5.  <span data-ttu-id="8ab77-113">**[OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-113">Select **OK**.</span></span>  

## <a name="use-a-newer-oracledataaccessdll-version"></a><span data-ttu-id="8ab77-114">新しい Oracle.DataAccess.dll バージョンを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-114">Use a newer Oracle.DataAccess.dll version</span></span>  

<span data-ttu-id="8ab77-115">Wcf-oracledb アダプターを使用または生成されたアダプターを使用する Visual Studio を使用するためのポートを構成するときに、アダプターが Oracle.DataAccess.dll バージョン 2.111.7.0 必要があること、メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ab77-115">When you configure a port to use the WCF-OracleDB adapter or use Visual Studio to consume a generated adapter, a message displays that the adapter needs Oracle.DataAccess.dll version 2.111.7.0.</span></span> <span data-ttu-id="8ab77-116">このメッセージを解決するには、サポートされている Oracle.DataAccess.dll バージョンをインストール (を参照してください[バージョンのリストをサポート](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx))、し、更新、`bindingRedirect`次の手順を使用して OracleDB 構成ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="8ab77-116">To resolve this message, install a supported Oracle.DataAccess.dll version (see [supported version list](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)), and then update the `bindingRedirect` element in the OracleDB configuration file using the following steps:</span></span>  
  
1.  <span data-ttu-id="8ab77-117">BizTalk Server では、次のフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-117">On the BizTalk Server, go to the following folders:</span></span>  
  
     <span data-ttu-id="8ab77-118">*ドライブ*: \Program Files\Microsoft BizTalk Adapter Pack (x64) \bin</span><span class="sxs-lookup"><span data-stu-id="8ab77-118">*drive*:\Program Files\Microsoft BizTalk Adapter Pack(x64)\bin</span></span>  
  
     <span data-ttu-id="8ab77-119">*ドライブ*: \Program Files (x86) \Microsoft BizTalk Adapter Pack\bin</span><span class="sxs-lookup"><span data-stu-id="8ab77-119">*drive*:\Program Files (x86)\Microsoft BizTalk Adapter Pack\bin</span></span>  
  
2.  <span data-ttu-id="8ab77-120">Microsoft.Adapters.OracleDB.config ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8ab77-120">Open the Microsoft.Adapters.OracleDB.config file.</span></span>  
  
3.  <span data-ttu-id="8ab77-121">次のセクションを見つけて、コピー/貼り付け、次。</span><span class="sxs-lookup"><span data-stu-id="8ab77-121">Find the following section, and then copy/paste the following:</span></span>  
  
    ```  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
              <dependentAssembly>  
                        <assemblyIdentity name="Oracle.DataAccess" publicKeyToken="89b483f429c47342" culture="neutral" />  
                        <bindingRedirect oldVersion="2.111.7.00" newVersion="2.112.1.00"/>  
              </dependentAssembly>  
    </assemblyBinding>  
  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8ab77-122">この例では設定*newVersion* 2.112.1.00 にします。</span><span class="sxs-lookup"><span data-stu-id="8ab77-122">In this example, we set *newVersion* to 2.112.1.00.</span></span> <span data-ttu-id="8ab77-123">この値をインストールしたバージョンに設定します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-123">Set this value to the version you have installed.</span></span>  
  
> [!IMPORTANT]
> - <span data-ttu-id="8ab77-124">このグループに複数の BizTalk Server がある場合は、グループ内のすべての BizTalk サーバーでこの変更を行います。</span><span class="sxs-lookup"><span data-stu-id="8ab77-124">If there are multiple BizTalk Servers in this group, make this change on all the BizTalk servers in the group.</span></span>  
> - <span data-ttu-id="8ab77-125">*NewVersion* Oracle.DataAccess.dll ファイルをコンピューターにインストールされているのバージョンに基づく更新する値が必要です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-125">The *newVersion* value needs to be updated based on the version of the Oracle.DataAccess.dll file installed on the computer.</span></span>  <span data-ttu-id="8ab77-126">Oracle.DataAccess.dll は、Oracle からインストールする Oracle クライアントに含まれています。</span><span class="sxs-lookup"><span data-stu-id="8ab77-126">Oracle.DataAccess.dll is included with the Oracle Client you install from Oracle.</span></span>  <span data-ttu-id="8ab77-127">される Oracle クライアント バージョンをインストールする必要がありますのみ[BizTalk Adapter Pack でサポートされている](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-127">You must only install an Oracle Client version that is [supported by the BizTalk Adapter Pack](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx).</span></span>  
  
## <a name="create-sql-server-database-objects-sap-adapter-only"></a><span data-ttu-id="8ab77-128">SQL Server データベース オブジェクト (SAP アダプターのみ) を作成します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-128">Create SQL Server Database objects (SAP adapter only)</span></span>  
 <span data-ttu-id="8ab77-129">SAP システムで tRFCs を呼び出し、実行、 *SapAdapter DbScript-Install.sql* SQL スクリプト。</span><span class="sxs-lookup"><span data-stu-id="8ab77-129">To invoke tRFCs in an SAP system, run the *SapAdapter-DbScript-Install.sql* SQL script.</span></span> <span data-ttu-id="8ab77-130">このスクリプトがインストールされている、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストールし、SQL Server でデータベース オブジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-130">This script is installed with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, and creates database objects in SQL Server.</span></span> <span data-ttu-id="8ab77-131">インストールされている通常の*\<インストール ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-131">The script is typically installed at *\<installation drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]*.</span></span> <span data-ttu-id="8ab77-132">TRFCs を呼び出すため、アダプターを使用しているときにそのデータベース名を入力する限り、任意の SQL Server データベースに対してこのスクリプトを実行できます。</span><span class="sxs-lookup"><span data-stu-id="8ab77-132">You can run this script against any SQL Server database, as long as you enter that database name while using the adapter to invoke tRFCs.</span></span>
  
## <a name="register-the-adapter-bindings"></a><span data-ttu-id="8ab77-133">アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-133">Register the adapter bindings</span></span>
<span data-ttu-id="8ab77-134">中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストール、セットアップ ウィザードがアダプターのバインドが、または、.NET Framework Data Provider for mySAP Business Suite を登録に失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ab77-134">During the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, the setup wizard may fail to register the adapter bindings or the .NET Framework Data Provider for mySAP Business Suite.</span></span> <span data-ttu-id="8ab77-135">アダプターのインストールが、セットアップが続行されます。</span><span class="sxs-lookup"><span data-stu-id="8ab77-135">And the setup proceeds with the adapter installation.</span></span> <span data-ttu-id="8ab77-136">これは、Windows Communication Foundation (WCF) のインストールによって起こります、[!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)]インストール、または壊れている可能性が machine.config ファイルです。</span><span class="sxs-lookup"><span data-stu-id="8ab77-136">This may be caused by the Windows Communication Foundation (WCF) installation, the [!INCLUDE[afproductnamelong](../includes/afproductnamelong-md.md)] installation, or the machine.config file being corrupt.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="8ab77-137">次の手順を完了*のみ*machine.config ファイルに、アダプターのバインド、または .NET Framework データ プロバイダーを登録するセットアップ ウィザードが失敗した場合。</span><span class="sxs-lookup"><span data-stu-id="8ab77-137">Complete the following steps *only* if the setup wizard fails to register the adapter bindings, or .NET Framework Data Providers in the machine.config file.</span></span>  
  
1.  <span data-ttu-id="8ab77-138">コンピューター上の machine.config ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-138">Go to the machine.config file on the computer.</span></span> <span data-ttu-id="8ab77-139">たとえば、32 ビット プラットフォームで、machine.config は下にある使用可能な*\<システム ドライブ\>: \WINDOWS\Microsoft.NET\Framework\\< バージョン\>\CONFIG*です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-139">For example, on a 32-bit platform, the machine.config is available under *\<system drive\>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG*.</span></span>  
  
2.  <span data-ttu-id="8ab77-140">テキスト エディターを使用してファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="8ab77-140">Open the file using a text editor.</span></span>  
  
3.  <span data-ttu-id="8ab77-141">アダプターのバインドを登録します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-141">Register the adapter bindings:</span></span>  
  
    1.  <span data-ttu-id="8ab77-142">検索、`system.serviceModel`要素、およびその下にある次の追加。</span><span class="sxs-lookup"><span data-stu-id="8ab77-142">Search for the `system.serviceModel` element, and add the following under it:</span></span>  
  
        ```  
        <client>  
          <endpoint binding="sapBinding" contract="IMetadataExchange" name="sap" />  
          <endpoint binding="siebelBinding" contract="IMetadataExchange" name="siebel" />  
          <endpoint binding="oracleDBBinding" contract="IMetadataExchange" name="oracleDb" />  
          <endpoint binding="oracleEBSBinding" contract="IMetadataExchange" name="oracleEBS" />  
          <endpoint binding="sqlBinding" contract="IMetadataExchange" name="mssql" />  
        </client>  
        ```  
  
    2.  <span data-ttu-id="8ab77-143">検索、 `bindingElementExtensions` system.serviceModel\extensions 下にある要素。</span><span class="sxs-lookup"><span data-stu-id="8ab77-143">Search for the `bindingElementExtensions` element under system.serviceModel\extensions.</span></span>  
  
    3.  <span data-ttu-id="8ab77-144">不足しているアダプターのバインドを探します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-144">Look for the missing adapter binding.</span></span> <span data-ttu-id="8ab77-145">次のセクションを追加、`bindingElementExtensions`バインドに応じて、不足しているアダプターのノードです。</span><span class="sxs-lookup"><span data-stu-id="8ab77-145">Add the following sections under the `bindingElementExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="8ab77-146">セットアップ ウィザードに任意登録に失敗した場合、すべてのバインドを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ab77-146">You must register all the bindings if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="8ab77-147">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-147">For the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapAdapter" type="Microsoft.Adapters.SAP.SAPAdapterExtensionElement,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-148">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-148">For the [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelAdapter" type="Microsoft.Adapters.Siebel.SiebelAdapterExtensionElement,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-149">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-149">For the [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleDBAdapter" type="Microsoft.Adapters.OracleDB.OracleDBAdapterExtensionElement,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-150">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-150">For the [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="OracleEBSAdapter" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingElementExtensionElement, Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-151">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-151">For the [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlAdapter" type="Microsoft.Adapters.Sql.SqlAdapterBindingElementExtensionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    4.  <span data-ttu-id="8ab77-152">検索、 `bindingExtensions` system.serviceModel\extensions 下にある要素。</span><span class="sxs-lookup"><span data-stu-id="8ab77-152">Search for the `bindingExtensions` element under system.serviceModel\extensions.</span></span>  
  
    5.  <span data-ttu-id="8ab77-153">不足しているアダプターのバインドを探します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-153">Look for the missing adapter binding.</span></span> <span data-ttu-id="8ab77-154">次のセクションを追加、`bindingExtensions`バインドに応じて、不足しているアダプターのノードです。</span><span class="sxs-lookup"><span data-stu-id="8ab77-154">Add the following sections under the `bindingExtensions` node, depending on the missing adapter binding.</span></span> <span data-ttu-id="8ab77-155">セットアップ ウィザードに任意登録に失敗した場合、すべてのバインドを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ab77-155">You must register all the bindings if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="8ab77-156">[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-156">For [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], add:</span></span>  
  
        ```  
        <add name="sapBinding" type="Microsoft.Adapters.SAP.SAPAdapterBindingSection,Microsoft.Adapters.SAP, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-157">[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-157">For [!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)], add:</span></span>  
  
        ```  
        <add name="siebelBinding" type="Microsoft.Adapters.Siebel.SiebelAdapterBindingSection,Microsoft.Adapters.Siebel, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-158">[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-158">For [!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)], add:</span></span>  
  
        ```  
        <add name="oracleDBBinding" type="Microsoft.Adapters.OracleDB.OracleDBAdapterBindingSection,Microsoft.Adapters.OracleDB, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-159">[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-159">For [!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)], add:</span></span>  
  
        ```  
        <add name="OracleEBSBinding" type="Microsoft.Adapters.OracleEBS.OracleEBSBindingCollectionElement, Microsoft.Adapters.OracleEBS,Microsoft.Adapters.OracleEBS, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-160">[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-160">For [!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)], add:</span></span>  
  
        ```  
        <add name="sqlBinding" type="Microsoft.Adapters.Sql.SqlAdapterBindingCollectionElement,Microsoft.Adapters.Sql, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
    > [!NOTE]
    >  <span data-ttu-id="8ab77-161">公開キーの値を取得するには、次を参照してください。**公開キーとバージョン特定**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="8ab77-161">To get the public key value, see **Determine the public key and version** (in this topic).</span></span>  
  
4.  <span data-ttu-id="8ab77-162">.NET Framework データ プロバイダーを登録します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-162">Register the .NET Framework data providers:</span></span>  
  
    1.  <span data-ttu-id="8ab77-163">検索、 `DbProviderFactories` system.data ノードの下の要素。</span><span class="sxs-lookup"><span data-stu-id="8ab77-163">Search for the `DbProviderFactories` element under the system.data node.</span></span>  
  
    2.  <span data-ttu-id="8ab77-164">不足している .NET Framework データ プロバイダーを探します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-164">Look for the missing .NET Framework Data Providers.</span></span> <span data-ttu-id="8ab77-165">下にある次のセクションを追加、`DbProviderFactories`ノード、不足しているプロバイダーによっても異なります。</span><span class="sxs-lookup"><span data-stu-id="8ab77-165">Add the following sections under the `DbProviderFactories` node, depending on the missing provider.</span></span> <span data-ttu-id="8ab77-166">セットアップ ウィザードに任意登録に失敗した場合は、すべてのプロバイダーを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ab77-166">You must register all the providers if the setup wizard fails to register any.</span></span>  
  
         <span data-ttu-id="8ab77-167">[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-167">For the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SAPClient Data Provider" invariant="Microsoft.Data.SAPClient"   
            description=".NET Framework Data Provider for mySAP Business Suite"    type="Microsoft.Data.SAPClient.SAPClientFactory,Microsoft.Data.SAPClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
         <span data-ttu-id="8ab77-168">[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]を追加します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-168">For the [!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)], add:</span></span>  
  
        ```  
        <add name="SiebelClient Data Provider" invariant="Microsoft.Data.SiebelClient"  
            description=".NET Framework Data Provider for Siebel eBusiness Applications"  
            type="Microsoft.Data.SiebelClient.SiebelProviderFactory,Microsoft.Data.SiebelClient, Version=<version>, Culture=neutral, PublicKeyToken=<public key>" />  
        ```  
  
5.  <span data-ttu-id="8ab77-169">machine.config ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="8ab77-169">Save and close the machine.config file.</span></span>  
  
## <a name="determine-the-public-key-and-version"></a><span data-ttu-id="8ab77-170">公開キーとバージョンを決定します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-170">Determine the public key and version</span></span>  
 <span data-ttu-id="8ab77-171">公開キーと、アダプターまたは .NET Framework Data Provider のバージョンを確認するのには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-171">Complete the following steps to determine the public key and version for an adapter or the .NET Framework Data Provider.</span></span>  
  
1.  <span data-ttu-id="8ab77-172">通常、Windows ディレクトリに移動*C:\WINDOWS\assembly*です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-172">Go to the Windows directory, typically *C:\WINDOWS\assembly*.</span></span>  
  
2.  <span data-ttu-id="8ab77-173">対象の公開キーを指定してを選択し、DLL を右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-173">Right-click the DLL for which you want the public key, and then select **Properties**.</span></span> <span data-ttu-id="8ab77-174">次の表は、各アダプターおよびプロバイダーの Dll の名前を示します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-174">The following table lists the name of the DLLs for each adapter and provider:</span></span>  
  
    |<span data-ttu-id="8ab77-175">アダプターと .NET Framework データ プロバイダー</span><span class="sxs-lookup"><span data-stu-id="8ab77-175">Adapter/.NET Framework Data Provider</span></span>|<span data-ttu-id="8ab77-176">DLL の名前</span><span class="sxs-lookup"><span data-stu-id="8ab77-176">Name of the DLL</span></span>|  
    |---|---|  
    |[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]|<span data-ttu-id="8ab77-177">Microsoft.Adapters.SAP</span><span class="sxs-lookup"><span data-stu-id="8ab77-177">Microsoft.Adapters.SAP</span></span>|  
    |[!INCLUDE[adaptersiebel_short](../includes/adaptersiebel-short-md.md)]|<span data-ttu-id="8ab77-178">Microsoft.Adapters.Siebel</span><span class="sxs-lookup"><span data-stu-id="8ab77-178">Microsoft.Adapters.Siebel</span></span>|  
    |[!INCLUDE[adapteroracle_short](../includes/adapteroracle-short-md.md)]|<span data-ttu-id="8ab77-179">Microsoft.Adapters.OracleDB</span><span class="sxs-lookup"><span data-stu-id="8ab77-179">Microsoft.Adapters.OracleDB</span></span>|  
    |[!INCLUDE[adapteroraclebusinessshort](../includes/adapteroraclebusinessshort-md.md)]|<span data-ttu-id="8ab77-180">Microsoft.Adapters.OracleEBS</span><span class="sxs-lookup"><span data-stu-id="8ab77-180">Microsoft.Adapters.OracleEBS</span></span>|  
    |[!INCLUDE[adaptersqlshort](../includes/adaptersqlshort-md.md)]|<span data-ttu-id="8ab77-181">Microsoft.Adapters.Sql.dll</span><span class="sxs-lookup"><span data-stu-id="8ab77-181">Microsoft.Adapters.Sql.dll</span></span>|  
    |[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]|<span data-ttu-id="8ab77-182">Microsoft.Data.SAPClient</span><span class="sxs-lookup"><span data-stu-id="8ab77-182">Microsoft.Data.SAPClient</span></span>|  
    |[!INCLUDE[adoprovidersiebelshort](../includes/adoprovidersiebelshort-md.md)]|<span data-ttu-id="8ab77-183">Microsoft.Data.SiebelClient</span><span class="sxs-lookup"><span data-stu-id="8ab77-183">Microsoft.Data.SiebelClient</span></span>|  
  
3.  <span data-ttu-id="8ab77-184">**全般** タブで、**公開キー トークンの**値は、DLL の公開キー。</span><span class="sxs-lookup"><span data-stu-id="8ab77-184">On the **General** tab, the **Public Key Token** value is the public key for the DLL.</span></span> <span data-ttu-id="8ab77-185">**バージョン**値は、DLL のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="8ab77-185">The **Version** value is the version number for the DLL.</span></span>  
  
4.  <span data-ttu-id="8ab77-186">公開キーをコピーし、**キャンセル**です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-186">Copy the public key, and then select **Cancel**.</span></span>  
  
## <a name="install-the-custom-rfcs"></a><span data-ttu-id="8ab77-187">カスタム Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ab77-187">Install the custom RFCs</span></span>  
<span data-ttu-id="8ab77-188">のみ必須*場合*を使用する、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-188">Required only *if* you want to use the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="8ab77-189">参照してください[カスタム Rfc のインストール](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)で、[!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]ドキュメント。</span><span class="sxs-lookup"><span data-stu-id="8ab77-189">See [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md) in the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)] documentation.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="8ab77-190">提供されるカスタム Rfc の以前のバージョンを使用しているかどうか、 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]、このリリースで提供、Rfc にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8ab77-190">If you are using an earlier version of the custom RFCs provided with the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)], then you must upgrade them to the RFCs provided with this release.</span></span> <span data-ttu-id="8ab77-191">そのため、以前の Rfc を削除し、このリリースに含まれている Rfc をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ab77-191">Do this by removing the earlier RFCs, and then installing the RFCs included with this release.</span></span>  

## <a name="install-the-enterprise-applications"></a><span data-ttu-id="8ab77-192">エンタープライズ アプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8ab77-192">Install the enterprise applications</span></span>  
<span data-ttu-id="8ab77-193">手順と、別のエンタープライズの LOB システムをインストールするガイダンスは、エンタープライズ システムによって提供されるインストール ガイドを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8ab77-193">For the steps and guidance to install the different enterprise LOB systems, we recommend you use the installation guides provided by the enterprise system.</span></span> <span data-ttu-id="8ab77-194">存在する場合は、特定の構成の変更は、アダプターのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8ab77-194">Also refer to its adapter documentation for specific configuration changes, if any.</span></span>   

## <a name="installation-and-post-installation-checklist"></a><span data-ttu-id="8ab77-195">インストールおよびインストール後のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="8ab77-195">Installation and post-installation checklist</span></span>  
  
-   <span data-ttu-id="8ab77-196">すべてをインストールするかどうかを確認、[ソフトウェアの前提条件](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md)正しいインストール オプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-196">Make sure you installed all the [software prerequisites](../adapters-and-accelerators/software-prerequisites-for-biztalk-adapter-pack-2016.md) with the correct installation option.</span></span>
  
-   <span data-ttu-id="8ab77-197">サポートされている、企業の LOB アプリケーションをインストールしたコンピューターにインストールされているバージョンであることを確認してください、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-197">Make sure you have the supported version of the enterprise LOB applications installed on your computer where you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="8ab77-198">参照してください[サポートされている行の基幹業務 (LOB) システム](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-198">See [Supported Line-of-Business (LOB) systems](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-systems.aspx).</span></span>  
  
-   <span data-ttu-id="8ab77-199">LOB システム接続するエンタープライズ用のアダプターのみをインストールするには、インストールしたを確認してください、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]を使用して、**カスタム**インストール オプションです。</span><span class="sxs-lookup"><span data-stu-id="8ab77-199">To install only the adapter for the enterprise LOB system you want to connect, make sure you installed the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] using the **Custom** installation option.</span></span> <span data-ttu-id="8ab77-200">使用していないことを確認、**完了**インストール オプションです。</span><span class="sxs-lookup"><span data-stu-id="8ab77-200">Make sure you did not use the **Complete** installation option.</span></span> <span data-ttu-id="8ab77-201">参照してください[BizTalk Adapter Pack をインストールする](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md)です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-201">See [Installing the BizTalk Adapter Pack](../adapters-and-accelerators/installing-the-biztalk-adapter-pack-2016.md).</span></span>  
  
-   <span data-ttu-id="8ab77-202">SAP システムを使用して、tRFC の呼び出しを作成するかどうか、 [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)]、SQL Server データベースで、必要なテーブルを作成するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-202">If you want to make tRFC calls to the SAP system using the [!INCLUDE[adaptersap_short](../includes/adaptersap-short-md.md)], make sure you create the required tables in a SQL Server database.</span></span> <span data-ttu-id="8ab77-203">参照してください**SQL Server データベースの作成オブジェクト**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="8ab77-203">See **Create SQL Server Database objects** (in this topic).</span></span>
  
-   <span data-ttu-id="8ab77-204">実行中に、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]セットアップ ウィザードで、バインドを登録できませんでしたを示すエラー メッセージを取得可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8ab77-204">While running the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] setup wizard, you may get an error message that states the setup failed to register the bindings.</span></span> <span data-ttu-id="8ab77-205">場合は、手動で登録します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-205">If so, register them manually.</span></span> <span data-ttu-id="8ab77-206">参照してください**アダプターのバインドを登録**(」を参照)。</span><span class="sxs-lookup"><span data-stu-id="8ab77-206">See **Register the adapter bindings** (in this topic).</span></span>  
  
-   <span data-ttu-id="8ab77-207">インストールする場合、[!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)]の一部として、[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]インストール、SAP システムにカスタムの Rfc をインストールするかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="8ab77-207">If you chose to install the [!INCLUDE[adoprovidersapshort](../includes/adoprovidersapshort-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] installation, make sure you install the custom RFCs on the SAP system.</span></span> <span data-ttu-id="8ab77-208">参照してください[インストール カスタム Rfc](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="8ab77-208">See [Install Custom RFCs](../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>

## <a name="more-good-info"></a><span data-ttu-id="8ab77-209">詳細な情報</span><span class="sxs-lookup"><span data-stu-id="8ab77-209">More good info</span></span>
[<span data-ttu-id="8ab77-210">変更するか、BizTalk Adapter Pack の削除</span><span class="sxs-lookup"><span data-stu-id="8ab77-210">Change or remove the BizTalk Adapter Pack</span></span>](../adapters-and-accelerators/update-or-uninstall-the-biztalk-adapter-pack-2016.md)  
[<span data-ttu-id="8ab77-211">BizTalk Adapter Pack に関する FAQ</span><span class="sxs-lookup"><span data-stu-id="8ab77-211">BizTalk Adapter Pack FAQ</span></span>](../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)