---
title: Oracle データベース アダプターを使用した運用上の問題のトラブルシューティング |Microsoft Docs
description: 一般的な問題と Oracle データベース アダプターの BizTalk アダプター パック (BAP) の解決策
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fb83245-2b6a-48cc-8601-b923bb009a58
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13dfe903e897ebc3d26e6dc380233f80253ddfc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968419"
---
# <a name="troubleshoot-operational-issues-with-the-oracle-database-adapter"></a><span data-ttu-id="73653-103">Oracle データベース アダプターを使用した運用上の問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="73653-103">Troubleshoot operational issues with the Oracle Database adapter</span></span>
<span data-ttu-id="73653-104">トラブルシューティングの手法を使用して発生する可能性がある操作のエラーを解決するのには[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73653-104">Troubleshooting techniques to resolve operational errors that you may experience using [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>  
  
## <a name="enable-tracing"></a><span data-ttu-id="73653-105">トレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="73653-105">Enable tracing</span></span>  
 <span data-ttu-id="73653-106">トレースのサポートについては、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[診断トレースとメッセージ ログの Oracle データベース アダプター](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="73653-106">For information about tracing support in the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Diagnostic tracing and message logging for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/diagnostic-tracing-and-message-logging-for-the-oracle-database-adapter.md).</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="73653-107">既知の問題</span><span class="sxs-lookup"><span data-stu-id="73653-107">Known Issues</span></span>  
 <span data-ttu-id="73653-108">使用する場合に発生する可能性が最も一般的なエラーを次に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]と共に、考えられる原因と解決します。</span><span class="sxs-lookup"><span data-stu-id="73653-108">The following are the most common errors you might encounter when using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], along with their probable cause and resolution.</span></span>   
  
### <a name="BKMK_OraDBLoading"></a> <span data-ttu-id="73653-109">アダプターのバインドを読み込み中にエラー</span><span class="sxs-lookup"><span data-stu-id="73653-109">Error in loading the adapter bindings</span></span>  
 <span data-ttu-id="73653-110">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-110">**Problem**</span></span>  
  
 <span data-ttu-id="73653-111">開始しようとすると、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]、次のエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="73653-111">When you try to start the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], you get the following error:</span></span>  
  
```  
There was an error loading the binding, <binding name>, from your system configuration.  
ConfigurationErrorsException: Exception has been thrown by the target of an invocation.  
```  
  
 <span data-ttu-id="73653-112">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-112">**Cause**</span></span>  
  
 <span data-ttu-id="73653-113">開始しようとすると、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]WCF がインストールされているすべてのアダプターのアダプターのバインドを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="73653-113">When you try to start the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], WCF loads the adapter bindings for all the installed adapters.</span></span> <span data-ttu-id="73653-114">さらに、アダプターのバインドは、エンタープライズ アプリケーションの特定のクライアント ソフトウェアに依存します。</span><span class="sxs-lookup"><span data-stu-id="73653-114">In turn, the adapter bindings are dependent on the specific client software for the enterprise application.</span></span> <span data-ttu-id="73653-115">この問題は次の理由の両方またはいずれかに直面する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73653-115">You might face this issue for one or both of the following reasons:</span></span>  
  
- <span data-ttu-id="73653-116">アダプターがインストールされているコンピューターでは、必要な LOB クライアント ソフトウェアがインストールされていません。</span><span class="sxs-lookup"><span data-stu-id="73653-116">The required LOB client software is not installed on the computer where you installed the adapter.</span></span>  
  
- <span data-ttu-id="73653-117">含まれているすべてのアダプターをインストールすると、アダプターのインストールを標準または完了した、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73653-117">You did a Typical or Complete installation of the adapter, which installs all the adapters contained in the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="73653-118">ただし、1 つだけのエンタープライズ アプリケーション用に LOB クライアント ライブラリをインストールする場合があります。</span><span class="sxs-lookup"><span data-stu-id="73653-118">However, the LOB client libraries might be installed for only one enterprise application.</span></span> <span data-ttu-id="73653-119">その結果、GUI の他のアダプターのバインドの読み込みに失敗します。</span><span class="sxs-lookup"><span data-stu-id="73653-119">As a result, the GUI fails to load the bindings for the other adapters.</span></span>  
  
  <span data-ttu-id="73653-120">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-120">**Resolution**</span></span>  
  
- <span data-ttu-id="73653-121">必要な LOB クライアント バージョンがインストールされているコンピューターにインストールされていることを確認、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73653-121">Make sure that the required LOB client versions are installed on the computer where you installed the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="73653-122">[サポートされている基幹業務 (LOB) とエンタープライズ システム](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)サポートされているクライアント バージョンを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="73653-122">[Supported Line-of-Business (LOB) and Enterprise systems](https://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx) lists the supported client versions.</span></span>  
  
