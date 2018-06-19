---
title: Siebel アダプターの BizTalk での運用上の問題のトラブルシューティング |Microsoft ドキュメント
description: 共通の問題と解決策の Siebel アダプターの BizTalk アダプター パック (BAP) の
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 74d152d9-9893-4f93-894a-350bae8be7bd
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff6e36afd7cecc967069fd3ecf5414c6afdb014
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009635"
---
# <a name="troubleshoot-operational-issues-with-the-siebel-adapter"></a><span data-ttu-id="204a6-103">Siebel アダプターでの運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="204a6-103">Troubleshoot Operational Issues with the Siebel adapter</span></span>
<span data-ttu-id="204a6-104">このセクションで説明を使用する場合に発生する可能性が運用上の問題に関する情報をまとめて、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="204a6-104">This section provides a centralized location for information about operational issues you might encounter when using the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
## <a name="enabling-tracing"></a><span data-ttu-id="204a6-105">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="204a6-105">Enabling Tracing</span></span>  
 <span data-ttu-id="204a6-106">トレースのサポートについては、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を参照してください[診断トレースと Siebel アダプターのメッセージがログ](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="204a6-106">For information about tracing support in the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Diagnostic Tracing and Message Logging for the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/diagnostic-tracing-and-message-logging-for-the-siebel-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="204a6-107">既知の問題</span><span class="sxs-lookup"><span data-stu-id="204a6-107">Known Issues</span></span>  
 <span data-ttu-id="204a6-108">いくつかの問題と推奨されるソリューションを使用しているときに発生する可能性を次のとおり、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="204a6-108">The following are some issues and recommended solutions that you might encounter while using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
  
###  <a name="BKMK_SiebelBindingError"></a><span data-ttu-id="204a6-109">アダプターのバインドを読み込み中にエラー</span><span class="sxs-lookup"><span data-stu-id="204a6-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="204a6-110">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-110">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-111">起動しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]GUI では、次のエラー。</span><span class="sxs-lookup"><span data-stu-id="204a6-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the GUI gives the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="204a6-112">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-112">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-113">開始すると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="204a6-113">When you start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="204a6-114">さらに、アダプターのバインドは、特定のエンタープライズ アプリケーションのクライアント ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="204a6-114">In turn, the adapter bindings are dependent on the specific enterprise application client software.</span></span> <span data-ttu-id="204a6-115">そのため、次の理由の一方または両方について、この問題に直面する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="204a6-115">So, you could face this issue for one or both of the following reasons:</span></span>  
  
-   <span data-ttu-id="204a6-116">必要な LOB クライアント ソフトウェアは、アダプターがインストールされているコンピューターにインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="204a6-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
-   <span data-ttu-id="204a6-117">すべてのアダプターをインストールすると、アダプターの「標準」や「完了」のインストールで実行した、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="204a6-117">You did a "Typical" or "Complete" installation of the adapter, which installs all the adapters in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="204a6-118">ただし、1 つだけのエンタープライズ アプリケーション用のクライアント ライブラリをインストールする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="204a6-118">However, the client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="204a6-119">その結果、GUI は、他のアダプターのバインドを読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="204a6-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
 <span data-ttu-id="204a6-120">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-120">**Resolution**</span></span>  
  
-   <span data-ttu-id="204a6-121">必要なクライアントのバージョンがインストールされているコンピューターにインストールされていることを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="204a6-121">Make sure the required client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="204a6-122">必要があるアダプターのみをインストールするアダプターのカスタム インストールを行うことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="204a6-122">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
###  <a name="BKMK_SiebelDispAdap"></a><span data-ttu-id="204a6-123">Siebel アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="204a6-123">The Siebel adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="204a6-124">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-124">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-125">付属するアダプターの以前のバージョンとは異なり[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]に付属の[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="204a6-125">Unlike the earlier version of the adapters that shipped with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] that shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] does not show up in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="204a6-126">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-126">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-127">最新[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]WCF カスタム バインドがします。</span><span class="sxs-lookup"><span data-stu-id="204a6-127">The latest [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="204a6-128">そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールに表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="204a6-128">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="204a6-129">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-129">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-130">明示的に追加することができます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]に記載されている手順に従って、管理コンソール[Siebel アダプターを BizTalk Server 管理コンソールに追加](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)です。</span><span class="sxs-lookup"><span data-stu-id="204a6-130">You can explicitly add the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_SiebelConnecting"></a><span data-ttu-id="204a6-131">Siebel システムへの接続中にエラー</span><span class="sxs-lookup"><span data-stu-id="204a6-131">Error while connecting to the Siebel system</span></span>  
 <span data-ttu-id="204a6-132">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-132">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-133">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]Siebel システムに接続しようとすると、次のエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="204a6-133">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] gives the following error when you try to connect to the Siebel system:</span></span>  
  
