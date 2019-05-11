---
title: SAP アダプターの BizTalk で運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的なエラー、問題、および BizTalk アダプター パック (BAP) での mySAP アダプターを使用した解決策
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
ms.openlocfilehash: 5c9888127e93b381f9148d995adb90e5706b07a6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372420"
---
# <a name="troubleshoot-operational-issues-with-the-sap-adapter"></a><span data-ttu-id="013f9-103">SAP アダプターを使用した運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="013f9-103">Troubleshoot Operational Issues with the SAP adapter</span></span>
<span data-ttu-id="013f9-104">このセクションを使用する場合に発生する可能性のある操作のエラーを解決するのには、トラブルシューティングの手法を使用して説明します[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-104">This section discusses using troubleshooting techniques to resolve operational errors that you might encounter when using [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
### <a name="enable-tracing"></a><span data-ttu-id="013f9-105">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="013f9-105">Enable tracing</span></span>  
 <span data-ttu-id="013f9-106">トレースのサポートについては、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[診断トレースとメッセージ ログを SAP アダプターの](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="013f9-106">For information about tracing support in the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Diagnostic Tracing and Message Logging for the SAP adapter](../../adapters-and-accelerators/adapter-sap/diagnostic-tracing-and-message-logging-for-the-sap-adapter.md).</span></span>  
  
##  <a name="client_dll"></a> <span data-ttu-id="013f9-107">バインディングの読み込みエラー</span><span class="sxs-lookup"><span data-stu-id="013f9-107">Error loading the binding</span></span>  
 <span data-ttu-id="013f9-108">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-108">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-109">開始しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]GUI では、次のエラー。</span><span class="sxs-lookup"><span data-stu-id="013f9-109">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="013f9-110">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-110">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-111">開始すると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]インストールされているすべてのアダプターのアダプターのバインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="013f9-111">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="013f9-112">さらに、アダプターのバインドは、エンタープライズ アプリケーションの特定のクライアント ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="013f9-112">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="013f9-113">この問題は次の理由の両方またはいずれかに直面する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="013f9-113">You might face this issue for one or both of the following reasons:</span></span>  
  
- <span data-ttu-id="013f9-114">アダプターがインストールされているコンピューターでは、必要な LOB クライアント ソフトウェアがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="013f9-114">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
- <span data-ttu-id="013f9-115">含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了した、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-115">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="013f9-116">ただし、1 つだけのエンタープライズ アプリケーション用に LOB クライアント ライブラリをインストールする場合があります。</span><span class="sxs-lookup"><span data-stu-id="013f9-116">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="013f9-117">その結果、GUI の他のアダプターのバインドの読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="013f9-117">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
  <span data-ttu-id="013f9-118">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-118">**Resolution**</span></span>  
  
- <span data-ttu-id="013f9-119">必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="013f9-119">Make sure you do a Custom installation of the adapters to install only the adapter you need.</span></span>  
  
- <span data-ttu-id="013f9-120">必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされているかどうかを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-120">Make sure the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="013f9-121">[サポートされている LOB システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているバージョンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="013f9-121">[Supported LOB systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported versions.</span></span> <span data-ttu-id="013f9-122">[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]も、SAP システムとのインターフェイスの特定の Dll が必要です。</span><span class="sxs-lookup"><span data-stu-id="013f9-122">The [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] also requires certain DLLs to interface with the SAP system.</span></span> <span data-ttu-id="013f9-123">アダプターに必要な Dll の詳細については、次を参照してください。 [Data Provider for SAP のインストールのカスタム Rfc](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="013f9-123">For more information about the DLLs required by the adapter, see [Install Custom RFCs for the Data Provider for SAP](../../adapters-and-accelerators/adapter-sap/install-custom-rfcs-for-the-data-provider-for-sap.md).</span></span>
  
##  <a name="BKMK_SAPDisplay"></a> <span data-ttu-id="013f9-124">SAP アダプターが BizTalk 管理コンソールではありません。</span><span class="sxs-lookup"><span data-stu-id="013f9-124">The SAP adapter is missing in BizTalk Administration console</span></span>  
 <span data-ttu-id="013f9-125">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-125">**Problem**</span></span>  
  