- <span data-ttu-id="73653-123">必要なアダプターのみをインストールするアダプターのカスタム インストールを実行することを確認します。</span><span class="sxs-lookup"><span data-stu-id="73653-123">Make sure you do a custom installation of the adapters to install only the adapter you need.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="73653-124">ODP.NET の最新バージョンで、アプリケーションの動作を確認するには、"ポリシー Dll"コンピューターにインストールされているし、GAC に登録が必要です。</span><span class="sxs-lookup"><span data-stu-id="73653-124">To make sure your application works with the most recent version of ODP.NET, you must have the "policy DLLs" installed on the computer and registered in the GAC.</span></span> <span data-ttu-id="73653-125">詳細については、次を参照してください。 [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) Oracle の web サイト。</span><span class="sxs-lookup"><span data-stu-id="73653-125">For more information, see [Oracle Data Provider for .NET](http://go.microsoft.com/fwlink/p/?LinkId=92834) on Oracle's website.</span></span>  
  
###  <a name="BKMK_OraDBAdapDisplay"></a> <span data-ttu-id="73653-126">Oracle データベース アダプターは BizTalk Server 管理コンソールでアダプタの一覧に表示されません。</span><span class="sxs-lookup"><span data-stu-id="73653-126">The Oracle database adapter does not display in the list of adapters in BizTalk Server Administration console</span></span>  
 <span data-ttu-id="73653-127">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-127">**Problem**</span></span>  
  
<span data-ttu-id="73653-128">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]付属しています[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]BizTalk Server 管理コンソールでアダプタの一覧にも記載されていません。</span><span class="sxs-lookup"><span data-stu-id="73653-128">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] inlcuded with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is not listed in the list of adapters in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="73653-129">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-129">**Cause**</span></span>  
  
 <span data-ttu-id="73653-130">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] WCF カスタム バインドします。</span><span class="sxs-lookup"><span data-stu-id="73653-130">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] is a WCF custom binding.</span></span> <span data-ttu-id="73653-131">そのため、ですが、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールが表示されます、 [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)]、WCF カスタム バインドは表示されませんし、そのため、表示されない WCF ベース[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73653-131">So, although the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console displays the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], it does not display the WCF custom bindings and hence, does not display the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="73653-132">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-132">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-133">明示的に追加することができます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]次で説明されている手順に従って、管理コンソール[を BizTalk Server 管理コンソールの Oracle データベース アダプターの追加](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)します。</span><span class="sxs-lookup"><span data-stu-id="73653-133">You can explicitly add the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by following the steps mentioned in [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
###  <a name="BKMK_OraDBXMLRetrieve"></a> <span data-ttu-id="73653-134">65,536 個を超えるノードを持つ XML 出力の取得中にエラー</span><span class="sxs-lookup"><span data-stu-id="73653-134">Error while retrieving XML output with more than 65,536 nodes</span></span>  
 <span data-ttu-id="73653-135">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-135">**Problem**</span></span>  
  
 <span data-ttu-id="73653-136">アダプターは、65,536 を超えるノードを持つ出力 XML を取得するときに、次のエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="73653-136">The adapter gives the following error when retrieving XML output that has more than 65,536 nodes.</span></span>  
  
```  
Maximum number of items that can be serialized or deserialized in an object graph is '65536'.  
Change the object graph or increase the MaxItemsInObjectGraph quota.  
```  
  
 <span data-ttu-id="73653-137">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-137">**Cause**</span></span>  
  
 <span data-ttu-id="73653-138">アダプターは、シリアル化し、65,536 を超える項目を含むオブジェクトを逆シリアル化できません。</span><span class="sxs-lookup"><span data-stu-id="73653-138">The adapter cannot serialize and deserialize an object with more than 65,536 items.</span></span>  
  
 <span data-ttu-id="73653-139">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-139">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-140">この問題を解決するには、設定して、`maxItemsInObjectGraph`パラメーター。</span><span class="sxs-lookup"><span data-stu-id="73653-140">You can fix this issue by setting the `maxItemsInObjectGraph` parameter.</span></span> <span data-ttu-id="73653-141">これは、次の 2 つの方法のいずれかで設定できます。</span><span class="sxs-lookup"><span data-stu-id="73653-141">You can set this in either of the following two ways:</span></span>  
  
- <span data-ttu-id="73653-142">変更することで、このパラメーターを設定、`maxItemsInObjectGraph`パラメーター、`ServiceBehavior`サービス クラスの属性。</span><span class="sxs-lookup"><span data-stu-id="73653-142">Set this parameter by changing the `maxItemsInObjectGraph` parameter in the `ServiceBehavior` attribute on your service class.</span></span>  
  
- <span data-ttu-id="73653-143">次のアプリケーションの app.config ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="73653-143">Add the following to your application's app.config file.</span></span>  
  
  ```  
  <behaviors>  
    <endpointBehaviors>  
      <behavior name="NewBehavior">  
        <dataContractSerializer maxItemsInObjectGraph="65536000" />  
      </behavior>  
    </endpointBehaviors>  
  </behaviors>  
  ```  
  
  <span data-ttu-id="73653-144">サンプルの app.config では、次のように検索します。</span><span class="sxs-lookup"><span data-stu-id="73653-144">A sample app.config looks like this.</span></span>  
  
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
      <endpoint   behaviorConfiguration="NewBehavior" binding="oracleDBBinding"  
       contract="IOutboundContract" name="oracle_ICalculator" />  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
###  <a name="BKMK_OraDBPerfOps"></a> <span data-ttu-id="73653-145">Oracle データベースに対する操作の実行中のエラー</span><span class="sxs-lookup"><span data-stu-id="73653-145">Error while performing operations on the Oracle database</span></span>  
 <span data-ttu-id="73653-146">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-146">**Problem**</span></span>  
  
 <span data-ttu-id="73653-147">使用して Oracle データベースに対して任意の操作を実行するときに、アダプターでは、次のエラー[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73653-147">The adapter gives the following error when performing any operation on the Oracle database using [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="73653-148">**BizTalk Server 用**</span><span class="sxs-lookup"><span data-stu-id="73653-148">**For BizTalk Server**</span></span>  
  
  ```  
  System.ArgumentNullException: Value cannot be null.  
  ```  
  
  <span data-ttu-id="73653-149">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-149">**Cause**</span></span>  
  
  <span data-ttu-id="73653-150">メッセージの WCF アクションが指定されていません。</span><span class="sxs-lookup"><span data-stu-id="73653-150">The WCF action for the message is not specified.</span></span> <span data-ttu-id="73653-151">WCF では、すべての操作では、LOB アプリケーションで実行する操作について、アダプターに通知を指定した SOAP アクションが必要です。</span><span class="sxs-lookup"><span data-stu-id="73653-151">WCF requires a SOAP action to be specified for every operation, which informs the adapter about the operation to be performed on the LOB application.</span></span>  
  
  <span data-ttu-id="73653-152">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-152">**Resolution**</span></span>  
  
  <span data-ttu-id="73653-153">送信ポートまたは BizTalk オーケストレーションでメッセージ コンテキスト プロパティとしては、SOAP アクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="73653-153">Specify the SOAP action in the send port or as a message context property in a BizTalk orchestration.</span></span> <span data-ttu-id="73653-154">手順については、[Oracle データベースの SOAP アクションを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73653-154">For instructions, see [Configure the SOAP action for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-soap-action-for-oracle-database.md).</span></span> <span data-ttu-id="73653-155">参照してください[メッセージとメッセージ スキーマ](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)各操作のアクションの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="73653-155">See [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md) to see a list of actions for each operation.</span></span>  
  
###  <a name="BKMK_OraDBXmlParsing"></a> <span data-ttu-id="73653-156">指定したアクションで、正しくない操作名により XmlReaderParsingException</span><span class="sxs-lookup"><span data-stu-id="73653-156">XmlReaderParsingException due to an incorrect operation name in the specified action</span></span>  
 <span data-ttu-id="73653-157">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-157">**Problem**</span></span>  
  
 <span data-ttu-id="73653-158">BizTalk Server 管理コンソールは、Oracle データベースにメッセージを送信するときに、次のエラーを示します。</span><span class="sxs-lookup"><span data-stu-id="73653-158">The BizTalk Server Administration Console gives the following error when sending messages to an Oracle database:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.XmlReaderParsingException: Invalid argument:  
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<operation_name>" Action="<action>" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="73653-159">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-159">**Cause**</span></span>  
  
 <span data-ttu-id="73653-160">によって作成されたポートのバインド ファイルをインポートして WCF カスタム ポートを構成する場合、[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]ポートのアクションは、次の形式で指定されます。</span><span class="sxs-lookup"><span data-stu-id="73653-160">If you configure a WCF-Custom port by importing the port binding file created by the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)], the action in the port is specified in the following format:</span></span>  
  
```  
<BtsActionMapping>  
  <Operation Name="Op1" Action="http://MyService/Svc/Op1" />  
</BtsActionMapping>  
```  
  
 <span data-ttu-id="73653-161">上記の形式では、操作名は、スキーマの生成中に選択した操作によって管理されます。</span><span class="sxs-lookup"><span data-stu-id="73653-161">In the above format, the operation name is governed by the operation you chose while generating the schema.</span></span> <span data-ttu-id="73653-162">たとえば、テーブルに対する挿入操作のスキーマを生成すると、アクションで、操作名が、"Insert"になります。</span><span class="sxs-lookup"><span data-stu-id="73653-162">For example, if you generated schema for the Insert operation on a table, the operation name in the action will be "Insert".</span></span> <span data-ttu-id="73653-163">ただし、論理ポートの操作名が BizTalk のオーケストレーションで作成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73653-163">However, the operation name in the logical port created in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] might be different.</span></span>  
  
 <span data-ttu-id="73653-164">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-164">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-165">確実に操作名の両方の論理ポート (BizTalk のオーケストレーションで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) (BizTalk Server 管理コンソール) で物理ポートが同じであるとします。</span><span class="sxs-lookup"><span data-stu-id="73653-165">Make sure the operation names in both the logical port (in the BizTalk orchestration in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]) and the physical port (in BizTalk Server Administration Console) are same.</span></span>  
  
