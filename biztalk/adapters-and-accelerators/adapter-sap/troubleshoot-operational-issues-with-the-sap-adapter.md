---
title: SAP アダプターの BizTalk での運用上の問題のトラブルシューティング |Microsoft ドキュメント
description: 一般的なエラーの問題、および mySAP アダプターの BizTalk アダプター パック (BAP) と解像度
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb0f005b-7548-478b-8243-69e07c29d02c
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f98a4f7b9ed0a504c3adc245916ca9d39af7a7fe
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967512"
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a><span data-ttu-id="dd53d-103">SAP アダプターでの運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-103">Troubleshoot Operational Issues with the SAP adapter</span></span>
<span data-ttu-id="dd53d-104">このセクションで説明を使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
### <a name="enable-tracing"></a><span data-ttu-id="dd53d-105">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-105">Enable tracing</span></span>  
 <span data-ttu-id="dd53d-106">トレースのサポートについては、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[診断トレースとメッセージ ログを SAP アダプターの](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-106">For information about tracing support in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Diagnostic Tracing and Message Logging for the SAP adapter](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md).</span></span>  
  
##  <a name="client_dll"></a><span data-ttu-id="dd53d-107">バインディングの読み込みエラー</span><span class="sxs-lookup"><span data-stu-id="dd53d-107">Error loading the binding</span></span>  
 <span data-ttu-id="dd53d-108">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-108">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-109">起動しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]GUI では、次のエラー。</span><span class="sxs-lookup"><span data-stu-id="dd53d-109">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="dd53d-110">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-110">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-111">開始すると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストールされているすべてのアダプターのアダプターのバインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-111">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="dd53d-112">一方、アダプターのバインドは、エンタープライズ アプリケーション用の特定のクライアント ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-112">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="dd53d-113">次の理由の一方または両方について、この問題に直面する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-113">You might face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="dd53d-114">必要な LOB クライアント ソフトウェアは、アダプターがインストールされているコンピューターにインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-114">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="dd53d-115">含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了したとき、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-115">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="dd53d-116">ただし、1 つだけのエンタープライズ アプリケーションに LOB クライアント ライブラリをインストールする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-116">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="dd53d-117">その結果、GUI は、他のアダプターのバインドを読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-117">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="dd53d-118">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-118">**Resolution**</span></span>  
  
-   <span data-ttu-id="dd53d-119">必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd53d-119">Make sure you do a Custom installation of the adapters to install only the adapter you need.</span></span>  
  
-   <span data-ttu-id="dd53d-120">必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-120">Make sure the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="dd53d-121">[サポートされている LOB システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているバージョンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-121">[Supported LOB systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported versions.</span></span> <span data-ttu-id="dd53d-122">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]も SAP システムとのインターフェイスの特定の Dll が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-122">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] also requires certain DLLs to interface with the SAP system.</span></span> <span data-ttu-id="dd53d-123">アダプターで必要な Dll の詳細については、次を参照してください。 [SAP 用データ プロバイダーのインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-123">For more information about the DLLs required by the adapter, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <a name="BKMK_SAPDisplay"></a><span data-ttu-id="dd53d-124">SAP アダプターが BizTalk 管理コンソールではありません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-124">The SAP adapter is missing in BizTalk Administration console</span></span>  
 <span data-ttu-id="dd53d-125">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-125">**Problem**</span></span>  
  