```  
Connecting to the system LOB has failed. Retrieving the COM class factory for component with CLSID {ID} failed due to the following error: 80040154  
```  
  
 <span data-ttu-id="204a6-134">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-134">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-135">Siebel Web クライアントは、コンピューターにインストールされていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="204a6-135">The Siebel Web client might not be installed on the computer.</span></span>  
  
 <span data-ttu-id="204a6-136">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-136">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-137">Siebel Web クライアントのサポートされているバージョンがコンピューターにインストールされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="204a6-137">Make sure the supported version of the Siebel Web client is installed on the computer.</span></span> <span data-ttu-id="204a6-138">サポートされているクライアントのインストール ガイドおよび Siebel のサーバー バージョンを参照してください。</span><span class="sxs-lookup"><span data-stu-id="204a6-138">Refer to the installation guide for supported client and server versions for Siebel.</span></span> <span data-ttu-id="204a6-139">インストール ガイドは\<システム ドライブ\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents です。</span><span class="sxs-lookup"><span data-stu-id="204a6-139">The installation guide is available at \<system drive\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
###  <a name="BKMK_SiebelXMLRetrieve"></a><span data-ttu-id="204a6-140">65536 以上のノードを持つ Xml を取得中にエラー</span><span class="sxs-lookup"><span data-stu-id="204a6-140">Error while retrieving XMLs with more than 65536 nodes</span></span>  
 <span data-ttu-id="204a6-141">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-141">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-142">アダプターは、65536 以上のノードを持つ XML 出力を取得中に、次のエラーを説明します。</span><span class="sxs-lookup"><span data-stu-id="204a6-142">The adapter gives the following error while retrieving XML output that has more than 65536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="204a6-143">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-143">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-144">アダプターは、シリアル化および 65536 以上の項目を含むオブジェクトを逆シリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="204a6-144">The adapter cannot serialize and deserialize an object with more than 65536 items.</span></span>  
  
 <span data-ttu-id="204a6-145">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-145">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-146">この問題を解決するには、設定、`maxItemsInObjectGraph`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="204a6-146">You can fix this issue by setting the `maxItemsInObjectGraph` parameter.</span></span> <span data-ttu-id="204a6-147">これは、次の 2 つの方法のいずれかで設定できます。</span><span class="sxs-lookup"><span data-stu-id="204a6-147">You can set this in any of the following two ways:</span></span>  
  
-   <span data-ttu-id="204a6-148">このパラメーターを変更することによって設定、`maxItemsInObjectGraph`内のパラメーター、`ServiceBehavior`サービス クラスの属性です。</span><span class="sxs-lookup"><span data-stu-id="204a6-148">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
-   <span data-ttu-id="204a6-149">次のアプリケーションの app.config ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="204a6-149">Add the following to your application's app.config file.</span></span>  
  
    ```  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="NewBehavior">  
          <dataContractSerializer maxItemsInObjectGraph="65536000" />  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    ```  
  
 <span data-ttu-id="204a6-150">サンプルの app.config をようになります。</span><span class="sxs-lookup"><span data-stu-id="204a6-150">A sample app.config will look like:</span></span>  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="siebelBinding"  
       contract="IOutboundContract" name="siebel_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_SiebelConnURI"></a><span data-ttu-id="204a6-151">Biztalk WCF カスタム ポートの接続 URI を指定する際にエラー</span><span class="sxs-lookup"><span data-stu-id="204a6-151">Error while specifying a connection URI for a WCF-Custom port in BizTalk</span></span>  
 <span data-ttu-id="204a6-152">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-152">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="204a6-153">接続の Siebel システムへの接続に URI を指定する場合は、次のエラーを得られます。</span><span class="sxs-lookup"><span data-stu-id="204a6-153"> gives the following error when you specify a connection URI to connect to the Siebel system.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="204a6-154">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-154">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-155">接続 URI は、標準のエンコード形式には従っていません。</span><span class="sxs-lookup"><span data-stu-id="204a6-155">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="204a6-156">たとえば、パラメーターの値にスペースを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="204a6-156">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="204a6-157">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-157">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-158">接続を指定する URI は、標準のエンコード形式に準拠して確認します。</span><span class="sxs-lookup"><span data-stu-id="204a6-158">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="204a6-159">たとえば、"%20"空白を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="204a6-159">For example, a blank space must be replaced by "%20".</span></span>  
  