###  <a name="BKMK_OraDBConnURI"></a> <span data-ttu-id="73653-166">Biztalk WCF カスタム ポートの接続 URI を指定するときにエラー</span><span class="sxs-lookup"><span data-stu-id="73653-166">Error while specifying a connection URI for a WCF-Custom port in BizTalk</span></span>  
 <span data-ttu-id="73653-167">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-167">**Problem**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="73653-168">接続、Oracle データベースに接続するための URI を指定する場合は、次のエラーを得られます。</span><span class="sxs-lookup"><span data-stu-id="73653-168">gives the following error when you specify a connection URI to connect to the Oracle database.</span></span>  
  
```  
Error saving properties.  
(System.ArgumentException) The specified address is invalid.  
(System.ArgumentException) Invalid address;  
"<connection URI>" is not a well-formed absolute uri.  
```  
  
 <span data-ttu-id="73653-169">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-169">**Cause**</span></span>  
  
 <span data-ttu-id="73653-170">接続 URI は標準のエンコード形式に準拠していません。</span><span class="sxs-lookup"><span data-stu-id="73653-170">The connection URI does not adhere to the standard encoding format.</span></span> <span data-ttu-id="73653-171">たとえば、パラメーターの値にスペースを含めることがあります。</span><span class="sxs-lookup"><span data-stu-id="73653-171">For example, the value for a parameter might contain a space.</span></span>  
  
 <span data-ttu-id="73653-172">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-172">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-173">指定した URI は、標準のエンコード形式に準拠する接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="73653-173">Make sure the connection URI you specify adheres to the standard encoding format.</span></span> <span data-ttu-id="73653-174">たとえば、"%20"を空白の領域を置き換える必要があります。</span><span class="sxs-lookup"><span data-stu-id="73653-174">For example, a blank space must be replaced by "%20".</span></span>  
  
###  <a name="BKMK_OraDBInvalCursor"></a> <span data-ttu-id="73653-175">REF CURSOR パラメーターを受け取るストアド プロシージャの呼び出し中に無効なカーソル例外</span><span class="sxs-lookup"><span data-stu-id="73653-175">Invalid cursor exception while invoking stored procedures that take REF CURSOR parameters</span></span>  
 <span data-ttu-id="73653-176">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-176">**Problem**</span></span>  
  
 <span data-ttu-id="73653-177">REF CURSOR の入力を受け取る、Oracle データベースでプロシージャを呼び出すと、次の例外が発生可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73653-177">When you invoke procedures in the Oracle database that take REF CURSOR inputs, you might get the following exception:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.TargetSystemException: ORA-01001: invalid cursor ---> Oracle.DataAccess.Client.OracleException  