<span data-ttu-id="dd53d-126">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]に含まれている[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-126">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] included with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="dd53d-127">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-127">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-128">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF カスタム バインドがします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-128">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="dd53d-129">そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-129">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="dd53d-130">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-130">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-131">明示的に追加することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-131">You can explicitly add the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
##  <a name="BKMK_SAPConnOpen"></a><span data-ttu-id="dd53d-132">Dll の SAP への接続を開くときにエラーがないです。</span><span class="sxs-lookup"><span data-stu-id="dd53d-132">DLLs are missing error opening a connection to SAP</span></span>  
 <span data-ttu-id="dd53d-133">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-133">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-134">使用して SAP システムへの接続を開くしようとすると、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、いくつかの Dll が欠落していることを通知 ダイアログ ボックスは、SAP システムに表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-134">When you try to open a connection to the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], a dialog box appears in the SAP system, informing that some DLLs are missing.</span></span>  
  
 <span data-ttu-id="dd53d-135">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-135">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-136">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Librfc32u.dll を使用して SAP システムとの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-136">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses librfc32u.dll to establish a connection with the SAP system.</span></span> <span data-ttu-id="dd53d-137">さらに、librfc32u.dll には、関数への Dll のセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-137">The librfc32u.dll, in turn, requires a set of DLLs to function.</span></span> <span data-ttu-id="dd53d-138">これらの Dll のサポートが、コンピューター上のパス変数に追加されていない場合、このエラーを取得する場所、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="dd53d-138">You get this error if these supporting DLLs are not added to the PATH variable on the computer where the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is installed.</span></span>  
  
 <span data-ttu-id="dd53d-139">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-139">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-140">解決策としては、表を参照してください、[アダプターのバインドを読み込み中にエラー](#client_dll)問題です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-140">Refer to the table provided as a resolution to the [Error in loading the adapter bindings](#client_dll) issue.</span></span> <span data-ttu-id="dd53d-141">表は、サポートされる SAP システムを使用するとのやり取りに必要な Dll、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-141">The table lists the supporting DLLs required to interface with the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <a name="BKMK_SAPXmlRetrieve"></a><span data-ttu-id="dd53d-142">65,536 個を超えるノードを持つ XML を取得中にエラー</span><span class="sxs-lookup"><span data-stu-id="dd53d-142">Error retrieving XML with more than 65,536 nodes</span></span>  
 <span data-ttu-id="dd53d-143">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-143">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-144">アダプターは、65,536 個を超えるノードを持つ XML 出力を取得中に、次のエラーを説明します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-144">The adapter gives the following error while retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="dd53d-145">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-145">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-146">アダプターは、シリアル化して、65,536 個を超える項目を含むオブジェクトを逆シリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-146">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="dd53d-147">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-147">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-148">この問題を解決するには、設定、`maxItemsInObjectGraph`次の 2 つの方法のいずれかのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="dd53d-148">You can fix this issue by setting the `maxItemsInObjectGraph` parameter in either of the following two ways:</span></span>  
  
-   <span data-ttu-id="dd53d-149">このパラメーターを変更することによって設定、`maxItemsInObjectGraph`内のパラメーター、`ServiceBehavior`サービス クラスの属性です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-149">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
-   <span data-ttu-id="dd53d-150">次のアプリケーションの app.config ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-150">Add the following to your application's app.config file.</span></span>  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 <span data-ttu-id="dd53d-151">サンプルの app.config は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-151">A sample app.config will look like the following.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
         <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <client>  
      <endpoint   behaviorConfiguration="NewBehavior" binding="sapBinding"  
       contract="IOutboundContract" name="sap_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
##  <a name="BKMK_SAPConnURI"></a><span data-ttu-id="dd53d-152">BizTalk Server で WCF カスタム ポートの接続 URI を入力するエラー</span><span class="sxs-lookup"><span data-stu-id="dd53d-152">Error entering a connection URI for a WCF-Custom port in BizTalk Server</span></span>  
 <span data-ttu-id="dd53d-153">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-153">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="dd53d-154">接続の SAP システムへの接続に URI を指定する場合は、次のエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-154"> gives the following error when you specify a connection URI to connect to the SAP system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="dd53d-155">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-155">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-156">接続 URI は、標準のエンコード形式には従っていません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-156">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="dd53d-157">たとえば、パラメーターの値にスペースを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-157">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="dd53d-158">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-158">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-159">接続を指定する URI は、標準のエンコード形式に準拠して確認します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-159">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="dd53d-160">たとえば、"%20"空白を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-160">For example, a blank space must be replaced by "%20".</span></span>  
  
##  <a name="BKMK_SAPOperate"></a><span data-ttu-id="dd53d-161">SAP に対する操作の完了中にエラーが System.ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="dd53d-161">System.ArgumentNullException error while completing an operation on SAP</span></span>  
 <span data-ttu-id="dd53d-162">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-162">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-163">SAP システムを使用して、任意の操作を実行するときに、アダプターは、次のエラーを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-163">The adapter gives the following error when performing any operation on the SAP system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 <span data-ttu-id="dd53d-164">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-164">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-165">メッセージの WCF アクションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="dd53d-166">WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="dd53d-167">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-167">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-168">送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="dd53d-169">手順については、次を参照してください。 [SAP システムの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-169">For instructions, see [Configure the SOAP action for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md).</span></span> <span data-ttu-id="dd53d-170">参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)各操作のアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-170">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) to see a list of actions for each operation.</span></span>  
  
##  <a name="BKMK_SAPXmlParsing"></a><span data-ttu-id="dd53d-171">指定されたアクション名が正しくない操作 XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="dd53d-171">XmlReaderParsingException due to incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="dd53d-172">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-172">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-173">BizTalk Server 管理コンソールは、SAP システムにメッセージを送信するときに、次のエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-173">The BizTalk Server Administration Console gives the following error when sending messages to an SAP system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="dd53d-174">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-174">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-175">によって作成されたポートのバインド ファイルをインポートすることによって、WCF カスタム ポートを構成する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートのアクションは、次の形式で指定されます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="dd53d-176">上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-176">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="dd53d-177">RFC_CUSTOMER_GET に対してスキーマを生成する場合など、アクションで操作名では、"RFC_CUSTOMER_GET"になります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-177">For example, if you generated schema for RFC_CUSTOMER_GET, the operation name in the action will be "RFC_CUSTOMER_GET".</span></span> <span data-ttu-id="dd53d-178">ただし、論理ポートにある操作名で BizTalk オーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="dd53d-179">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-179">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-180">確認操作名の両方、論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) (BizTalk Server 管理コンソール) での物理ポートは同じです。</span><span class="sxs-lookup"><span data-stu-id="dd53d-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
##  <a name="BKMK_SAPHundredCons"></a><span data-ttu-id="dd53d-181">SAP に 100 を超える接続を開くときのエラー</span><span class="sxs-lookup"><span data-stu-id="dd53d-181">Error opening more than 100 connections to SAP</span></span>  
 <span data-ttu-id="dd53d-182">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-182">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-183">アダプターは、SAP システムに 100 を超える接続を開く際に、次の例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-183">The adapter throws the following exception when opening more than 100 connections to the SAP system.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 <span data-ttu-id="dd53d-184">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-184">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-185">既定では、SAP は、システムに 100 を超える接続を有効にできません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-185">By default, SAP does not enable more than 100 connections into the system.</span></span>  
  
 <span data-ttu-id="dd53d-186">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-186">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-187">接続の最大数を増やすには、SAP クライアント ライブラリがインストールされ、値を数値に設定をあるコンピューター上で環境変数を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-187">To increase the maximum number of connections, you must create an environment variable on the computer that has the SAP client libraries installed and set it to a numeric value.</span></span> <span data-ttu-id="dd53d-188">この環境変数に指定した値は、SAP システムに変更できる接続の最大数です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-188">The value you specify for this environment variable is the maximum number of connections that can be made into the SAP system.</span></span> <span data-ttu-id="dd53d-189">次の内容で、環境変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-189">Create the environment variable with the following details:</span></span>  
  
-   <span data-ttu-id="dd53d-190">**変数名**: CPIC_MAX_CONV</span><span class="sxs-lookup"><span data-stu-id="dd53d-190">**Variable name**: CPIC_MAX_CONV</span></span>  
  
-   <span data-ttu-id="dd53d-191">**変数値**: 任意の正の数値。</span><span class="sxs-lookup"><span data-stu-id="dd53d-191">**Variable value**: any positive numeric value.</span></span> <span data-ttu-id="dd53d-192">たとえば、SAP システムに 200 の接続を有効にするには、200 として値を指定します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-192">For example, to enable 200 connections into the SAP system, specify the value as 200.</span></span>  
  
 <span data-ttu-id="dd53d-193">環境変数を作成する方法の詳細については、次を参照してください。「How To Windows 2000 でのシステム変数の作成」で[http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020)です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-193">For instructions on creating an environment variable, see "How To Create System Variables in Windows 2000" at [http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020).</span></span>  
  
##  <a name="BKMK_SAPIDOCMetadata"></a><span data-ttu-id="dd53d-194">エラーを生成するか、Idoc のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-194">Error generating or retrieving metadata for IDOCs</span></span>  
 <span data-ttu-id="dd53d-195">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-195">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-196">メタデータを生成するときに、**受信**、IDOC を SAP システムでの操作、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]というエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-196">While generating metadata for the **Receive** operation for an IDOC in an SAP system, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives the following error.</span></span>  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 <span data-ttu-id="dd53d-197">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-197">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-198">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOCTYPE_READ_COMPLETE RFC を使用してのメタデータを取得する、**受信**IDOC に対する操作です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-198">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the IDOCTYPE_READ_COMPLETE RFC to retrieve the metadata for the **Receive** operation for an IDOC.</span></span> <span data-ttu-id="dd53d-199">この RFC を呼び出すと、SAP システムで特定のユーザー権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-199">Invoking this RFC requires specific user permissions in the SAP system.</span></span> <span data-ttu-id="dd53d-200">メタデータを生成する、IDOCTYPE_READ_COMPLETE RFC を呼び出すためのアクセス許可がない資格情報を使用して SAP システムに接続している場合、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="dd53d-200">To generate metadata, if you have connected to the SAP system using a credential that does not have permission to invoke the IDOCTYPE_READ_COMPLETE RFC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an error.</span></span>  
  
 <span data-ttu-id="dd53d-201">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-201">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-202">アダプターを使用した同じ資格情報を使用して、SAP GUI にログインします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-202">Log in to the SAP GUI using the same credentials you had used for the adapter.</span></span> <span data-ttu-id="dd53d-203">トランザクション SE37 に移動し、IDOCTYPE_READ_COMPLETE として実行するには、RFC の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-203">Navigate to transaction SE37, and enter the name of the RFC to execute as IDOCTYPE_READ_COMPLETE.</span></span>  
  
 <span data-ttu-id="dd53d-204">入力パラメーター PI_IDOCTYP PI_CIMTYP、カスタム IDoc に対応する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-204">For the input parameters PI_IDOCTYP and PI_CIMTYP, enter the values corresponding to the custom IDoc.</span></span> <span data-ttu-id="dd53d-205">パラメーター PI_VERSION および PI_RELEASE、アダプター メタデータの UI で選択されていると同じ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-205">For the parameters PI_VERSION and PI_RELEASE, enter the same values as being chosen in the Adapter Metadata UI.</span></span> <span data-ttu-id="dd53d-206">実行に f8 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-206">And, press F8 to execute.</span></span>  
  
 <span data-ttu-id="dd53d-207">どのようなアダプターを受け取ると、問題に関する詳細な情報として、同じ例外を取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-207">You should get the same exception as what the adapter receives, with more information about the issue.</span></span>  
  
 <span data-ttu-id="dd53d-208">それでも問題を解決できない場合は、スキーマを生成、 **ReceiveIdoc**操作の代わりに、**受信**操作します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-208">If you are still not able to resolve the issue, generate a schema for the **ReceiveIdoc** operation instead of the **Receive** operation.</span></span> <span data-ttu-id="dd53d-209">ここでは、SAP アダプターは IDOCTYPE_READ_COMPLETE を使用しないと、エラーをスローしません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-209">In this case, the SAP adapter does not use IDOCTYPE_READ_COMPLETE, and does not throw any error.</span></span>  
  