<span data-ttu-id="013f9-126">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]に含まれている[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="013f9-126">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] included with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="013f9-127">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-127">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-128">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] WCF カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="013f9-128">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="013f9-129">そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-129">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="013f9-130">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-130">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-131">明示的に追加することができます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[SAP アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="013f9-131">You can explicitly add the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
##  <a name="BKMK_SAPConnOpen"></a> <span data-ttu-id="013f9-132">Dll の SAP への接続を開くときにエラーがないです。</span><span class="sxs-lookup"><span data-stu-id="013f9-132">DLLs are missing error opening a connection to SAP</span></span>  
 <span data-ttu-id="013f9-133">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-133">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-134">使用して SAP システムへの接続を開くしようとすると、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、いくつかの Dll が見つからないことを通知 ダイアログ ボックスは、SAP システムに表示されます。</span><span class="sxs-lookup"><span data-stu-id="013f9-134">When you try to open a connection to the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], a dialog box appears in the SAP system, informing that some DLLs are missing.</span></span>  
  
 <span data-ttu-id="013f9-135">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-135">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-136">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Librfc32u.dll を使用して、SAP システムとの接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="013f9-136">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses librfc32u.dll to establish a connection with the SAP system.</span></span> <span data-ttu-id="013f9-137">さらに、librfc32u.dll には、関数を Dll のセットが必要です。</span><span class="sxs-lookup"><span data-stu-id="013f9-137">The librfc32u.dll, in turn, requires a set of DLLs to function.</span></span> <span data-ttu-id="013f9-138">これらの Dll のサポートは、コンピューターの PATH 変数に追加されていない場合にこのエラーが発生した場所、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="013f9-138">You get this error if these supporting DLLs are not added to the PATH variable on the computer where the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is installed.</span></span>  
  
 <span data-ttu-id="013f9-139">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-139">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-140">解決方法として指定されたテーブルを参照してください、[アダプターのバインドを読み込み中にエラー](#client_dll)問題。</span><span class="sxs-lookup"><span data-stu-id="013f9-140">Refer to the table provided as a resolution to the [Error in loading the adapter bindings](#client_dll) issue.</span></span> <span data-ttu-id="013f9-141">表は、サポートに使用して SAP システムとやり取りするために必要な Dll、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-141">The table lists the supporting DLLs required to interface with the SAP system using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
##  <a name="BKMK_SAPXmlRetrieve"></a> <span data-ttu-id="013f9-142">65,536 個を超えるノードを持つ XML を取得中にエラー</span><span class="sxs-lookup"><span data-stu-id="013f9-142">Error retrieving XML with more than 65,536 nodes</span></span>  
 <span data-ttu-id="013f9-143">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-143">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-144">アダプターは、65,536 を超えるノードを持つ XML 出力の取得中に、次のエラーを説明します。</span><span class="sxs-lookup"><span data-stu-id="013f9-144">The adapter gives the following error while retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="013f9-145">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-145">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-146">アダプターは、シリアル化し、65,536 を超える項目を含むオブジェクトを逆シリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="013f9-146">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="013f9-147">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-147">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-148">この問題を解決するには、設定して、`maxItemsInObjectGraph`で次の 2 つの方法のいずれかのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="013f9-148">You can fix this issue by setting the `maxItemsInObjectGraph` parameter in either of the following two ways:</span></span>  
  
- <span data-ttu-id="013f9-149">変更することで、このパラメーターを設定、`maxItemsInObjectGraph`パラメーター、`ServiceBehavior`サービス クラスの属性。</span><span class="sxs-lookup"><span data-stu-id="013f9-149">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
- <span data-ttu-id="013f9-150">次のアプリケーションの app.config ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="013f9-150">Add the following to your application's app.config file.</span></span>  
  
  ```  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="NewBehavior">  
        <dataContractSerializer maxItemsInObjectGraph="65536000" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  ```  
  
  <span data-ttu-id="013f9-151">サンプルの app.config を次のようになります。</span><span class="sxs-lookup"><span data-stu-id="013f9-151">A sample app.config will look like the following.</span></span>  
  
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
  
##  <a name="BKMK_SAPConnURI"></a> <span data-ttu-id="013f9-152">BizTalk Server で WCF カスタム ポートの接続 URI の入力エラー</span><span class="sxs-lookup"><span data-stu-id="013f9-152">Error entering a connection URI for a WCF-Custom port in BizTalk Server</span></span>  
 <span data-ttu-id="013f9-153">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-153">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="013f9-154">接続、SAP システムに接続するための URI を指定する場合は、次のエラーを得られます。</span><span class="sxs-lookup"><span data-stu-id="013f9-154">gives the following error when you specify a connection URI to connect to the SAP system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="013f9-155">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-155">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-156">接続 URI は標準のエンコード形式に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="013f9-156">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="013f9-157">たとえば、パラメーターの値にスペースを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="013f9-157">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="013f9-158">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-158">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-159">指定した URI は、標準のエンコード形式に準拠する接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="013f9-159">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="013f9-160">たとえば、"%20"を空白の領域を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="013f9-160">For example, a blank space must be replaced by "%20".</span></span>  
  
##  <a name="BKMK_SAPOperate"></a> <span data-ttu-id="013f9-161">SAP に対する操作の完了中にエラーが System.ArgumentNullException</span><span class="sxs-lookup"><span data-stu-id="013f9-161">System.ArgumentNullException error while completing an operation on SAP</span></span>  
 <span data-ttu-id="013f9-162">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-162">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-163">使用して SAP システムに対して任意の操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-163">The adapter gives the following error when performing any operation on the SAP system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
```  
System.ArgumentNullException: Value cannot be null.  
```  
  
 <span data-ttu-id="013f9-164">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-164">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-165">メッセージの WCF アクションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="013f9-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="013f9-166">WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="013f9-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="013f9-167">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-167">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-168">送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="013f9-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="013f9-169">手順については、次を参照してください。 [SAP システムの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="013f9-169">For instructions, see [Configure the SOAP action for the SAP system](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md).</span></span> <span data-ttu-id="013f9-170">参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)各操作のアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="013f9-170">See [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md) to see a list of actions for each operation.</span></span>  
  
##  <a name="BKMK_SAPXmlParsing"></a> <span data-ttu-id="013f9-171">指定したアクションで正しくない操作名により XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="013f9-171">XmlReaderParsingException due to incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="013f9-172">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-172">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-173">BizTalk Server 管理コンソールでの SAP システムにメッセージを送信するときに、次のエラー。</span><span class="sxs-lookup"><span data-stu-id="013f9-173">The BizTalk Server Administration Console gives the following error when sending messages to an SAP system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="013f9-174">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-174">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-175">によって作成されたポートのバインド ファイルをインポートして WCF カスタム ポートを構成する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートのアクションは、次の形式で指定されます。</span><span class="sxs-lookup"><span data-stu-id="013f9-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="013f9-176">上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="013f9-176">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="013f9-177">RFC_CUSTOMER_GET 用にスキーマを生成した場合など、アクションで操作名では、"RFC_CUSTOMER_GET"になります。</span><span class="sxs-lookup"><span data-stu-id="013f9-177">For example, if you generated schema for RFC_CUSTOMER_GET, the operation name in the action will be "RFC_CUSTOMER_GET".</span></span> <span data-ttu-id="013f9-178">ただし、論理ポートの操作名が BizTalk のオーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="013f9-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="013f9-179">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-179">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-180">確実に操作名の両方の論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) (BizTalk Server 管理コンソール) で物理ポートが同じであるとします。</span><span class="sxs-lookup"><span data-stu-id="013f9-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
##  <a name="BKMK_SAPHundredCons"></a> <span data-ttu-id="013f9-181">SAP に 100 を超える接続を開くときのエラー</span><span class="sxs-lookup"><span data-stu-id="013f9-181">Error opening more than 100 connections to SAP</span></span>  
 <span data-ttu-id="013f9-182">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-182">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-183">SAP システムに 100 を超える接続を開くときに、アダプターは、次の例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="013f9-183">The adapter throws the following exception when opening more than 100 connections to the SAP system.</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.ConnectionException: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  GWHOST=<gw_host>, GWSERV=<gw_serv>, SYSNR=<sys_number>  
LOCATION    CPIC (TCP/IP) on local host with Unicode  
ERROR       max no of 100 conversations exceeded  
```  
  
 <span data-ttu-id="013f9-184">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-184">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-185">既定では、SAP は、システムに 100 を超える接続を有効にできません。</span><span class="sxs-lookup"><span data-stu-id="013f9-185">By default, SAP does not enable more than 100 connections into the system.</span></span>  
  
 <span data-ttu-id="013f9-186">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-186">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-187">接続の最大数を増やすには、SAP クライアント ライブラリがインストールされているし、数値の値に設定されているコンピューターで環境変数を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="013f9-187">To increase the maximum number of connections, you must create an environment variable on the computer that has the SAP client libraries installed and set it to a numeric value.</span></span> <span data-ttu-id="013f9-188">この環境変数に指定した値は、SAP システムに可能な接続の最大数です。</span><span class="sxs-lookup"><span data-stu-id="013f9-188">The value you specify for this environment variable is the maximum number of connections that can be made into the SAP system.</span></span> <span data-ttu-id="013f9-189">次の内容で環境変数を作成します。</span><span class="sxs-lookup"><span data-stu-id="013f9-189">Create the environment variable with the following details:</span></span>  
  
- <span data-ttu-id="013f9-190">**変数名**:CPIC_MAX_CONV</span><span class="sxs-lookup"><span data-stu-id="013f9-190">**Variable name**: CPIC_MAX_CONV</span></span>  
  
- <span data-ttu-id="013f9-191">**変数値**: 任意の正の数値。</span><span class="sxs-lookup"><span data-stu-id="013f9-191">**Variable value**: any positive numeric value.</span></span> <span data-ttu-id="013f9-192">たとえば、SAP システムに 200 の接続を有効にするには、200 として値を指定します。</span><span class="sxs-lookup"><span data-stu-id="013f9-192">For example, to enable 200 connections into the SAP system, specify the value as 200.</span></span>  
  
  <span data-ttu-id="013f9-193">環境変数を作成する方法の詳細については、次を参照してください。"で"Windows 2000 のシステム変数を作成する方法[ http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020)します。</span><span class="sxs-lookup"><span data-stu-id="013f9-193">For instructions on creating an environment variable, see "How To Create System Variables in Windows 2000" at [http://go.microsoft.com/fwlink/?LinkId=95020](http://go.microsoft.com/fwlink/?LinkId=95020).</span></span>  
  
##  <a name="BKMK_SAPIDOCMetadata"></a> <span data-ttu-id="013f9-194">エラーを生成するか、Idoc のメタデータを取得します。</span><span class="sxs-lookup"><span data-stu-id="013f9-194">Error generating or retrieving metadata for IDOCs</span></span>  
 <span data-ttu-id="013f9-195">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-195">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-196">メタデータを生成するときに、**受信**IDOC を SAP システムでの操作、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]というエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="013f9-196">While generating metadata for the **Receive** operation for an IDOC in an SAP system, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives the following error.</span></span>  
  
```  
Error while retrieving or generating the WSDL.  
Adapter message: Details: ErrorCode=RFC_EXCEPTION.  
ErrorGroup=RFC_ERROR_APPLICATION_EXCEPTION. SapErrorMessage= OBJECT_UNKNOWN.  
AdapterErrorMessage=Error returned by RfcCallReceiveEx while calling RFC: IDOCTYPE_READ_COMPLETE.  
```  
  
 <span data-ttu-id="013f9-197">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-197">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-198">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] IDOCTYPE_READ_COMPLETE RFC を使用してメタデータを取得する、**受信**IDOC に対する操作。</span><span class="sxs-lookup"><span data-stu-id="013f9-198">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses the IDOCTYPE_READ_COMPLETE RFC to retrieve the metadata for the **Receive** operation for an IDOC.</span></span> <span data-ttu-id="013f9-199">この RFC を呼び出すと、SAP システムで特定のユーザーのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="013f9-199">Invoking this RFC requires specific user permissions in the SAP system.</span></span> <span data-ttu-id="013f9-200">IDOCTYPE_READ_COMPLETE RFC を呼び出すアクセス許可がない資格情報を使用して SAP システムに接続している場合、メタデータを生成する、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]エラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="013f9-200">To generate metadata, if you have connected to the SAP system using a credential that does not have permission to invoke the IDOCTYPE_READ_COMPLETE RFC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an error.</span></span>  
  
 <span data-ttu-id="013f9-201">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-201">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-202">アダプターを使用したのと同じ資格情報を使用して、SAP GUI にログインします。</span><span class="sxs-lookup"><span data-stu-id="013f9-202">Log in to the SAP GUI using the same credentials you had used for the adapter.</span></span> <span data-ttu-id="013f9-203">トランザクション SE37 に移動し、IDOCTYPE_READ_COMPLETE として実行するには、RFC の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="013f9-203">Navigate to transaction SE37, and enter the name of the RFC to execute as IDOCTYPE_READ_COMPLETE.</span></span>  
  
 <span data-ttu-id="013f9-204">PI_IDOCTYP と PI_CIMTYP の入力パラメーターでは、カスタム IDoc に対応する値を入力します。</span><span class="sxs-lookup"><span data-stu-id="013f9-204">For the input parameters PI_IDOCTYP and PI_CIMTYP, enter the values corresponding to the custom IDoc.</span></span> <span data-ttu-id="013f9-205">PI_VERSION と PI_RELEASE パラメーター、アダプター メタデータの UI で選ばれているとして同じ値を入力します。</span><span class="sxs-lookup"><span data-stu-id="013f9-205">For the parameters PI_VERSION and PI_RELEASE, enter the same values as being chosen in the Adapter Metadata UI.</span></span> <span data-ttu-id="013f9-206">実行には f8 キーを押します。</span><span class="sxs-lookup"><span data-stu-id="013f9-206">And, press F8 to execute.</span></span>  
  
 <span data-ttu-id="013f9-207">としてどのようなアダプターを受け取ると、問題に関する詳細情報を同じ例外が発生する必要があります。</span><span class="sxs-lookup"><span data-stu-id="013f9-207">You should get the same exception as what the adapter receives, with more information about the issue.</span></span>  
  
 <span data-ttu-id="013f9-208">それでも問題を解決できない場合は、スキーマを生成、 **ReceiveIdoc**操作の代わりに、**受信**操作。</span><span class="sxs-lookup"><span data-stu-id="013f9-208">If you are still not able to resolve the issue, generate a schema for the **ReceiveIdoc** operation instead of the **Receive** operation.</span></span> <span data-ttu-id="013f9-209">この場合、SAP アダプターは IDOCTYPE_READ_COMPLETE を使用しないと、エラーをスローしません。</span><span class="sxs-lookup"><span data-stu-id="013f9-209">In this case, the SAP adapter does not use IDOCTYPE_READ_COMPLETE, and does not throw any error.</span></span>  
  
##  <a name="BKMK_SAPIDOCReceive"></a> <span data-ttu-id="013f9-210">エラーを送信または受信するが解放されていないセグメントの Idoc</span><span class="sxs-lookup"><span data-stu-id="013f9-210">Error sending or receiving IDOCs that have unreleased segments</span></span>  
 <span data-ttu-id="013f9-211">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-211">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-212">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]で Idoc を送信中には、XmlReaderParsingException (を使用して**送信**操作) Idoc を受信するか (を使用して**受信**操作) が解放されていないセグメント。</span><span class="sxs-lookup"><span data-stu-id="013f9-212">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException while sending IDOCs (using **Send** operation) or receiving IDOCs (using **Receive** operation) that have unreleased segments.</span></span>  
  
 <span data-ttu-id="013f9-213">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-213">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-214">セグメントの Idoc を使用したされます。</span><span class="sxs-lookup"><span data-stu-id="013f9-214">IDOCs are constituted of segments.</span></span> <span data-ttu-id="013f9-215">メタデータの生成中に、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムに存在するすべてのリリースされたセグメントを取得します。</span><span class="sxs-lookup"><span data-stu-id="013f9-215">While generating metadata, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] retrieves all the released segments that are present in the SAP system.</span></span> <span data-ttu-id="013f9-216">など、IDOC の受信操作を実行するにアダプターのクライアントがメタデータを使用する場合に、ただし、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] XmlReaderParsingException を提供します。</span><span class="sxs-lookup"><span data-stu-id="013f9-216">However, when the adapter client uses the metadata to perform an operation such as receiving an IDOC, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] gives an XmlReaderParsingException.</span></span> <span data-ttu-id="013f9-217">これには、IDOC を受信すると、SAP システムがいくつか解放されていないセグメントも、対象のメタデータは、アダプターによって生成されませんでしたを送信がある可能性があるために発生します。</span><span class="sxs-lookup"><span data-stu-id="013f9-217">This occurs because when the IDOC is received, the SAP system might have sent some unreleased segments as well, the metadata for which was not generated by the adapter.</span></span>  
  
 <span data-ttu-id="013f9-218">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-218">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-219">次のいずれかを行います。</span><span class="sxs-lookup"><span data-stu-id="013f9-219">Do any of the following:</span></span>  
  
-   <span data-ttu-id="013f9-220">解放されていないセグメントの適切な修正プログラムを適用することで、SAP システムをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="013f9-220">Upgrade your SAP system by applying appropriate patches for the unreleased segments.</span></span>  
  
-   <span data-ttu-id="013f9-221">使用**SendIdoc**または**ReceiveIdoc**操作を送信し、それぞれに Idoc を受信します。</span><span class="sxs-lookup"><span data-stu-id="013f9-221">Use **SendIdoc** or **ReceiveIdoc** operations to send and receive IDOCs respectively.</span></span> <span data-ttu-id="013f9-222">これらの操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="013f9-222">For more information about these operations, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <a name="BKMK_SAPIDOCSend"></a> <span data-ttu-id="013f9-223">Sap SAP FilePort で受信したフラット ファイル Idoc を送信するエラー</span><span class="sxs-lookup"><span data-stu-id="013f9-223">Error sending flat-file IDOCs to SAP that were received using the SAP FilePort</span></span>  
 <span data-ttu-id="013f9-224">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-224">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-225">送信しようとする場合 (を使用して**送信**操作) されるため、XML 形式に flatf ファイルを変換するフラット ファイル IDOC を SAP FilePort を使用して生成された SAP システムには、BizTalk オーケストレーションで、フラット ファイル パーサーの失敗、IDOD**送信**操作。</span><span class="sxs-lookup"><span data-stu-id="013f9-225">If you try to send (using **Send** operation) a flat-file IDOC to an SAP system that was generated using an SAP FilePort, the flat-file parser in the BizTalk orchestration fails to convert the flatf-file to an XML format, thereby failing the IDOD **Send** operation.</span></span>  
  
 <span data-ttu-id="013f9-226">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-226">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-227">SAP システムは、FilePort を使用して IDOC を生成するときは、セグメントの最後にすべての空白をトリムします。</span><span class="sxs-lookup"><span data-stu-id="013f9-227">When the SAP system generates an IDOC using a FilePort, it trims off all the empty spaces at the end of a segment.</span></span> <span data-ttu-id="013f9-228">ただし、フラット ファイル パーサーを正常にフラット ファイルを XML に変換するために、セグメントの最後のフィールドのデータが必要です。</span><span class="sxs-lookup"><span data-stu-id="013f9-228">However, the flat-file parser expects the data of the last field in the segment to be present to successfully convert the flat-file to XML.</span></span> <span data-ttu-id="013f9-229">空のスペースがセグメントに存在しないため、フラット ファイル パーサーが XML をフラット ファイルの解析に失敗します。</span><span class="sxs-lookup"><span data-stu-id="013f9-229">Because the empty spaces are not present in the segment, the flat-file parser fails to parse the flat-file to XML.</span></span>  
  
 <span data-ttu-id="013f9-230">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-230">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-231">フラット ファイル Idoc が SAP FilePort を使用して生成されたこのような使用、 **SendIdoc**操作代わりにします。</span><span class="sxs-lookup"><span data-stu-id="013f9-231">For such flat-file IDOCs generated using the SAP FilePort, use the **SendIdoc** operation instead.</span></span> <span data-ttu-id="013f9-232">この操作の詳細については、次を参照してください。 [sap Idoc に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="013f9-232">For more information about this operation, see [Operations on IDOCs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-idocs-in-sap.md).</span></span>  
  
##  <a name="BKMK_SAPRecIDOCCompat"></a> <span data-ttu-id="013f9-233">EnableBizTalkCompatibilityMode プロパティが設定されている場合、SAP の Idoc を受信中にエラーを true に</span><span class="sxs-lookup"><span data-stu-id="013f9-233">Error receiving IDOCs from SAP if EnableBizTalkCompatibilityMode property is set to true</span></span>  
 <span data-ttu-id="013f9-234">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-234">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-235">IDOC を受信中に、次の例外が発生した、 **EnableBizTalkCompatibilityMode**プロパティ セットを true にバインドします。</span><span class="sxs-lookup"><span data-stu-id="013f9-235">The following exception is encountered while receiving an IDOC with the **EnableBizTalkCompatibilityMode** binding property set to true:</span></span>  
  
```  
System.Exception: Loading property information list by namespace failed or property not found in the list. Verify that the schema is deployed properly.  
```  
  
 <span data-ttu-id="013f9-236">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-236">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-237">場合、バインド プロパティ**EnableBizTalkCompatibilityMode**に設定されている**true**、BizTalk プロパティ スキーマ DLL を追加する必要がありますの[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]、つまり、BizTalk アプリケーションにリソースとして、プロジェクトがデプロイされているアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="013f9-237">If the binding property **EnableBizTalkCompatibilityMode** is set to **true**, you must add the BizTalk property schema DLL for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as a resource in your BizTalk application, that is, the application in which your project is deployed.</span></span>  
  
 <span data-ttu-id="013f9-238">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-238">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-239">BizTalk プロパティ スキーマの名前、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]は*Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*します。</span><span class="sxs-lookup"><span data-stu-id="013f9-239">The name for the BizTalk property schema for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is *Microsoft.Adapters.SAP.BiztalkPropertySchema.dll*.</span></span> <span data-ttu-id="013f9-240">これには、インストールによって、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]セットアップ\<インストール ドライブ\>: \Program files \microsoft BizTalk アダプター Pack\bin します。</span><span class="sxs-lookup"><span data-stu-id="013f9-240">This is installed by the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] setup under \<installation drive\>:\ Program Files\Microsoft BizTalk Adapter Pack\bin.</span></span> <span data-ttu-id="013f9-241">このアセンブリを BizTalk アプリケーション内のリソースとして追加するには、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="013f9-241">Perform the following tasks to add this assembly as a resource in your BizTalk application.</span></span>  
  
#### <a name="add-an-assembly-as-a-resource-in-biztalk-application"></a><span data-ttu-id="013f9-242">BizTalk アプリケーションにリソースとしてアセンブリを追加します。</span><span class="sxs-lookup"><span data-stu-id="013f9-242">Add an assembly as a resource in BizTalk application</span></span>  
  
1. <span data-ttu-id="013f9-243">開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="013f9-243">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="013f9-244">コンソール ツリーで、展開**BizTalk グループ**、展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーションでは、します。</span><span class="sxs-lookup"><span data-stu-id="013f9-244">In the console tree, expand **BizTalk Group**, expand **Applications**, and then the application to which you want to add a BizTalk assembly.</span></span>  
  
3. <span data-ttu-id="013f9-245">展開**アプリケーション**と BizTalk アセンブリを追加するアプリケーション。</span><span class="sxs-lookup"><span data-stu-id="013f9-245">Expand **Applications** and the application to which you want to add a BizTalk assembly.</span></span>  
  
4. <span data-ttu-id="013f9-246">右クリック**リソース**、 をポイント**追加**、 をクリックし、 **BizTalk アセンブリ**します。</span><span class="sxs-lookup"><span data-stu-id="013f9-246">Right-click **Resources**, point to **Add**, and then click **BizTalk Assemblies**.</span></span>  
  
5. <span data-ttu-id="013f9-247">クリックして**追加**、BizTalk アセンブリ ファイルを含むフォルダーに移動し、BizTalk アセンブリ ファイルを選択を順にクリックします**オープン**します。</span><span class="sxs-lookup"><span data-stu-id="013f9-247">Click **Add**, navigate to the folder containing the BizTalk assembly file, select the BizTalk assembly file, and then click **Open**.</span></span>  
  
6. <span data-ttu-id="013f9-248">**オプション**、BizTalk アセンブリを GAC にインストールするためのオプションを指定し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="013f9-248">In **Options**, specify the options for installing the BizTalk assembly to the GAC, and then click **OK**.</span></span>  
  
##  <a name="BKMK_SAPIDOCValidate"></a> <span data-ttu-id="013f9-249">SAP システムから Idoc を受信中に検証エラー</span><span class="sxs-lookup"><span data-stu-id="013f9-249">Error in validation while receiving IDOCs from an SAP system</span></span>  
 <span data-ttu-id="013f9-250">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-250">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-251">SAP システムから受信した IDOC には、次のようなエラーで検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="013f9-251">An IDOC received from an SAP system fails validation with an error similar to the following:</span></span>  
  
```  
There was a failure executing the receive pipeline: "Microsoft.BizTalk.DefaultPipelines.XMLReceive, Microsoft.BizTalk.DefaultPipelines, Version=3.0.1.0, Culture=neutral, PublicKeyToken=<token>"  
Source: "Pipeline " Receive Port: "ReceiveIdoc" URI: "<connection uri>"  
Reason: The document failed to validate because of the following error:  
"The 'http://Microsoft.LobServices.Sap/2007/03/Types/Idoc/3/CREMAS03//620:TAXBS' element has an invalid value according to its data type."  
```  
  
 <span data-ttu-id="013f9-252">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-252">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-253">IDOC を受信するために生成されたメタデータには、受信操作の一部として、特定の列用に受信することを指定できる値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="013f9-253">The metadata generated for receiving an IDOC contains the permissible values that can be received for a particular column as part of the receive operation.</span></span> <span data-ttu-id="013f9-254">これらの値は、生成されたメタデータ内の列挙型として公開されます。</span><span class="sxs-lookup"><span data-stu-id="013f9-254">These values are exposed as enumeration in the generated metadata.</span></span> <span data-ttu-id="013f9-255">ただし、IDOC が実際に受信されると、受信した値は、列挙値を異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="013f9-255">However, when the IDOC is actually received, the value received could be different from the enumerated values.</span></span> <span data-ttu-id="013f9-256">そのため、値の検証中に受信操作が失敗します。</span><span class="sxs-lookup"><span data-stu-id="013f9-256">Hence the receive operation fails while validating the values.</span></span> <span data-ttu-id="013f9-257">たとえば、上記のエラーでは、TAXBS 列にメッセージの検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="013f9-257">For example, in the above error message validation fails for the TAXBS column.</span></span>  
  
 <span data-ttu-id="013f9-258">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-258">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-259">必要があります手動で編集する (BizTalk プロジェクト) のスキーマまたはクライアント プロキシで列挙型 (サービス モデルの WCF を使用して .NET プロジェクト) の SAP システムから受信した値を含める。</span><span class="sxs-lookup"><span data-stu-id="013f9-259">You must manually edit the enumeration in schema (for BizTalk projects) or the client proxy (for .NET projects using WCF service model) to include the value received from the SAP system.</span></span>  
  
##  <a name="BKMK_SAPFFIDOC"></a> <span data-ttu-id="013f9-260">フラット ファイル Idoc を前に、と後、XML への変換が同一でないです。</span><span class="sxs-lookup"><span data-stu-id="013f9-260">Flat-file IDOCs, before and after converting to XML, are not identical</span></span>  
 <span data-ttu-id="013f9-261">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-261">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-262">フラット ファイル IDOC をスキーマを使用して XML に変換し、スキーマを使用して、パイプライン経由のフラット ファイル IDOC を XML に変換するフラット ファイル パーサーを使用する場合は 2 つのフラット ファイル Idoc が一致しません。</span><span class="sxs-lookup"><span data-stu-id="013f9-262">If you use a flat file parser to convert a flat-file IDOC to an XML using the schema, and then convert the XML back to a flat-file IDOC through a pipeline using the schema, the two flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="013f9-263">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-263">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-264">XML フラット ファイル IDOC からを生成するときに、フラット ファイル パーサーが空白の値を持つ XML ノードを生成しません。</span><span class="sxs-lookup"><span data-stu-id="013f9-264">When generating the XML from a flat-file IDOC, the flat file parser does not generate the XML nodes with blank values.</span></span> <span data-ttu-id="013f9-265">この XML は、フラット ファイルに変換するときに、XML から不足しているノードは、フラット ファイル IDOC に反映されません。</span><span class="sxs-lookup"><span data-stu-id="013f9-265">When this XML is converted back to a flat-file, the nodes missing from the XML are not reflected in the flat-file IDOC.</span></span> <span data-ttu-id="013f9-266">そのため、フラット ファイル Idoc が一致しません。</span><span class="sxs-lookup"><span data-stu-id="013f9-266">Hence the flat-file IDOCs are not identical.</span></span>  
  
 <span data-ttu-id="013f9-267">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-267">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-268">フラット ファイルを XML、および「送信」または「受信」のノード定義内で、その逆に変換するために使用するスキーマで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="013f9-268">In the schema used to convert the flat-file to XML and vice-versa, within the "Send" or "Receive" node definition, do the following:</span></span>  
  
1. <span data-ttu-id="013f9-269">設定、 **suppress_empty_nodes**プロパティを**false**設定と、 **generate_empty_nodes**プロパティを**true**します。</span><span class="sxs-lookup"><span data-stu-id="013f9-269">Set the **suppress_empty_nodes** property to **false** and set the **generate_empty_nodes** property to **true**.</span></span> <span data-ttu-id="013f9-270">既定で、 **suppress_empty_nodes**プロパティに設定されて**true**と**generate_empty_nodes**プロパティに設定されて**false**とそのためすべての空のノードは、XML には反映されません。</span><span class="sxs-lookup"><span data-stu-id="013f9-270">By default, the **suppress_empty_nodes** property is set to **true** and the **generate_empty_nodes** property is set to **false**, and hence all empty nodes are not reflected in the XML.</span></span>  
  
2. <span data-ttu-id="013f9-271">フラット ファイルには、末尾に余分な改行を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="013f9-271">The flat-file may contain an extra carriage return at the end.</span></span> <span data-ttu-id="013f9-272">設定することができます、 **suppress_trailing_delimiters**プロパティを**はい**この余分なキャリッジ リターンを回避するためにします。</span><span class="sxs-lookup"><span data-stu-id="013f9-272">You can set the **suppress_trailing_delimiters** property to **Yes** to avoid this extra carriage return.</span></span> <span data-ttu-id="013f9-273">このプロパティも公開、**末尾の区切り記号の抑制**プロパティ内のスキーマを開く場合[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-273">This property is also exposed as the **Suppress Trailing Delimiters** property if you open the schema in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
##  <a name="BKMK_SAPAction"></a> <span data-ttu-id="013f9-274">バインド ファイルと共に作成する物理ポートを使用して、誤った操作エラー</span><span class="sxs-lookup"><span data-stu-id="013f9-274">Incorrect Action error using a physical port creating with a binding file</span></span>  
 <span data-ttu-id="013f9-275">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-275">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-276">使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] SAP システムで特定の操作のスキーマを生成するアドインも作成ポートのバインド ファイル。</span><span class="sxs-lookup"><span data-stu-id="013f9-276">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the SAP system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="013f9-277">インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server で物理ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="013f9-277">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="013f9-278">ただし、このようなポートを使用して SAP システムにメッセージを送信するとき、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。</span><span class="sxs-lookup"><span data-stu-id="013f9-278">However, when you send messages to the SAP system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="013f9-279">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-279">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-280">BizTalk オーケストレーションでの論理ポートを作成するときにこれらのポートの操作に特定の名前を指定または Operation_1、Operation_2 などのように既定の名前を使用します。ただし、によって生成されたバインド ファイルで、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する操作の名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="013f9-280">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="013f9-281">たとえば、RFC_CUSTOMER_GET のメタデータを生成する場合に、次のアクションは設定されます。</span><span class="sxs-lookup"><span data-stu-id="013f9-281">For example, if you generate metadata for RFC_CUSTOMER_GET, the action will be set to the following:</span></span>  
  
```  
<Operation Name="RFC_CUSTOMER_GET" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
```  
  
 <span data-ttu-id="013f9-282">バインド ファイルをインポートすると、物理ポートで同じアクションが設定されます。</span><span class="sxs-lookup"><span data-stu-id="013f9-282">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="013f9-283">そのため、論理ポート (Operation_1、Operation_2 など) の操作名では、エラーが発生する物理ポートで、アクションで指定された操作名が一致しません。</span><span class="sxs-lookup"><span data-stu-id="013f9-283">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="013f9-284">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-284">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-285">論理ポートで操作の名前は、物理ポートにアクションの一部として指定された操作名と同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="013f9-285">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="013f9-286">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="013f9-286">Do one of the following:</span></span>  
  
-   <span data-ttu-id="013f9-287">RFC_CUSTOMER_GET などのメタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートの操作名を変更します。</span><span class="sxs-lookup"><span data-stu-id="013f9-287">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example RFC_CUSTOMER_GET.</span></span>  
  
-   <span data-ttu-id="013f9-288">論理ポートで、操作名に物理ポートのアクションで、操作名を変更します。</span><span class="sxs-lookup"><span data-stu-id="013f9-288">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="013f9-289">たとえば、次のように物理ポートにアクションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="013f9-289">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET" />  
    ```  
  
##  <a name="BKMK_SAPTableParams"></a> <span data-ttu-id="013f9-290">応答メッセージにはで SAP 操作が実行されたが含まれていないテーブル パラメーターには</span><span class="sxs-lookup"><span data-stu-id="013f9-290">The response message for an operation ran on SAP does not contain any table parameters</span></span>  
 <span data-ttu-id="013f9-291">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-291">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-292">使用する場合、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムでの操作を実行する多数のテーブルを返すし、各テーブルには、SAP システムからの応答メッセージの一部として返される大規模なデータセットに金額は、レコードの数が多い。</span><span class="sxs-lookup"><span data-stu-id="013f9-292">If you use the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to execute an operation on the SAP system that returns a large number of tables, and each table has a large number of records, that will amount to a large dataset being returned as part of the response message from the SAP system.</span></span> <span data-ttu-id="013f9-293">既定で、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]応答メッセージの一部としてテーブル パラメーターは返されません。</span><span class="sxs-lookup"><span data-stu-id="013f9-293">So, by default, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not return any table parameters as part of the response message.</span></span>  
  
 <span data-ttu-id="013f9-294">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-294">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-295">追加するテーブルを要求する[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]応答の一部として返すにします。</span><span class="sxs-lookup"><span data-stu-id="013f9-295">You can request the tables that you want [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to return as part of the response.</span></span> <span data-ttu-id="013f9-296">SAP システムに送信する要求メッセージの一部として、空のテーブルのパラメーターを提供することで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="013f9-296">You can do so by providing an empty table parameter as part of the request message that you send to the SAP system.</span></span> <span data-ttu-id="013f9-297">たとえば、 `<table_parameter_name />`のようにします。</span><span class="sxs-lookup"><span data-stu-id="013f9-297">For example, `<table_parameter_name />`.</span></span>  
  
##  <a name="BKMK_SAPIncorrectCreds"></a> <span data-ttu-id="013f9-298">アダプター クライアントは、SAP からの応答を受け取りません</span><span class="sxs-lookup"><span data-stu-id="013f9-298">Adapter Clients do not receive the response from SAP</span></span>
 <span data-ttu-id="013f9-299">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-299">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-300">アダプターを使用するときに[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、資格情報、wcf-custom 送信ポートが正しくない要求メッセージは処理されません。</span><span class="sxs-lookup"><span data-stu-id="013f9-300">When using the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], if the credentials on the WCF-custom send port are incorrect, the request messages are not processed.</span></span> <span data-ttu-id="013f9-301">正しい資格情報を指定した後、SAP システムにメッセージを送信し、応答を受信します。</span><span class="sxs-lookup"><span data-stu-id="013f9-301">After you specify the correct credentials, the message is sent to the SAP system and a response is received.</span></span> <span data-ttu-id="013f9-302">ただし、応答メッセージでは、出力ポートを使用できません。</span><span class="sxs-lookup"><span data-stu-id="013f9-302">However, the response message is not available to the out port.</span></span>  
  
 <span data-ttu-id="013f9-303">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-303">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-304">BizTalk ホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="013f9-304">Restart the BizTalk host instance.</span></span>  
  
##  <a name="BKMK_SAPInboundConn"></a> <span data-ttu-id="013f9-305">SAP サーバーから受信メッセージの受信接続の問題</span><span class="sxs-lookup"><span data-stu-id="013f9-305">Connectivity issues receiving an inbound message from the SAP server</span></span>  
 <span data-ttu-id="013f9-306">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-306">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-307">WCF カスタムを使用して、SAP サーバーからの受信メッセージの受信ポートを受信中にのみ、次のエラーが発生した、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-307">You get the following error only while receiving an inbound message from the SAP server using a WCF-Custom receive port for the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
```  
The Messaging Engine failed to add a receive location "<location_name>" with URL "<connection URI>" to the adapter "WCF-Custom".  
Reason: "Microsoft.Adapters.SAP.RFCException: Details: ErrorCode=RFC_OK. ErrorGroup=RFC_ERROR_COMMUNICATION. SapErrorMessage=Connect to SAP gateway failed  
Connect_PM  TPNAME=<name>, GWHOST=<host>, GWSERV=<server>  
```  
  
 <span data-ttu-id="013f9-308">ただしは、正常に送信ポートの WCF カスタムを使用して SAP システムへのメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="013f9-308">However, you are successfully able to send messages to the SAP system using a WCF-Custom send port.</span></span>  
  
 <span data-ttu-id="013f9-309">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-309">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-310">アダプター クライアントを実行し、受信メッセージの受信をもう一度お試しください。 場所は、同じコンピューターには、SAP GUI をインストールします。</span><span class="sxs-lookup"><span data-stu-id="013f9-310">Install the SAP GUI on the same computer where you are running the adapter client and try receiving the inbound message again.</span></span> <span data-ttu-id="013f9-311">SAP GUI をインストールする方法の詳細については、SAP のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="013f9-311">For more information about how to install the SAP GUI, refer to SAP documentation.</span></span>  
  
##  <a name="BKMK_SAPRootNode"></a> <span data-ttu-id="013f9-312">BizTalk プロジェクト内の RootNode TypeName とエラー</span><span class="sxs-lookup"><span data-stu-id="013f9-312">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="013f9-313">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-313">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-314">BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:</span><span class="sxs-lookup"><span data-stu-id="013f9-314">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="013f9-315">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-315">**Resolution**</span></span>  
  
1.  <span data-ttu-id="013f9-316">クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="013f9-316">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="013f9-317">**RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。</span><span class="sxs-lookup"><span data-stu-id="013f9-317">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
##  <a name="BKMK_SAPVS2008"></a> <span data-ttu-id="013f9-318">Visual Studio で、アダプターを使用する際に無効なバインド警告</span><span class="sxs-lookup"><span data-stu-id="013f9-318">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="013f9-319">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-319">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-320">Visual Studio でアプリケーションを作成するアダプターを使用すると、アダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="013f9-320">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'sapBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="013f9-321">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-321">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-322">この警告が表示されます、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]バインド、`sapBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="013f9-322">This warning appears because the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] binding, `sapBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="013f9-323">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-323">**Resolution**</span></span>  
  
 <span data-ttu-id="013f9-324">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="013f9-324">You can safely ignore this warning.</span></span>  
  
##  <a name="BKMK_SAPSimilarSchema"></a> <span data-ttu-id="013f9-325">BizTalk Server での XLANG 例外</span><span class="sxs-lookup"><span data-stu-id="013f9-325">XLANG exception in BizTalk Server</span></span>
 <span data-ttu-id="013f9-326">**問題**</span><span class="sxs-lookup"><span data-stu-id="013f9-326">**Problem**</span></span>  
  
 <span data-ttu-id="013f9-327">BizTalk Server では、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="013f9-327">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="013f9-328">**原因**</span><span class="sxs-lookup"><span data-stu-id="013f9-328">**Cause**</span></span>  
  
 <span data-ttu-id="013f9-329">これは、次のいずれかの原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="013f9-329">This happens because of either of the following:</span></span>  
  
- <span data-ttu-id="013f9-330">1 つ以上を生成した (SendIdoc ReceiveIdoc など)、BizTalk Server プロジェクト内の汎用的な操作のスキーマを BizTalk Server アプリケーションに展開し、SAP システムのそれぞれの操作を実行するアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="013f9-330">You have generated more than one schema of a generic operation (such as SendIdoc and ReceiveIdoc) in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to perform respective operations on an SAP system.</span></span> <span data-ttu-id="013f9-331">競合が、スキーマは共通であるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。</span><span class="sxs-lookup"><span data-stu-id="013f9-331">Because the schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
- <span data-ttu-id="013f9-332">複数のプロジェクトが発生した場合の各 BizTalk Server プロジェクトの一般的な操作のスキーマを生成、各プロジェクトを同じ BizTalk Server アプリケーション ホスト、および、実行、またはアプリケーションを実行するそれぞれの個別にデプロイSAP システムに対する操作。</span><span class="sxs-lookup"><span data-stu-id="013f9-332">In case of multiple projects, you have generated a generic operation schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to perform respective operations on an SAP system.</span></span> <span data-ttu-id="013f9-333">競合が、スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるために展開 BizTalk Server アプリケーションとアセンブリのさまざまな一般的なスキーマの間であります。</span><span class="sxs-lookup"><span data-stu-id="013f9-333">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
  <span data-ttu-id="013f9-334">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="013f9-334">**Resolution**</span></span>  
  
  <span data-ttu-id="013f9-335">BizTalk Server アプリケーションの 1 つの一般的な操作のスキーマ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="013f9-335">Use a single generic operation schema file for a BizTalk Server application.</span></span> <span data-ttu-id="013f9-336">同じホスト上の複数の BizTalk Server アプリケーションで汎用的な操作のスキーマを使用する必要がある場合は、1 つの汎用操作スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションからジェネリック操作のスキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="013f9-336">If you need to use a generic operation schema in multiple BizTalk Server applications on the same host, create an application containing a single generic operation schema, and then use the generic operation schema from all other applications in BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="013f9-337">参照</span><span class="sxs-lookup"><span data-stu-id="013f9-337">See Also</span></span>  
[<span data-ttu-id="013f9-338">SAP アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="013f9-338">Troubleshoot the SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/troubleshoot-the-sap-adapter.md)