###  <a name="BKMK_SiebelPerfOps"></a><span data-ttu-id="204a6-160">Siebel システムに対する演算を実行中のエラー</span><span class="sxs-lookup"><span data-stu-id="204a6-160">Error while performing operation on the Siebel system</span></span>  
 <span data-ttu-id="204a6-161">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-161">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-162">Siebel システムを使用して、すべての操作を実行するときに、アダプターは、次のエラーを[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="204a6-162">The adapter gives the following error when performing any operation on the Siebel system using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="204a6-163">**BizTalk server**</span><span class="sxs-lookup"><span data-stu-id="204a6-163">**For BizTalk Server**</span></span>  
  
    ```  
    System.ArgumentNullException: Value cannot be null.  
    ```  
  
 <span data-ttu-id="204a6-164">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-164">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-165">メッセージの WCF アクションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="204a6-165">The WCF action for the message is not specified.</span></span> <span data-ttu-id="204a6-166">WCF には、すべての操作では、LOB アプリケーション上で実行される操作について、アダプターに通知を指定する SOAP アクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="204a6-166">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
 <span data-ttu-id="204a6-167">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-167">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-168">送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="204a6-168">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="204a6-169">手順については、次を参照してください。 [Siebel の SOAP アクションを構成する](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md)です。</span><span class="sxs-lookup"><span data-stu-id="204a6-169">For instructions, see [Configure the SOAP action for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-soap-action-for-siebel.md).</span></span> <span data-ttu-id="204a6-170">参照してください[メッセージおよびメッセージ スキーマ](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)各操作のアクションの一覧についてはします。</span><span class="sxs-lookup"><span data-stu-id="204a6-170">See [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md) for a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_SiebelXmlParsing"></a><span data-ttu-id="204a6-171">正しくない操作名が指定したアクションで XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="204a6-171">XmlReaderParsingException due to an incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="204a6-172">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-172">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-173">BizTalk Server 管理コンソールは、Siebel システムにメッセージを送信するときに、次のエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="204a6-173">The BizTalk Server Administration console gives the following error when sending messages to a Siebel system:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="204a6-174">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-174">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-175">によって作成されたポートのバインド ファイルをインポートすることによって、WCF カスタム ポートを構成する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートのアクションは、次の形式で指定されます。</span><span class="sxs-lookup"><span data-stu-id="204a6-175">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="204a6-176">上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="204a6-176">In the preceding format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="204a6-177">Siebel ビジネス コンポーネントでクエリ操作のスキーマを生成した場合など、アクションで操作名では、「クエリ」になります。</span><span class="sxs-lookup"><span data-stu-id="204a6-177">For example, if you generated schema for a Query operation on a Siebel business component, the operation name in the action will be "Query".</span></span> <span data-ttu-id="204a6-178">ただし、論理ポートにある操作名で BizTalk オーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="204a6-178">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="204a6-179">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-179">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-180">確認操作名の両方、論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) と物理ポート (BizTalk Server 管理コンソール) が同じです。</span><span class="sxs-lookup"><span data-stu-id="204a6-180">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration console) are the same.</span></span>  
  
###  <a name="BKMK_SiebelTerminate"></a><span data-ttu-id="204a6-181">Siebel アダプターを使用してアプリケーションを終了しません。</span><span class="sxs-lookup"><span data-stu-id="204a6-181">Application using the Siebel adapter does not terminate</span></span>  
 <span data-ttu-id="204a6-182">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-182">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-183">使用するアプリケーション、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel とクライアント バージョン 7.5 を終了しません。</span><span class="sxs-lookup"><span data-stu-id="204a6-183">An application that uses the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Siebel client version 7.5 does not terminate.</span></span>  
  
 <span data-ttu-id="204a6-184">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-184">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-185">これは、Siebel クライアントの問題により、プロセスを終了しません Siebel サーバーからログオフするときです。</span><span class="sxs-lookup"><span data-stu-id="204a6-185">This is because of a Siebel client issue where the process does not terminate when logging off from a Siebel server.</span></span>  
  
 <span data-ttu-id="204a6-186">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-186">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-187">7.5.3.17 クイック フィックス QF0H05 と共に、Siebel サーバー用にインストールされた更新プログラムがあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="204a6-187">Make sure you have the patch 7.5.3.17 installed for the Siebel server, along with the quick fix QF0H05.</span></span>  
  
###  <a name="BKMK_SiebelHang"></a><span data-ttu-id="204a6-188">Siebel アダプターがハングする Siebel サーバーが再起動した場合</span><span class="sxs-lookup"><span data-stu-id="204a6-188">Siebel adapter may hang if the Siebel server is restarted</span></span>  
 <span data-ttu-id="204a6-189">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-189">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-190">場合は、Siebel サーバーを再起動中に、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel サーバーを使用するメッセージを送信する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]ハングする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="204a6-190">If the Siebel server is restarted while the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is sending a message to the Siebel server using, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] may hang.</span></span>  
  
 <span data-ttu-id="204a6-191">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-191">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-192">BizTalk アプリケーションのホスト インスタンスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="204a6-192">Restart the BizTalk application host instance.</span></span> <span data-ttu-id="204a6-193">これを行うに、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールのコンソール ツリーで  **BizTalk グループ**、展開**プラットフォームの設定**、クリックして**ホスト インスタンス**です。</span><span class="sxs-lookup"><span data-stu-id="204a6-193">To do so from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, in the console tree expand **BizTalk Group**, expand **Platform Settings**, and then click **Host Instances**.</span></span> <span data-ttu-id="204a6-194">右側のウィンドウからホスト名を右クリックし、**再起動**です。</span><span class="sxs-lookup"><span data-stu-id="204a6-194">From the right pane, right-click the host name, and then select **Restart**.</span></span>  
  