```  
  
 <span data-ttu-id="73653-178">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-178">**Cause**</span></span>  
  
 <span data-ttu-id="73653-179">REF Cursor PL/SQL のブロックを呼び出しているプロシージャをパイプ処理できますは、IN の REF CURSOR でしたの取得に割り当てられますアウト REF カーソル。</span><span class="sxs-lookup"><span data-stu-id="73653-179">The PL/SQL block for the procedure that you are invoking could be piping the REF CURSORs, that is, the IN REF CURSOR could be getting assigned to the OUT REF CURSOR.</span></span>  
  
 <span data-ttu-id="73653-180">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-180">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-181">PL/SQL ブロックは、適切な処理を行わなくても OUT REF Cursor をパイプしない必要があります。</span><span class="sxs-lookup"><span data-stu-id="73653-181">The PL/SQL block must not pipe the IN to the OUT REF CURSORs without proper processing.</span></span>  
  
###  <a name="BKMK_OraDBValidateResp"></a> <span data-ttu-id="73653-182">BizTalk Server を使用して、ReadLOB 操作に対する応答の検証中にエラー</span><span class="sxs-lookup"><span data-stu-id="73653-182">Error while validating the response for the ReadLOB operation using BizTalk Server</span></span>  
 <span data-ttu-id="73653-183">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-183">**Problem**</span></span>  
  
 <span data-ttu-id="73653-184">使用して ReadLOB 操作の実行中に、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、Oracle データベースからの応答が Web サービス記述言語 (WSDL) に対して検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="73653-184">While performing a ReadLOB operation using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], the response from the Oracle database fails validation against the Web Services Description Language (WSDL).</span></span>  
  
 <span data-ttu-id="73653-185">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-185">**Cause**</span></span>  
  
 <span data-ttu-id="73653-186">WSDL には、サービス ベースの要求の実行が定義されているが、BizTalk のシナリオは必要ありません StreamBody ノード名が含まれています。</span><span class="sxs-lookup"><span data-stu-id="73653-186">The WSDL contains a StreamBody node name that is defined for execution of service-based requests, but is not needed for BizTalk scenarios.</span></span> <span data-ttu-id="73653-187">そのため、XML で、StreamBody ノードが含まれていませんが、出力は、WSDL と比較すると、検証は失敗します。</span><span class="sxs-lookup"><span data-stu-id="73653-187">Therefore, when the output XML, which does not contain the StreamBody node, is compared with the WSDL, validation fails.</span></span>  
  
 <span data-ttu-id="73653-188">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-188">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-189">BizTalk Server を使用して生成された出力結果に対して検証するときに、WSDL から StreamBody ノードを削除します。</span><span class="sxs-lookup"><span data-stu-id="73653-189">Remove the StreamBody node from the WSDL when validating against the output that was generated using BizTalk Server.</span></span> <span data-ttu-id="73653-190">そのためには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="73653-190">Perform the following steps to do so:</span></span>  
  
1. <span data-ttu-id="73653-191">StreamBody ノードを含む WSDL は、次のように検索します。</span><span class="sxs-lookup"><span data-stu-id="73653-191">The WSDL containing the StreamBody node looks like this.</span></span>  
  
   ```  
   <xs:element name="ReadLOBResponse">  
       <xs:annotation>  
         <xs:documentation>  
           <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>  
         </xs:documentation>  
       </xs:annotation>  
       <xs:complexType>  
         <xs:sequence>  
           <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" nillable="true" type="ns3:StreamBody" />  
         </xs:sequence>  
       </xs:complexType>  
     </xs:element>  
   ```  
  
    <span data-ttu-id="73653-192">次のように、前に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="73653-192">Replace the preceding with the following.</span></span>  
  
   ```  
   <xs:element name="ReadLOBResponse">  
    <xs:annotation>  
    <xs:documentation>  
     <doc:action xmlns:doc="http://schemas.microsoft.com/servicemodel/adapters/metadata/documentation">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/TBL_ALL_DATATYPES/ReadLOB/response\</doc:action>   
     </xs:documentation>  
     </xs:annotation>  
    <xs:complexType>  
    <xs:sequence>  
     <xs:element minOccurs="1" maxOccurs="1" name="ReadLOBResult" type="xs:base64Binary" />   
     </xs:sequence>  
     </xs:complexType>  
     </xs:element>  
   ```  
  
    <span data-ttu-id="73653-193">型への参照を削除するこの手順で元の XSD では、"ns3:StreamBody"= し、型に置き換え"xs:base64Binary"を = です。</span><span class="sxs-lookup"><span data-stu-id="73653-193">In this step, you removed the reference to type="ns3:StreamBody" in the original XSD and replaced it with type="xs:base64Binary".</span></span> <span data-ttu-id="73653-194">また、元の XSD から nillable ="true"の値を削除します。</span><span class="sxs-lookup"><span data-stu-id="73653-194">Also, you removed the nillable="true" value from the original XSD.</span></span>  
  
2. <span data-ttu-id="73653-195">次は、WSDL から削除します。</span><span class="sxs-lookup"><span data-stu-id="73653-195">Remove the following from the WSDL.</span></span>  
  
   ```  
   <xs:complexType name="StreamBody">  
       <xs:sequence>  
         <xs:element minOccurs="1" maxOccurs="1" name="Stream">  
           <xs:simpleType>  
             <xs:restriction base="xs:base64Binary">  
               <xs:minLength value="0" />  
             </xs:restriction>  
           </xs:simpleType>  
         </xs:element>  
       </xs:sequence>  
     </xs:complexType>  
     <xs:element name="StreamBody" nillable="true" type="ns3:StreamBody" />  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="73653-196">ReadLOB 操作はサポートされていません[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73653-196">ReadLOB operation is not supported with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="73653-197">LOB データを読み取るテーブルの選択操作を使用する必要があります、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]ソリューション。</span><span class="sxs-lookup"><span data-stu-id="73653-197">You should use a table Select operation to read LOB data from a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
###  <a name="BKMK_OraDBSchemaValidateFail"></a> <span data-ttu-id="73653-198">ポーリングのシナリオでスキーマの検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="73653-198">Schema validation may fail in polling scenarios</span></span>  
 <span data-ttu-id="73653-199">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-199">**Problem**</span></span>  
  
 <span data-ttu-id="73653-200">シナリオでスキーマの検証に失敗した場所、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]データベース ROWID または UNROWID 型のフィールドが含まれているテーブルをポーリングします。</span><span class="sxs-lookup"><span data-stu-id="73653-200">Schema validation fails in scenarios where the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] polls database tables that contain fields of type ROWID or UNROWID.</span></span>  
  
 <span data-ttu-id="73653-201">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-201">**Cause**</span></span>  
  
 <span data-ttu-id="73653-202">デザイン時に、アダプターは、ROWID または UNROWID、型のフィールドを含むテーブルのメタデータを生成するときに、スキーマが含まれています"nillable = false"、つまり、ROWID または UNROWID 型のフィールドが null にできません。</span><span class="sxs-lookup"><span data-stu-id="73653-202">At design-time, when the adapter generates metadata for the table containing fields of type ROWID or UNROWID, the schema includes “nillable=false”, which means that fields of type ROWID or UNROWID cannot be null.</span></span> <span data-ttu-id="73653-203">ただし、実行時に、アダプターは、メタデータを取得するときに ROWID または UNROWID 型のフィールドの null 値を格納します。</span><span class="sxs-lookup"><span data-stu-id="73653-203">However, at run-time when the adapter retrieves the metadata, the fields of type ROWID or UNROWID contain null values.</span></span> <span data-ttu-id="73653-204">そのため、スキーマの検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="73653-204">Hence the schema validation fails.</span></span>  
  
 <span data-ttu-id="73653-205">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-205">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-206">使用する場合、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]で[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]スキーマの検証を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="73653-206">If you are using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you may choose to disable schema validation.</span></span> <span data-ttu-id="73653-207">スキーマが変更を手動で編集する代わりに、"nillbale = true"ROWID と UNROWID データ型。</span><span class="sxs-lookup"><span data-stu-id="73653-207">Alternatively, you may manually edit the schema to change “nillbale=true” for ROWID and UNROWID data types.</span></span>  
  