##  <a name="BKMK_SAPIDOCReceive"></a><span data-ttu-id="dd53d-210">エラーの送信または受信するが解放されていないセグメントの Idoc</span><span class="sxs-lookup"><span data-stu-id="dd53d-210">Error sending or receiving IDOCs that have unreleased segments</span></span>  
 <span data-ttu-id="dd53d-211">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-211">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-212">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Idoc の送信中に、XmlReaderParsingException を示します (を使用して**送信**操作) Idoc を受信または (を使用して**受信**操作) が解放されていないセグメント。</span><span class="sxs-lookup"><span data-stu-id="dd53d-212">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException while sending IDOCs (using **Send** operation) or receiving IDOCs (using **Receive** operation) that have unreleased segments.</span></span>  
  
 <span data-ttu-id="dd53d-213">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-213">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-214">Idoc はセグメントの角形で構成します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-214">IDOCs are constituted of segments.</span></span> <span data-ttu-id="dd53d-215">メタデータの生成中に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムに存在するすべてのリリースのセグメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-215">While generating metadata, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] retrieves all the released segments that are present in the SAP system.</span></span> <span data-ttu-id="dd53d-216">ただし、ときに、アダプターのクライアントはメタデータを使用、IDOC の受信などの操作を実行する、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] XmlReaderParsingException を提供します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-216">However, when the adapter client uses the metadata to perform an operation such as receiving an IDOC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException.</span></span> <span data-ttu-id="dd53d-217">これは、IDOC を受信すると、SAP システムが送信されることがいくつか解放されていないセグメント同様に、対象のメタデータは、アダプターによって生成されなかったために発生します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-217">This occurs because when the IDOC is received, the SAP system might have sent some unreleased segments as well, the metadata for which was not generated by the adapter.</span></span>  
  
 <span data-ttu-id="dd53d-218">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-218">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-219">次のいずれかを行います。</span><span class="sxs-lookup"><span data-stu-id="dd53d-219">Do any of the following:</span></span>  
  