###  <a name="BKMK_SiebelAction"></a><span data-ttu-id="204a6-195">アダプター サービスのアドインで生成されたバインド ファイルを使用して、ポートを作成する場合でも、アダプターで物理ポートのアクションが認識されません。</span><span class="sxs-lookup"><span data-stu-id="204a6-195">The adapter does not recognize the action on the physical port even though you use the binding file generated by the Consume Adapter Service add-in to create the ports</span></span>  
 <span data-ttu-id="204a6-196">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-196">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-197">使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Siebel システムで特定の操作のスキーマを生成するには、アドインでもポート バインド ファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="204a6-197">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the Siebel system, the add-in also creates a port binding file.</span></span> <span data-ttu-id="204a6-198">インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server での物理ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="204a6-198">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="204a6-199">ただし、このようなポートを使用して、Siebel システムにメッセージを送信するときに、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。</span><span class="sxs-lookup"><span data-stu-id="204a6-199">However, when you send messages to the Siebel system using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="204a6-200">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-200">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-201">BizTalk オーケストレーションの論理ポートを作成するときにそれらのポートでの操作の特定の名前を指定するか、Operation_1、Operation_2 などのように既定の名前に使用します。ただし、によって生成されたバインド ファイルでは、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する操作の名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="204a6-201">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the operation for which you generate metadata.</span></span> <span data-ttu-id="204a6-202">たとえば、アカウント ビジネス コンポーネントに対する挿入操作のメタデータを生成する場合、次に、アクションは設定されます。</span><span class="sxs-lookup"><span data-stu-id="204a6-202">For example, if you generate metadata for Insert operation on the Account business component, the action will be set to the following:</span></span>  
  
```  
<Operation Name="Insert" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
```  
  
 <span data-ttu-id="204a6-203">バインド ファイルをインポートするときに、同じアクションは物理ポートに設定されます。</span><span class="sxs-lookup"><span data-stu-id="204a6-203">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="204a6-204">そのため、論理ポート ([operation_1]、Operation_2 など) での操作名では、エラーが発生しましたの物理ポートのアクションで指定した操作名が一致しません。</span><span class="sxs-lookup"><span data-stu-id="204a6-204">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="204a6-205">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-205">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-206">論理ポートにある操作名は、物理ポートにアクションの一部として指定された操作名と同じことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="204a6-206">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="204a6-207">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="204a6-207">Do one of the following:</span></span>  
  