###  <a name="BKMK_OraDBUnreasonConv"></a> <span data-ttu-id="73653-208">実行するときに、'要求された不合理変換' エラーでは、パラメーターとしてレコードの種類を使用したプロシージャが格納されています。</span><span class="sxs-lookup"><span data-stu-id="73653-208">'Unreasonable conversion requested' error when executing stored procedures with Record Types as parameters</span></span>  
 <span data-ttu-id="73653-209">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-209">**Cause**</span></span>  
  
 <span data-ttu-id="73653-210">パラメーターとして、Oracle がプロシージャが格納されているシナリオのレコードの種類を検討します。</span><span class="sxs-lookup"><span data-stu-id="73653-210">Consider a scenario where an Oracle stored procedure takes a Record Type as a parameter.</span></span> <span data-ttu-id="73653-211">レコードの種類として宣言されていることを前提としています\<テーブル名\>%rowtype、テーブルと長い形式のデータ型の列があります。</span><span class="sxs-lookup"><span data-stu-id="73653-211">Assume that the Record Type is declared as \<table name\>%ROWTYPE, where the table has a column of LONG data type.</span></span> <span data-ttu-id="73653-212">ときに、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]検出すると長い形式のデータ型、データ型のサイズを指定された値と等しく設定する、 **LongDatatypeColumnSize**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="73653-212">When the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] encounters the LONG data type, it sets the size of the data type equal to the value specified for the **LongDatatypeColumnSize** binding property.</span></span> <span data-ttu-id="73653-213">ただし、Oracle データベースでは、長い形式のデータ型のサイズは定義しません。</span><span class="sxs-lookup"><span data-stu-id="73653-213">However, the Oracle database does not define a size for the LONG data type.</span></span> <span data-ttu-id="73653-214">そのため、アダプターが、ストアド プロシージャを呼び出すときに、'要求された不合理変換' エラーになります。</span><span class="sxs-lookup"><span data-stu-id="73653-214">So, when the adapter invokes the stored procedure, it results in an ‘Unreasonable conversion requested’ error.</span></span>  
  
 <span data-ttu-id="73653-215">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-215">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-216">レコード型の長い形式のデータ型の場合は、パッケージの一部として明示的に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="73653-216">If a Record Type has a LONG data type, you must explicitly define it as part of a package.</span></span>  
  
###  <a name="BKMK_OraDBAdapRecognize"></a> <span data-ttu-id="73653-217">Consume Adapter Service アドインによって生成されたバインド ファイルを使用して、ポートを作成する場合でも、アダプターが物理ポートでアクションを認識しません</span><span class="sxs-lookup"><span data-stu-id="73653-217">The adapter does not recognize the action on the physical port even though you use the binding file generated by the Consume Adapter Service add-in to create the ports</span></span>  
 <span data-ttu-id="73653-218">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-218">**Problem**</span></span>  
  
 <span data-ttu-id="73653-219">使用した後、 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] Oracle データベースで特定の操作のスキーマを生成するアドインも作成ポートのバインド ファイル。</span><span class="sxs-lookup"><span data-stu-id="73653-219">After you use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate schema for a specific operation on the Oracle database, the add-in also creates a port binding file.</span></span> <span data-ttu-id="73653-220">インポートできますこのバインド ファイルを使用して、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールを BizTalk Server で物理ポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="73653-220">You can import this binding file using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console to create physical ports in BizTalk Server.</span></span> <span data-ttu-id="73653-221">ただし、このようなポートを使用して Oracle データベースにメッセージを送信するとき、アダプターがポートで指定したアクションを理解する失敗し、次のようなエラーします。</span><span class="sxs-lookup"><span data-stu-id="73653-221">However, when you send messages to the Oracle database using such ports, the adapter fails to understand the action specified on the port and gives an error similar to the following:</span></span>  
  