-   <span data-ttu-id="dd53d-220">解放されていないセグメントの適切な修正プログラムを適用することで、SAP システムをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-220">Upgrade your SAP system by applying appropriate patches for the unreleased segments.</span></span>  
  
-   <span data-ttu-id="dd53d-221">使用して**SendIdoc**または**ReceiveIdoc**操作を送信し、それぞれの Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-221">Use **SendIdoc** or **ReceiveIdoc** operations to send and receive IDOCs respectively.</span></span> <span data-ttu-id="dd53d-222">これらの操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-222">For more information about these operations, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <a name="BKMK_SAPIDOCSend"></a><span data-ttu-id="dd53d-223">フラット ファイル Idoc を SAP FilePort で受信した SAP に送信中にエラー</span><span class="sxs-lookup"><span data-stu-id="dd53d-223">Error sending flat-file IDOCs to SAP that were received using the SAP FilePort</span></span>  
 <span data-ttu-id="dd53d-224">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-224">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-225">送信しようとする場合 (を使用して**送信**操作) flatf ファイルを失敗したため、XML 形式に変換するフラット ファイル IDOC を SAP FilePort を使用して生成された SAP システムには、BizTalk オーケストレーションで、フラット ファイル パーサーは失敗しますIDOD**送信**操作します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-225">If you try to send (using **Send** operation) a flat-file IDOC to an SAP system that was generated using an SAP FilePort, the flat-file parser in the BizTalk orchestration fails to convert the flatf-file to an XML format, thereby failing the IDOD **Send** operation.</span></span>  
  
 <span data-ttu-id="dd53d-226">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-226">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-227">SAP システムは、FilePort を使用して、IDOC を生成するとき、セグメントの末尾のすべての空白をトリムします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-227">When the SAP system generates an IDOC using a FilePort, it trims off all the empty spaces at the end of a segment.</span></span> <span data-ttu-id="dd53d-228">ただし、フラット ファイル パーサーでは、XML にフラット ファイルを正常に変換するには、存在するセグメントの最後のフィールドのデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-228">However, the flat-file parser expects the data of the last field in the segment to be present to successfully convert the flat-file to XML.</span></span> <span data-ttu-id="dd53d-229">空のスペースは、セグメント内に存在できないため、XML にフラット ファイルの解析をフラット ファイル パーサーは失敗します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-229">Because the empty spaces are not present in the segment, the flat-file parser fails to parse the flat-file to XML.</span></span>  
  
 <span data-ttu-id="dd53d-230">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-230">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-231">フラット ファイル Idoc が SAP FilePort を使用して生成されたこのような使用、 **SendIdoc**操作代わりにします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-231">For such flat-file IDOCs generated using the SAP FilePort, use the **SendIdoc** operation instead.</span></span> <span data-ttu-id="dd53d-232">この操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-232">For more information about this operation, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <a name="BKMK_SAPRecIDOCCompat"></a><span data-ttu-id="dd53d-233">EnableBizTalkCompatibilityMode プロパティが設定されている場合、SAP からの Idoc を受信中にエラーを true に</span><span class="sxs-lookup"><span data-stu-id="dd53d-233">Error receiving IDOCs from SAP if EnableBizTalkCompatibilityMode property is set to true</span></span>  
 <span data-ttu-id="dd53d-234">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-234">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-235">IDOC を受信中に、次の例外が発生した、 **EnableBizTalkCompatibilityMode**プロパティ セットを true にバインドします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-235">The following exception is encountered while receiving an IDOC with the **EnableBizTalkCompatibilityMode** binding property set to true:</span></span>  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 <span data-ttu-id="dd53d-236">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-236">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-237">場合、バインディング プロパティ**EnableBizTalkCompatibilityMode**に設定されている**true**、BizTalk プロパティ スキーマ DLL を追加する必要がありますの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、つまり、BizTalk アプリケーションにリソースとして、プロジェクトを配置するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="dd53d-237">If the binding property **EnableBizTalkCompatibilityMode** is set to **true**, you must add the BizTalk property schema DLL for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a resource in your BizTalk application, that is, the application in which your project is deployed.</span></span>  
  
 <span data-ttu-id="dd53d-238">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-238">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-239">BizTalk プロパティ スキーマの名前、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-239">The name for the BizTalk property schema for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*.</span></span> <span data-ttu-id="dd53d-240">これには、インストールによって、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]下にあるセットアップ\<インストール ドライブ\>: \プログラム \microsoft BizTalk アダプター Pack\bin です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-240">This is installed by the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup under \<installation drive\>:\ Program Files\Microsoft BizTalk Adapter Pack\bin.</span></span> <span data-ttu-id="dd53d-241">このアセンブリを BizTalk アプリケーションにリソースとして追加する、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-241">Perform the following tasks to add this assembly as a resource in your BizTalk application.</span></span>  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a><span data-ttu-id="dd53d-242">BizTalk アプリケーションにリソースとしてアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-242">Add an assembly as a resource in BizTalk application</span></span>  
  