-   <span data-ttu-id="204a6-208">Insert の例については、メタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートにある操作名を変更します。</span><span class="sxs-lookup"><span data-stu-id="204a6-208">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example Insert.</span></span>  
  
-   <span data-ttu-id="204a6-209">論理ポートでの操作名には、物理ポートのアクションで、操作名を変更します。</span><span class="sxs-lookup"><span data-stu-id="204a6-209">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="204a6-210">たとえば、次のように物理ポートにアクションを変更します。</span><span class="sxs-lookup"><span data-stu-id="204a6-210">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert" />  
    ```  
  
###  <a name="BKMK_SiebelXMLEncode"></a><span data-ttu-id="204a6-211">Siebel アダプターは、名前の XML でエンコードされた文字列が Siebel オブジェクトを処理しません</span><span class="sxs-lookup"><span data-stu-id="204a6-211">Siebel adapter does not handle Siebel objects with XML encoded strings in the name</span></span>  
 <span data-ttu-id="204a6-212">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-212">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-213">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]を名前にエンコードされた XML 文字列を持つ Siebel オブジェクト (ビジネス オブジェクト、ビジネス コンポーネント、ビジネス サービス、候補リスト、メソッド、フィールド、引数など) に関連する操作を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="204a6-213">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] cannot perform operations involving Siebel objects (business objects, business components, business services, picklist, methods, fields, arguments, etc) that have XML encoded strings in their name.</span></span> <span data-ttu-id="204a6-214">たとえば、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]名前 Time_x0020_Stamp のビジネス サービス メソッドを呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="204a6-214">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] will not be able to invoke a business service method with the name Time_x0020_Stamp.</span></span>  
  
 <span data-ttu-id="204a6-215">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-215">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-216">Siebel オブジェクトには、名前にエンコードされた XML 文字列が含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="204a6-216">Make sure the Siebel objects do not contain XML encoded strings in their name.</span></span>  
  
###  <a name="BKMK_SiebelRootNode"></a><span data-ttu-id="204a6-217">RootNode TypeName BizTalk プロジェクト内のエラー</span><span class="sxs-lookup"><span data-stu-id="204a6-217">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="204a6-218">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-218">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-219">BizTalk プロジェクトに[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:</span><span class="sxs-lookup"><span data-stu-id="204a6-219">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="204a6-220">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-220">**Resolution**</span></span>  
  
1.  <span data-ttu-id="204a6-221">クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="204a6-221">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="204a6-222">**RootNode TypeName**プロパティ、無効な文字を削除するまたは予約語、たとえば、ドット (.) です。</span><span class="sxs-lookup"><span data-stu-id="204a6-222">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_SiebelVS2008"></a><span data-ttu-id="204a6-223">Visual Studio でのアダプターの使用時の無効なバインドの警告</span><span class="sxs-lookup"><span data-stu-id="204a6-223">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="204a6-224">**問題**</span><span class="sxs-lookup"><span data-stu-id="204a6-224">**Problem**</span></span>  
  
 <span data-ttu-id="204a6-225">Visual Studio でアプリケーションを作成するアダプターを使用して、アダプターによって生成された構成ファイル (app.config) を開くと、次のような警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="204a6-225">When you use the adapter to create an application in Visual Studio and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'siebelBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="204a6-226">**原因**</span><span class="sxs-lookup"><span data-stu-id="204a6-226">**Cause**</span></span>  
  
 <span data-ttu-id="204a6-227">この警告が表示されます、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]バインド、`siebelBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="204a6-227">This warning appears because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] binding, `siebelBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="204a6-228">**解決策**</span><span class="sxs-lookup"><span data-stu-id="204a6-228">**Resolution**</span></span>  
  
 <span data-ttu-id="204a6-229">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="204a6-229">You can safely ignore this warning.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="204a6-230">参照</span><span class="sxs-lookup"><span data-stu-id="204a6-230">See Also</span></span>  
[<span data-ttu-id="204a6-231">Siebel アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="204a6-231">Troubleshoot the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/troubleshoot-the-siebel-adapter.md)