```  
Microsoft.ServiceModel.Channels.Common.UnsupportedOperationException: Incorrect Action   
<BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <Operation Name="<op_name>" Action="<action>" />  
</BtsActionMapping>. Correct the specified Action, or refer to the documentation on the allowed formats for the Actions.  
```  
  
 <span data-ttu-id="73653-222">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-222">**Cause**</span></span>  
  
 <span data-ttu-id="73653-223">BizTalk オーケストレーションでの論理ポートを作成するときにこれらのポートの操作に特定の名前を指定または Operation_1、Operation_2 などのように既定の名前を使用します。ただし、によって生成されたバインド ファイルで、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]操作名がメタデータを生成する Oracle データベース操作の名前と同じです。</span><span class="sxs-lookup"><span data-stu-id="73653-223">When you create logical ports in a BizTalk orchestration, you specify certain names for the operations on those ports or you just use the default names like Operation_1, Operation_2, etc. However, in the binding file generated by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], the operation name is same as the name of the Oracle database operation for which you generate metadata.</span></span> <span data-ttu-id="73653-224">たとえば、Oracle データベースで ACCOUNTACTIVITY テーブルに対する Select 操作のメタデータを生成する場合に、次のアクションは設定されます。</span><span class="sxs-lookup"><span data-stu-id="73653-224">For example, if you generate metadata for Select operation on ACCOUNTACTIVITY table in the Oracle database, the action will be set to the following:</span></span>  
  
```  
<Operation Name="Select" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
```  
  
 <span data-ttu-id="73653-225">バインド ファイルをインポートすると、物理ポートで同じアクションが設定されます。</span><span class="sxs-lookup"><span data-stu-id="73653-225">When you import the binding file, the same action is set on physical port.</span></span> <span data-ttu-id="73653-226">そのため、論理ポート (Operation_1、Operation_2 など) の操作名では、エラーが発生する物理ポートで、アクションで指定された操作名が一致しません。</span><span class="sxs-lookup"><span data-stu-id="73653-226">So, the operation names on the logical port (Operation_1, Operation_2, etc.) do not match the operation names specified in the action on the physical port, resulting in an error.</span></span>  
  
 <span data-ttu-id="73653-227">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-227">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-228">論理ポートで操作の名前は、物理ポートにアクションの一部として指定された操作名と同じことを確認します。</span><span class="sxs-lookup"><span data-stu-id="73653-228">Make sure the operation name in the logical port is the same as the operation name specified as part of the action in the physical port.</span></span> <span data-ttu-id="73653-229">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="73653-229">Do one of the following:</span></span>  
  
-   <span data-ttu-id="73653-230">Select の例については、メタデータを生成する操作に Operation_1 などから BizTalk オーケストレーションの論理ポートの操作名を変更します。</span><span class="sxs-lookup"><span data-stu-id="73653-230">Change the operation name in the logical port in BizTalk orchestration from Operation_1, etc. to the operation for which you generate metadata, for example Select.</span></span>  
  
-   <span data-ttu-id="73653-231">論理ポートで、操作名に物理ポートのアクションで、操作名を変更します。</span><span class="sxs-lookup"><span data-stu-id="73653-231">Change the operation name in the action on the physical port to the operation name in the logical port.</span></span> <span data-ttu-id="73653-232">たとえば、次のように物理ポートにアクションを変更できます。</span><span class="sxs-lookup"><span data-stu-id="73653-232">For example, you could change the action in the physical port to resemble the following:</span></span>  
  
    ```  
    <Operation Name="Operation_1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY/Select" />  
    ```  
  
###  <a name="BKMK_OraDBOverflowExcep"></a> <span data-ttu-id="73653-233">アダプターは、操作を実行する方法 ("System.overflowexception:") オーバーフロー例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="73653-233">Adapter throws an overflow exception (“System.OverflowException”) on executing an operation</span></span>  
 <span data-ttu-id="73653-234">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-234">**Problem**</span></span>  
  
 <span data-ttu-id="73653-235">データセットまたは厳密に型指定の REF CURSOR の内部で Oracle の数値データ型を格納している操作を実行しようとする場合、アダプターを使用して、アダプターは、オーバーフロー例外をスロー可能性があります。</span><span class="sxs-lookup"><span data-stu-id="73653-235">Using the adapter, if you try to perform an operation containing Oracle numeric data types inside DataSets or weakly-typed REF CURSORS, the adapter might throw an overflow exception.</span></span>  
  
 <span data-ttu-id="73653-236">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-236">**Cause**</span></span>  
  
 <span data-ttu-id="73653-237">これは、大規模なデータセットや、それぞれの .NET 型に収まらない厳密に型指定の REF CURSOR の内部で Oracle の数値データ型の値を指定する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="73653-237">This happens if you supply a large value for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS that cannot fit into the respective .NET type.</span></span>  
  
 <span data-ttu-id="73653-238">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-238">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-239">データセットまたは厳密に型指定の REF CURSOR、Oracle の数値データ型の大きな値を渡す場合は、安全な」と入力の値を設定して有効にする必要があります、 **EnableSafeTyping**プロパティをバインド**true**.</span><span class="sxs-lookup"><span data-stu-id="73653-239">If you want to pass large values for the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS, you must enable safe typing by setting the value of the **EnableSafeTyping** binding property to **true**.</span></span> <span data-ttu-id="73653-240">安全な入力を有効にすると、データセットまたは厳密に型指定の REF CURSOR、Oracle の数値データ型が文字列として公開します。</span><span class="sxs-lookup"><span data-stu-id="73653-240">Enabling safe typing exposes the Oracle numeric data type inside DataSets or weakly-typed REF CURSORS as strings.</span></span>  
  