1.  <span data-ttu-id="dd53d-243">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。</span><span class="sxs-lookup"><span data-stu-id="dd53d-243">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="dd53d-244">コンソール ツリーで  **BizTalk グループ**、展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーション、します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-244">In the console tree, expand **BizTalk Group**, expand **Applications**, and then the application to which you want to add a BizTalk assembly.</span></span>  
  
3.  <span data-ttu-id="dd53d-245">展開**アプリケーション**および BizTalk アセンブリを追加するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="dd53d-245">Expand **Applications** and the application to which you want to add a BizTalk assembly.</span></span>  
  
4.  <span data-ttu-id="dd53d-246">右クリック**リソース**、 をポイント**追加**、クリックして**BizTalk アセンブリ**です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-246">Right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
5.  <span data-ttu-id="dd53d-247">をクリックして**追加**は、BizTalk アセンブリ ファイルを含むフォルダーに移動し、BizTalk アセンブリ ファイルを選択し、をクリックして**開く**です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-247">Click **Add**, navigate to the folder containing the BizTalk assembly file, select the BizTalk assembly file, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="dd53d-248">**オプション**、GAC に BizTalk アセンブリをインストールするためのオプションを指定し、クリックして**OK**です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-248">In **Options**, specify the options for installing the BizTalk assembly to the GAC, and then click **OK**.</span></span>  
  
##  <a name="BKMK_SAPIDOCValidate"></a><span data-ttu-id="dd53d-249">SAP システムから Idoc を受信中に検証のエラー</span><span class="sxs-lookup"><span data-stu-id="dd53d-249">Error in validation while receiving IDOCs from an SAP system</span></span>  
 <span data-ttu-id="dd53d-250">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-250">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-251">SAP システムから受信した IDOC には、次のようなエラーで検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-251">An IDOC received from an SAP system fails validation with an error similar to the following:</span></span>  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 <span data-ttu-id="dd53d-252">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-252">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-253">IDOC を受信するために生成されるメタデータには、受信操作の一部として特定の列用に受信することが許可される値が含まれます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-253">The metadata generated for receiving an IDOC contains the permissible values that can be received for a particular column as part of the receive operation.</span></span> <span data-ttu-id="dd53d-254">これらの値は、生成されたメタデータ内の列挙型として公開されます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-254">These values are exposed as enumeration in the generated metadata.</span></span> <span data-ttu-id="dd53d-255">ただし、IDOC が実際に受信されると、受信した値は、列挙値を異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-255">However, when the IDOC is actually received, the value received could be different from the enumerated values.</span></span> <span data-ttu-id="dd53d-256">そのため、受信操作は、値の検証中に失敗します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-256">Hence the receive operation fails while validating the values.</span></span> <span data-ttu-id="dd53d-257">たとえば、上記のエラーでは、TAXBS 列にメッセージの検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-257">For example, in the above error message validation fails for the TAXBS column.</span></span>  
  
 <span data-ttu-id="dd53d-258">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-258">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-259">必要があります手動で編集する schema (BizTalk プロジェクトの場合) またはクライアント プロキシ内の列挙型 (.NET プロジェクトの WCF を使用してサービス モデル) の SAP システムから受信した値を含めます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-259">You must manually edit the enumeration in schema (for BizTalk projects) or the client proxy (for .NET projects using WCF service model) to include the value received from the SAP system.</span></span>  
  
##  <a name="BKMK_SAPFFIDOC"></a><span data-ttu-id="dd53d-260">フラット ファイル Idoc 前に、と後、XML への変換が一致しません</span><span class="sxs-lookup"><span data-stu-id="dd53d-260">Flat-file IDOCs, before and after converting to XML, are not identical</span></span>  
 <span data-ttu-id="dd53d-261">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-261">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-262">フラット ファイル IDOC をスキーマを使用して XML に変換し、スキーマを使用して、パイプライン経由のフラット ファイル IDOC を XML に変換し、フラット ファイル パーサーを使用する場合は 2 つのフラット ファイル Idoc が一致しません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-262">If you use a flat file parser to convert a flat-file IDOC to an XML using the schema, and then convert the XML back to a flat-file IDOC through a pipeline using the schema, the two flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="dd53d-263">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-263">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-264">XML フラット ファイル IDOC からを生成するときに、フラット ファイル パーサーは空白の値を持つ XML ノードを生成しません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-264">When generating the XML from a flat-file IDOC, the flat file parser does not generate the XML nodes with blank values.</span></span> <span data-ttu-id="dd53d-265">この XML は、フラット ファイルに変換するときに、XML に表示されないノードは、フラット ファイル IDOC に反映されません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-265">When this XML is converted back to a flat-file, the nodes missing from the XML are not reflected in the flat-file IDOC.</span></span> <span data-ttu-id="dd53d-266">そのため、フラット ファイル Idoc が一致しません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-266">Hence the flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="dd53d-267">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-267">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-268">XML と、「送信」または「受信」のノード定義内で、その逆に、フラット ファイルを変換するために使用するスキーマでは、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dd53d-268">In the schema used to convert the flat-file to XML and vice-versa, within the "Send" or "Receive" node definition, do the following:</span></span>  
  
1.  <span data-ttu-id="dd53d-269">設定、 **suppress_empty_nodes**プロパティを**false**設定と、 **generate_empty_nodes**プロパティを**true**です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-269">Set the **suppress_empty_nodes** property to **false** and set the **generate_empty_nodes** property to **true**.</span></span> <span data-ttu-id="dd53d-270">既定では、 **suppress_empty_nodes**プロパティに設定されている**true**と**generate_empty_nodes**プロパティに設定されている**false**、およびそのため空のすべてのノードは、XML には反映されません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-270">By default, the **suppress_empty_nodes** property is set to **true** and the **generate_empty_nodes** property is set to **false**, and hence all empty nodes are not reflected in the XML.</span></span>  
  