###  <a name="BKMK_OraDBRootNode"></a> <span data-ttu-id="73653-241">BizTalk プロジェクト内の RootNode TypeName とエラー</span><span class="sxs-lookup"><span data-stu-id="73653-241">Error with RootNode TypeName in BizTalk Projects</span></span>  
 <span data-ttu-id="73653-242">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-242">**Problem**</span></span>  
  
 <span data-ttu-id="73653-243">BizTalk プロジェクトで[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]からスキーマが生成される場合、[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]無効な文字または予約語を含む、 **RootNode TypeName**プロパティ、プロジェクトのコンパイル中に次のエラーが発生:</span><span class="sxs-lookup"><span data-stu-id="73653-243">In a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], if the schemas generated from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] contains invalid characters or reserved words for the **RootNode TypeName** property, the following error will occur while compiling the project:</span></span>  
  
```  
Node <node reference> - Specify a valid .NET type name for this root node.  
The current .NET type name of this root node is invalid (it is a reserved BizTalk Keyword or is an invalid C# identifier).  
```  
  
 <span data-ttu-id="73653-244">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-244">**Resolution**</span></span>  
  
1.  <span data-ttu-id="73653-245">クリックし、エラーで参照されている rood ノードを右クリックして**プロパティ**します。</span><span class="sxs-lookup"><span data-stu-id="73653-245">Right-click the rood node referenced in the error and select **Properties**.</span></span>  
  
2.  <span data-ttu-id="73653-246">**RootNode TypeName**プロパティ、無効な文字を削除するかの予約語、たとえば、ドット (.)。</span><span class="sxs-lookup"><span data-stu-id="73653-246">For the **RootNode TypeName** property, remove any illegal characters or reserved words, for example, dot (.).</span></span>  
  
###  <a name="BKMK_OraDBInvalBinding"></a> <span data-ttu-id="73653-247">Visual Studio で、アダプターを使用する際に無効なバインド警告</span><span class="sxs-lookup"><span data-stu-id="73653-247">Invalid binding warning when using the adapter in Visual Studio</span></span>  
 <span data-ttu-id="73653-248">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-248">**Problem**</span></span>  
  
 <span data-ttu-id="73653-249">アプリケーションを作成するアダプターを使用すると[!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]とアダプターによって生成された構成ファイル (app.config) を開き、次のような警告を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73653-249">When you use the adapter to create an application in [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)] and you open the configuration file (app.config) generated by the adapter, you see a warning similar to the following:</span></span>  
  
```  
The element 'bindings' has invalid child element 'oracleDBBinding'. List of possible elements expected: 'basicHttpBinding, customBinding, ...  
```  
  
 <span data-ttu-id="73653-250">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-250">**Cause**</span></span>  
  
 <span data-ttu-id="73653-251">この警告が表示されます、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]バインド、`oracleDBBinding`に付属の標準バインディングではない、[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="73653-251">This warning appears because the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding, `oracleDBBinding`, is not a standard binding shipped with the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)].</span></span>  
  
 <span data-ttu-id="73653-252">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-252">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-253">この警告は無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="73653-253">You can safely ignore this warning.</span></span>  
  
###  <a name="BKMK_OraDBNotification"></a> <span data-ttu-id="73653-254">同じアプリケーション内で 1 つ以上の通知スキーマを使用するか、同じホスト上の複数のアプリケーションで通知スキーマを使用している場合、BizTalk Server は例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="73653-254">BizTalk Server throws an exception if you use more than one Notification schema in the same application or use the Notification schema across multiple applications on the same host</span></span>  
 <span data-ttu-id="73653-255">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-255">**Problem**</span></span>  
  
 <span data-ttu-id="73653-256">BizTalk Server では、XLANG 例外やアプリケーションも、複数のスキーマには、メッセージの種類が一致するためには、ドキュメント仕様を特定できないことを示す例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="73653-256">BizTalk Server throws an XLANG exception or an exception stating that the application cannot locate the document specification because multiple schemas matched the message type.</span></span>  
  
 <span data-ttu-id="73653-257">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-257">**Cause**</span></span>  
  
 <span data-ttu-id="73653-258">これは、次のいずれかの原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="73653-258">This happens because of either of the following:</span></span>  
  
- <span data-ttu-id="73653-259">1 つ以上を生成した通知スキーマを BizTalk Server プロジェクトで、BizTalk Server アプリケーションに展開し、Oracle データベースから通知を受け取るアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="73653-259">You have generated more than one Notification schema in a BizTalk Server project, deployed it to a BizTalk Server application, and then ran the application to receive notifications from the Oracle database.</span></span> <span data-ttu-id="73653-260">競合が通知のスキーマは共通であるため、BizTalk Server アプリケーションに展開されているスキーマ間であります。</span><span class="sxs-lookup"><span data-stu-id="73653-260">Because the Notification schemas are common, there is a conflict between the schemas that are deployed in the BizTalk Server application.</span></span>  
  
- <span data-ttu-id="73653-261">複数のプロジェクトが発生した場合、同じホスト上の別の BizTalk Server アプリケーションを各プロジェクト配置されたプロジェクト、BizTalk Server の各通知スキーマを生成したから通知を受信するアプリケーションを実行し、Oracle データベース。</span><span class="sxs-lookup"><span data-stu-id="73653-261">In case of multiple projects, you have generated a Notification schema for each of the BizTalk Server projects, deployed each project to a separate BizTalk Server application on the same host, and then ran an application or applications to receive notifications from the Oracle database.</span></span> <span data-ttu-id="73653-262">競合が、スキーマとアセンブリは BizTalk Server のアプリケーション間でアクセス可能であるために展開 BizTalk Server アプリケーションとアセンブリのさまざまな一般的なスキーマの間であります。</span><span class="sxs-lookup"><span data-stu-id="73653-262">Because the schemas and assemblies are accessible across the applications in BizTalk Server, there is a conflict between the common schemas deployed under various BizTalk Server applications and assemblies.</span></span>  
  
  <span data-ttu-id="73653-263">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-263">**Resolution**</span></span>  
  
  <span data-ttu-id="73653-264">BizTalk Server アプリケーションの 1 つの通知スキーマ ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="73653-264">Use a single Notification schema file for a BizTalk Server application.</span></span> <span data-ttu-id="73653-265">同じホスト上の複数の BizTalk Server アプリケーションで通知スキーマを使用する必要がある場合、1 つの通知スキーマを含むアプリケーションを作成し、BizTalk Server で他のすべてのアプリケーションから通知スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="73653-265">If you need to use the Notification schema in multiple BizTalk Server applications on the same host, create an application containing a single Notification schema, and then use the notification schema from all other applications in BizTalk Server.</span></span>  
  