2.  <span data-ttu-id="dd53d-271">フラット ファイルには、末尾に余分な改行を含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-271">The flat-file may contain an extra carriage return at the end.</span></span> <span data-ttu-id="dd53d-272">設定することができます、 **suppress_trailing_delimiters**プロパティを**はい**この余分なキャリッジ リターンを回避します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-272">You can set the **suppress_trailing_delimiters** property to **Yes** to avoid this extra carriage return.</span></span> <span data-ttu-id="dd53d-273">このプロパティも公開、**末尾の区切り記号の抑制**プロパティ内のスキーマを開く場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-273">This property is also exposed as the **Suppress Trailing Delimiters** property if you open the schema in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
##  <a name="BKMK_SAPAction"></a><span data-ttu-id="dd53d-274">バインド ファイルと共に作成する物理ポートを使用して、誤った操作エラー</span><span class="sxs-lookup"><span data-stu-id="dd53d-274">Incorrect Action error using a physical port creating with a binding file</span></span>  
 <span data-ttu-id="dd53d-275">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-275">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-276">使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SAP システムで特定の操作のスキーマを生成するには、アドインでもポート バインド ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-276">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the SAP system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="dd53d-277">インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server での物理ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-277">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="dd53d-278">ただし、このようなポートを使用して SAP システムにメッセージを送信するときに、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-278">However, when you send messages to the SAP system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="dd53d-279">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-279">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-280">BizTalk オーケストレーションの論理ポートを作成するときにそれらのポートでの操作の特定の名前を指定するか、Operation_1、Operation_2 などのように既定の名前に使用します。ただし、によって生成されたバインド ファイルでは、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する操作の名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="dd53d-280">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="dd53d-281">たとえば、RFC_CUSTOMER_GET のメタデータを生成する場合、次に、アクションは設定されます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-281">For example, if you generate metadata for RFC_CUSTOMER_GET, the action will be set to the following:</span></span>  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 <span data-ttu-id="dd53d-282">バインド ファイルをインポートするときに、同じアクションは物理ポートに設定されます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-282">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="dd53d-283">そのため、論理ポート ([operation_1]、Operation_2 など) での操作名では、エラーが発生しましたの物理ポートのアクションで指定した操作名が一致しません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-283">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="dd53d-284">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-284">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-285">論理ポートにある操作名は、物理ポートにアクションの一部として指定された操作名と同じことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="dd53d-285">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="dd53d-286">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="dd53d-286">Do one of the following:</span></span>  
  
-   <span data-ttu-id="dd53d-287">たとえば RFC_CUSTOMER_GET、メタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートにある操作名を変更します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-287">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example RFC_CUSTOMER_GET.</span></span>  
  
-   <span data-ttu-id="dd53d-288">論理ポートでの操作名には、物理ポートのアクションで、操作名を変更します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-288">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="dd53d-289">たとえば、次のように物理ポートにアクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-289">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <a name="BKMK_SAPTableParams"></a><span data-ttu-id="dd53d-290">応答メッセージ SAP 上で実行された操作を含まないテーブル パラメーター</span><span class="sxs-lookup"><span data-stu-id="dd53d-290">The response message for an operation ran on SAP does not contain any table parameters</span></span>  
 <span data-ttu-id="dd53d-291">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-291">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-292">使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムに対して操作を実行する多数のテーブルを返すし、各テーブルには、するための SAP システムからの応答メッセージの一部として返されるデータセットが大きいレコードの数が多い。</span><span class="sxs-lookup"><span data-stu-id="dd53d-292">If you use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to execute an operation on the SAP system that returns a large number of tables, and each table has a large number of records, that will amount to a large dataset being returned as part of the response message from the SAP system.</span></span> <span data-ttu-id="dd53d-293">既定では、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]応答メッセージの一部として、テーブル パラメーターは返しません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-293">So, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not return any table parameters as part of the response message.</span></span>  
  
 <span data-ttu-id="dd53d-294">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-294">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-295">追加するテーブルを要求する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]応答の一部として返すためにします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-295">You can request the tables that you want [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to return as part of the response.</span></span> <span data-ttu-id="dd53d-296">SAP システムに送信する要求メッセージの一部として、空のテーブルのパラメーターを提供することによって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-296">You can do so by providing an empty table parameter as part of the request message that you send to the SAP system.</span></span> <span data-ttu-id="dd53d-297">たとえば、 `<table_parameter_name />`のようにします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-297">For example, `<table_parameter_name />`.</span></span>  
  
##  <a name="BKMK_SAPIncorrectCreds"></a><span data-ttu-id="dd53d-298">アダプターのクライアントが SAP からの応答を受信しません</span><span class="sxs-lookup"><span data-stu-id="dd53d-298">Adapter Clients do not receive the response from SAP</span></span>
 <span data-ttu-id="dd53d-299">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-299">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-300">アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、WCF カスタムの資格情報の送信ポートが正しくない要求メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-300">When using the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="dd53d-301">正しい資格情報を指定すると後、メッセージは、SAP システムに送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-301">After you specify the correct credentials, the message is sent to the SAP system and a response is received.</span></span> <span data-ttu-id="dd53d-302">ただし、応答メッセージでは、出力ポートを使用できません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-302">However, the response message is not available to the out port.</span></span>  
  
 <span data-ttu-id="dd53d-303">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-303">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-304">BizTalk ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-304">Restart the BizTalk host instance.</span></span>  
  
##  <a name="BKMK_SAPInboundConn"></a><span data-ttu-id="dd53d-305">SAP サーバーから受信メッセージを受信接続の問題</span><span class="sxs-lookup"><span data-stu-id="dd53d-305">Connectivity issues receiving an inbound message from the SAP server</span></span>  
 <span data-ttu-id="dd53d-306">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-306">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-307">WCF カスタムを使用して、SAP サーバーからの受信メッセージの受信ポートの受信中にのみ、次のエラーを取得する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-307">You get the following error only while receiving an inbound message from the SAP server using a WCF-Custom receive port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 <span data-ttu-id="dd53d-308">ただしは、正常に Wcf-custom を使用して、SAP システムへのメッセージの送信ポートを送信できます。</span><span class="sxs-lookup"><span data-stu-id="dd53d-308">However, you are successfully able to send messages to the SAP system using a WCF-Custom send port.</span></span>  
  
 <span data-ttu-id="dd53d-309">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-309">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-310">SAP GUI、同じコンピューターにインストール場所、アダプターのクライアントを実行しているし、受信メッセージの受信をもう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="dd53d-310">Install the SAP GUI on the same computer where you are running the adapter client and try receiving the inbound message again.</span></span> <span data-ttu-id="dd53d-311">SAP の GUI をインストールする方法の詳細については、SAP のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd53d-311">For more information about how to install the SAP GUI, refer to SAP documentation.</span></span>  
  
##  <a name="BKMK_SAPRootNode"></a><span data-ttu-id="dd53d-312">RootNode TypeName BizTalk プロジェクト内のエラー</span><span class="sxs-lookup"><span data-stu-id="dd53d-312">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="dd53d-313">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-313">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-314">BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:</span><span class="sxs-lookup"><span data-stu-id="dd53d-314">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="dd53d-315">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-315">**Resolution**</span></span>  
  
1.  <span data-ttu-id="dd53d-316">クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-316">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="dd53d-317">**RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-317">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
##  <a name="BKMK_SAPVS2008"></a><span data-ttu-id="dd53d-318">Visual Studio でのアダプターの使用時の無効なバインドの警告</span><span class="sxs-lookup"><span data-stu-id="dd53d-318">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="dd53d-319">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-319">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-320">Visual Studio でアプリケーションを作成するアダプターを使用して、アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dd53d-320">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="dd53d-321">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-321">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-322">この警告が表示されます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド、`sapBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="dd53d-322">This warning appears because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding, `sapBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="dd53d-323">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-323">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-324">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="dd53d-324">You can safely ignore this warning.</span></span>  
  
##  <a name="BKMK_SAPSimilarSchema"></a><span data-ttu-id="dd53d-325">BizTalk Server での XLANG 例外</span><span class="sxs-lookup"><span data-stu-id="dd53d-325">XLANG exception in BizTalk Server</span></span>
 <span data-ttu-id="dd53d-326">**問題**</span><span class="sxs-lookup"><span data-stu-id="dd53d-326">**Problem**</span></span>  
  
 <span data-ttu-id="dd53d-327">BizTalk Server は、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-327">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="dd53d-328">**原因**</span><span class="sxs-lookup"><span data-stu-id="dd53d-328">**Cause**</span></span>  
  
 <span data-ttu-id="dd53d-329">これは、次のいずれかのため発生します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-329">This happens because of either of the following:</span></span>  
  
-   <span data-ttu-id="dd53d-330">1 つ以上を生成する (SendIdoc ReceiveIdoc など)、BizTalk Server プロジェクト内の汎用的な操作のスキーマは、BizTalk Server アプリケーションに展開し、SAP システム上のそれぞれの操作を実行するアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-330">You have generated more than one schema of a generic operation (such as SendIdoc and ReceiveIdoc) in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to perform respective operations on an SAP system.</span></span> <span data-ttu-id="dd53d-331">競合が、スキーマは、一般的なであるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。</span><span class="sxs-lookup"><span data-stu-id="dd53d-331">Because the schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
-   <span data-ttu-id="dd53d-332">複数のプロジェクトが発生した場合の各 BizTalk Server プロジェクトの一般的な操作のスキーマを生成を同じ BizTalk Server アプリケーションをホストして、実行、アプリケーションまたはアプリケーションを実行するそれぞれの個別の各プロジェクトの配置SAP システムに対する操作。</span><span class="sxs-lookup"><span data-stu-id="dd53d-332">In case of multiple projects, you have generated a generic operation schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to perform respective operations on an SAP system.</span></span> <span data-ttu-id="dd53d-333">スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるため競合があるさまざまな BizTalk Server アプリケーションおよびアセンブリの下でデプロイされる共通のスキーマ間でします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-333">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
 <span data-ttu-id="dd53d-334">**解決策**</span><span class="sxs-lookup"><span data-stu-id="dd53d-334">**Resolution**</span></span>  
  
 <span data-ttu-id="dd53d-335">BizTalk Server アプリケーションの 1 つの一般的な操作のスキーマ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-335">Use a single generic operation schema file for a BizTalk Server application.</span></span> <span data-ttu-id="dd53d-336">同じホスト上の複数の BizTalk Server アプリケーションで一般的な操作のスキーマを使用する必要がある場合、1 つの汎用操作スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションから汎用の操作のスキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="dd53d-336">If you need to use a generic operation schema in multiple BizTalk Server applications on the same host, create an application containing a single generic operation schema, and then use the generic operation schema from all other applications in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd53d-337">参照</span><span class="sxs-lookup"><span data-stu-id="dd53d-337">See Also</span></span>  
[<span data-ttu-id="dd53d-338">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="dd53d-338">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)