###  <a name="BKMK_MemUsage"></a> <span data-ttu-id="73653-266">メモリ使用量とスレッド数の増加、トランザクション受信操作で、アダプターを使用する場合</span><span class="sxs-lookup"><span data-stu-id="73653-266">Memory usage and thread count increases when using the adapter in a transacted inbound operation</span></span>  
 <span data-ttu-id="73653-267">**問題**</span><span class="sxs-lookup"><span data-stu-id="73653-267">**Problem**</span></span>  
  
 <span data-ttu-id="73653-268">ポーリングなどのトランザクション受信操作で**かどうかデータがないポーリングされるテーブルで使用できる**アダプターがポーリングを継続しは、時間の期間にわたってメモリ使用量とスレッド数の増加が発生します。</span><span class="sxs-lookup"><span data-stu-id="73653-268">In a transacted inbound operation, such as Polling, **if there is no data available in the table being polled** and the adapter continues to poll, over a period of time you experience an increase in the memory usage and the thread count.</span></span>  
  
 <span data-ttu-id="73653-269">**原因**</span><span class="sxs-lookup"><span data-stu-id="73653-269">**Cause**</span></span>  
  
 <span data-ttu-id="73653-270">**かどうかはデータがないポーリングされるテーブルで使用できる**後にすべて受信タイムアウトのサイクル[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]ポーリング操作を続行する新しいスレッドを生成します。</span><span class="sxs-lookup"><span data-stu-id="73653-270">**If there is no data available in the table being polled**, after every receive timeout cycle, [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] spawns a new thread to continue the polling operation.</span></span> <span data-ttu-id="73653-271">そのため、期間のスレッドの数とメモリ使用量が増加します。</span><span class="sxs-lookup"><span data-stu-id="73653-271">Hence, the thread count and memory usage increases over a period of time.</span></span> <span data-ttu-id="73653-272">ただし、ポーリングされるテーブルにいくつかのデータがある場合、同じスレッドは、すべての後続のポーリングを実行する継続します。</span><span class="sxs-lookup"><span data-stu-id="73653-272">However, if the table being polled has some data, the same thread continues to perform all subsequent polls.</span></span>  
  
 <span data-ttu-id="73653-273">**解決方法**</span><span class="sxs-lookup"><span data-stu-id="73653-273">**Resolution**</span></span>  
  
 <span data-ttu-id="73653-274">設定をお勧め、 **ReceiveTimeout**に最大の可能な値である 24.20:31:23.6470000 (24 日)、新しいスレッドは 24 日間にのみを生成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="73653-274">We recommend setting the **ReceiveTimeout** to the maximum possible value, which is 24.20:31:23.6470000 (24 days) so that a new thread is spawned only every 24 days.</span></span> <span data-ttu-id="73653-275">メモリ使用量とスレッドの数が大きくが多すぎるが早すぎるようになります。</span><span class="sxs-lookup"><span data-stu-id="73653-275">This will ensure that the memory usage and thread count does not grow too much too soon.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73653-276">SqlAdapterInboundTransactionBehavior が設定されている場合、TransactionTimeout が 24.20:31:23.6470000 (24 日) である最大の可能な値にも構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="73653-276">If SqlAdapterInboundTransactionBehavior has been set, make sure the TransactionTimeout is also configured to maximum possible value, which is 24.20:31:23.6470000 (24 days).</span></span> <span data-ttu-id="73653-277">この回避策を使用する場合、トランザクション分離レベルを構成する場合のみ、SqlAdapterInboundTransactionBehavior を追加できます。</span><span class="sxs-lookup"><span data-stu-id="73653-277">When using this workaround, we can add the SqlAdapterInboundTransactionBehavior only if the transaction isolation level has to be configured.</span></span> <span data-ttu-id="73653-278">それ以外の場合、これはその動作を削除することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="73653-278">Else, it is a best practice to remove that behavior.</span></span>  
  
 <span data-ttu-id="73653-279">詳細については、 **ReceiveTimeout**プロパティ、バインドを参照してください[Oracle データベース アダプターのバインドのプロパティについて](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md)します。</span><span class="sxs-lookup"><span data-stu-id="73653-279">For more information about the **ReceiveTimeout** binding property, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span> <span data-ttu-id="73653-280">バインドのプロパティを指定する方法の詳細については、[for Oracle Database バインド プロパティを構成する](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="73653-280">For instructions on specifying binding properties, see [Configure the binding properties for Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-the-binding-properties-for-oracle-database.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73653-281">アダプターを使用する場合[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]、タイムアウトを大きな値に設定した場合、アダプターの機能は影響しません。</span><span class="sxs-lookup"><span data-stu-id="73653-281">When using the adapter with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], setting the timeout to a large value does not impact the functionality of the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73653-282">参照</span><span class="sxs-lookup"><span data-stu-id="73653-282">See Also</span></span>  
[<span data-ttu-id="73653-283">Oracle データベース アダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="73653-283">Troubleshoot the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-the-oracle-database-adapter.md)  
[<span data-ttu-id="73653-284">Oracle データベース アダプターのインストールに関する問題をトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="73653-284">Troubleshoot installation issues with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/troubleshoot-installation-issues-with-the-oracle-database-adapter.md)