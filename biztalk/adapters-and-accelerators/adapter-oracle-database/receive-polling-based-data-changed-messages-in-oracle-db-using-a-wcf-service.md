---
title: WCF サービス モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージの受信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF service model, receiving polling-based messages
- how to, receive polling-based message
- polling-based messages, receiving by using the WCF service model
ms.assetid: 0324e8bf-d9d1-46f5-b896-b9fc8e61d514
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94c3bfa7dd789380b5b781b9316d7243e6a4680c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529459"
---
# <a name="receive-polling-based-data-changed-messages-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="f0122-102">WCF サービス モデルを使用して Oracle データベースでのポーリングに基づいたデータ変更メッセージを受信します。</span><span class="sxs-lookup"><span data-stu-id="f0122-102">Receive Polling-based Data-changed Messages in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="f0122-103">構成することができます、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]ポーリング ベースのデータを受信するには、Oracle のテーブルまたはビューに対するメッセージを変更します。</span><span class="sxs-lookup"><span data-stu-id="f0122-103">You can configure the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to receive polling-based data changed messages against an Oracle table or view.</span></span> <span data-ttu-id="f0122-104">データ変更メッセージを受信するには、定期的に、アダプターが Oracle のテーブルまたはビューにオプションの PL/SQL コード ブロックを続けるに対する SQL クエリを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0122-104">To receive data-changed messages, the adapter periodically executes a SQL query against an Oracle table or view followed by an optional PL/SQL code block.</span></span> <span data-ttu-id="f0122-105">によって SQL クエリの結果が返されるし、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]受信 POLLINGSTMT 操作の設定、厳密に型指定された結果としてアプリケーションにします。</span><span class="sxs-lookup"><span data-stu-id="f0122-105">The results of the SQL query are then returned by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to your application as a strongly-typed result set in an inbound POLLINGSTMT operation.</span></span> <span data-ttu-id="f0122-106">使用してデータベースを構成し、Oracle のポーリングを実行するためのメカニズムの詳細については、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]を参照してください[Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0122-106">For more information about the mechanism used to configure and perform polling on an Oracle database using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span> <span data-ttu-id="f0122-107">続行する前に、このトピックで確認することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f0122-107">We strongly recommended that you read this topic before proceeding.</span></span>  
  
 <span data-ttu-id="f0122-108">WCF サービス モデルを使用する場合は、POLLINGSTMT 操作を受信するには、次の必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0122-108">To receive the POLLINGSTMT operation when you use the WCF service model, you must:</span></span>  
  
- <span data-ttu-id="f0122-109">アダプターによって公開されているメタデータから POLLINGSTMT 操作用には、WCF サービス コントラクト (インターフェイス) を生成します。</span><span class="sxs-lookup"><span data-stu-id="f0122-109">Generate a WCF service contract (interface) for the POLLINGSTMT operation from the metadata exposed by the adapter.</span></span> <span data-ttu-id="f0122-110">これを行うには、使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または ServiceModel メタデータ ユーティリティ ツール (svcutil.exe)。</span><span class="sxs-lookup"><span data-stu-id="f0122-110">To do this, you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe).</span></span>  
  
- <span data-ttu-id="f0122-111">このインターフェイスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f0122-111">Implement a WCF service from this interface.</span></span>  
  
- <span data-ttu-id="f0122-112">サービス ホストを使用してこの WCF サービス ホスト (**System.ServiceModel.ServiceHost**)。</span><span class="sxs-lookup"><span data-stu-id="f0122-112">Host this WCF service using a service host (**System.ServiceModel.ServiceHost**).</span></span>  
  
  <span data-ttu-id="f0122-113">このセクションのトピックでは、情報および Oracle データベースのテーブルおよび WCF サービス モデルでのビューにポーリングを実行するために手順を説明します。</span><span class="sxs-lookup"><span data-stu-id="f0122-113">The topics in this section provide information and procedures to help you perform polling on Oracle database tables and views in the WCF service model.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="f0122-114">このトピックで使用する例について</span><span class="sxs-lookup"><span data-stu-id="f0122-114">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="f0122-115">このトピックの例では、/SCOTT/ACCOUNTACTIVITY テーブルと/SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="f0122-115">The examples in this topic use the /SCOTT/ACCOUNTACTIVITY table and the /SCOTT/Package/ACCOUNT_PKG/PROCESS_ACTIVITY function.</span></span> <span data-ttu-id="f0122-116">これらの成果物を生成するスクリプトが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]サンプル。</span><span class="sxs-lookup"><span data-stu-id="f0122-116">A script to generate these artifacts is supplied with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="f0122-117">サンプルの詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0122-117">For more information about the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="configuring-polling-in-the-wcf-service-model"></a><span data-ttu-id="f0122-118">WCF サービス モデルでのポーリングの構成</span><span class="sxs-lookup"><span data-stu-id="f0122-118">Configuring Polling in the WCF Service Model</span></span>  
 <span data-ttu-id="f0122-119">構成する、 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] Oracle データベースのテーブルおよびビューのバインドのプロパティとオプションの接続プロパティ (パラメーター) を設定してポーリングを実行します。</span><span class="sxs-lookup"><span data-stu-id="f0122-119">You configure the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to perform polling on Oracle database tables and views by setting binding properties and an optional connection property (parameter).</span></span> <span data-ttu-id="f0122-120">これらのプロパティの一部は必須ですが、およびデザイン時と実行時の両方でいくつかに影響を与える設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0122-120">Some of these properties are mandatory, and some, to have an effect, must be set both at design-time and run-time.</span></span>  
  
- <span data-ttu-id="f0122-121">デザイン時に、設定する接続パラメーターとバインドのプロパティを WCF サービス コントラクトを生成する Oracle データベースに接続するとき。</span><span class="sxs-lookup"><span data-stu-id="f0122-121">At design-time, you set connection parameters and binding properties when you connect to the Oracle Database to generate a WCF service contract.</span></span>  
  
- <span data-ttu-id="f0122-122">実行時に、サービス ホストを作成するために使用 OracleDBBinding オブジェクトにバインドのプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="f0122-122">At runtime you set binding properties on the OracleDBBinding object that you use to create the service host.</span></span> <span data-ttu-id="f0122-123">サービス ホストにサービスのリスナーを追加する場合は、接続パラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="f0122-123">You set the connection parameter when you add a service listener to the service host.</span></span>  
  
  <span data-ttu-id="f0122-124">バインドのプロパティとポーリングを構成するために使用する接続パラメーターの概要を次に示します。</span><span class="sxs-lookup"><span data-stu-id="f0122-124">The following list provides a brief overview of the binding properties and connection parameters used to configure polling:</span></span>  
  
- <span data-ttu-id="f0122-125">**PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="f0122-125">The **PollingStatement** binding property.</span></span> <span data-ttu-id="f0122-126">デザイン時と実行時の両方にこのバインドのプロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0122-126">You must set this binding property both at design-time and at run-time.</span></span>  
  
- <span data-ttu-id="f0122-127">省略可能なバインドのプロパティ。</span><span class="sxs-lookup"><span data-stu-id="f0122-127">Optional binding properties.</span></span> <span data-ttu-id="f0122-128">これらは、実行時に設定するのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="f0122-128">These only have to be set at run-time.</span></span>  
  
- <span data-ttu-id="f0122-129">**AcceptCredentialsInUri**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="f0122-129">The **AcceptCredentialsInUri** binding property.</span></span> <span data-ttu-id="f0122-130">このバインドのプロパティを設定する必要があります**true**実行時の接続 URI 内の資格情報を有効にする場合にします。</span><span class="sxs-lookup"><span data-stu-id="f0122-130">You must set this binding property to **true** during run-time if you want to enable credentials in the connection URI.</span></span> <span data-ttu-id="f0122-131">サービス ホストにサービス エンドポイントを追加するときに、ユーザー名とパスワードを接続 URI に存在することがあります。</span><span class="sxs-lookup"><span data-stu-id="f0122-131">The user name and password must be present in the connection URI when you add a service endpoint to the service host.</span></span>  
  
- <span data-ttu-id="f0122-132">**PollingId**接続 URI の文字列パラメーターをクエリします。</span><span class="sxs-lookup"><span data-stu-id="f0122-132">The **PollingId** query string parameter in the connection URI.</span></span> <span data-ttu-id="f0122-133">POLLINGSTMT 操作の名前空間を変更する場合は、デザイン時と実行時の両方では、この接続プロパティを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0122-133">If you want to change the namespace of the POLLINGSTMT operation, you must set this connection property both at design-time and run-time.</span></span>  
  
  <span data-ttu-id="f0122-134">バインドのプロパティとポーリングを構成するために使用する接続パラメーターの詳細については、次を参照してください。 [Oracle データベース アダプターのポーリングに基づいたデータ変更メッセージを受信](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0122-134">For a complete description of the binding properties and connection parameters used to configure polling, see [Receive polling-based data-changed messages in Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/receive-polling-based-data-changed-messages-in-oracle-database-adapter.md).</span></span>  
  
## <a name="the-wcf-service-contract-and-class"></a><span data-ttu-id="f0122-135">WCF サービス コントラクトとクラス</span><span class="sxs-lookup"><span data-stu-id="f0122-135">The WCF Service Contract and Class</span></span>  
 <span data-ttu-id="f0122-136">いずれかを使用する、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]または、ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を作成する WCF サービス コントラクト (インターフェイス) と POLLINGSTMT 操作のクラスをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f0122-136">You use either the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to create a WCF service contract (interface) and supporting classes for the POLLINGSTMT operation.</span></span>  
  
 <span data-ttu-id="f0122-137">POLLINGSTMT 操作のサービス コントラクトを生成するこれらのツールのいずれかで、Oracle データベースに接続する場合。</span><span class="sxs-lookup"><span data-stu-id="f0122-137">When you connect to the Oracle database with either of these tools to generate a service contract for the POLLINGSTMT operation:</span></span>  
  
- <span data-ttu-id="f0122-138">指定する必要があります、 **PollingStatement**プロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="f0122-138">You must specify the **PollingStatement** binding property.</span></span> <span data-ttu-id="f0122-139">アダプターは、正しいメタデータ POLLINGSTMT 操作によって返される結果の厳密に型指定されたセットを生成するのに、このバインドのプロパティで、SELECT ステートメントを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0122-139">The adapter uses the SELECT statement in this binding property to generate the correct metadata for the strongly-typed result set returned by the POLLINGSTMT operation.</span></span>  
  
- <span data-ttu-id="f0122-140">必要に応じて、接続 URI で PollingId パラメーターを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f0122-140">You can optionally specify a PollingId parameter in the connection URI.</span></span> <span data-ttu-id="f0122-141">アダプターでは、このパラメーターを使用して、POLLINGSTMT 操作の名前空間を生成します。</span><span class="sxs-lookup"><span data-stu-id="f0122-141">The adapter uses this parameter to generate the namespace for the POLLINGSTMT operation.</span></span>  
  
  <span data-ttu-id="f0122-142">次の例。</span><span class="sxs-lookup"><span data-stu-id="f0122-142">In the following examples:</span></span>  
  
- <span data-ttu-id="f0122-143">**PollingStatement** "SELECT \* から ACCOUNTACTIVITY FOR UPDATE"に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f0122-143">**PollingStatement** is set to "SELECT \* FROM ACCOUNTACTIVITY FOR UPDATE".</span></span>  
  
- <span data-ttu-id="f0122-144">**PollingId** "AcctActivity"に設定されます。</span><span class="sxs-lookup"><span data-stu-id="f0122-144">**PollingId** is set to "AcctActivity".</span></span>  
  
### <a name="the-wcf-service-contract-interface"></a><span data-ttu-id="f0122-145">WCF サービス コントラクト (インターフェイス)</span><span class="sxs-lookup"><span data-stu-id="f0122-145">The WCF Service Contract (Interface)</span></span>  
 <span data-ttu-id="f0122-146">次のコードでは、POLLINGSTMT 操作用に生成する WCF サービス コントラクト (インターフェイス) を示します。</span><span class="sxs-lookup"><span data-stu-id="f0122-146">The following code shows the WCF service contract (interface) generated for the POLLINGSTMT operation.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.ServiceContractAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03", ConfigurationName="POLLINGSTMT_OperationGroup")]  
public interface POLLINGSTMT_OperationGroup {  
  
    // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)  
    // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
    [System.ServiceModel.OperationContractAttribute(IsOneWay=true, Action="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT")]  
    void POLLINGSTMT(POLLINGSTMT request);  
}  
```  
  
### <a name="the-message-contracts"></a><span data-ttu-id="f0122-147">メッセージ コントラクト</span><span class="sxs-lookup"><span data-stu-id="f0122-147">The Message Contracts</span></span>  
 <span data-ttu-id="f0122-148">接続 URI の PollingId パラメーターでは、メッセージ コントラクトの名前空間が変更されます。</span><span class="sxs-lookup"><span data-stu-id="f0122-148">The message contract namespace is modified by the PollingId parameter in the connection URI.</span></span> <span data-ttu-id="f0122-149">要求メッセージは、厳密に型指定されたレコードのセットを返します。</span><span class="sxs-lookup"><span data-stu-id="f0122-149">The request message returns a set of strongly-typed records.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
[System.ServiceModel.MessageContractAttribute(WrapperName="POLLINGSTMT", WrapperNamespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", IsWrapped=true)]  
public partial class POLLINGSTMT {  
  
    [System.ServiceModel.MessageBodyMemberAttribute(Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity", Order=0)]  
    public microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD;  
  
    public POLLINGSTMT() {  
    }  
  
    public POLLINGSTMT(microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity.POLLINGSTMTRECORD[] POLLINGSTMTRECORD) {  
        this.POLLINGSTMTRECORD = POLLINGSTMTRECORD;  
    }  
}  
```  
  
### <a name="the-data-contract-namespace"></a><span data-ttu-id="f0122-150">データ コントラクトの Namespace</span><span class="sxs-lookup"><span data-stu-id="f0122-150">The Data Contract Namespace</span></span>  
 <span data-ttu-id="f0122-151">データ コントラクトは、サービスと交換されるデータを抽象的に記述するクライアントの間の正式な取り決めです。</span><span class="sxs-lookup"><span data-stu-id="f0122-151">A data contract is a formal agreement between a service and a client that abstractly describes the data to be exchanged.</span></span> <span data-ttu-id="f0122-152">これは、通信するために、クライアントとサービスする必要はありません同一の型では、同じデータ コントラクトのみを共有します。</span><span class="sxs-lookup"><span data-stu-id="f0122-152">That is, in order to communicate, the client and the service do not have to share the same types, only the same data contracts.</span></span>  
  
 <span data-ttu-id="f0122-153">メッセージの変更データが発生した場合、データ コントラクト名前空間も変更 PollingId パラメーターで (指定した) 場合の接続 URI です。</span><span class="sxs-lookup"><span data-stu-id="f0122-153">In case of data change messages, the data contract namespace is also modified by the PollingId parameter (if specified) in the connection URI.</span></span> <span data-ttu-id="f0122-154">データ コントラクトは、クエリの結果セット内の厳密に型指定されたレコードを表すクラスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="f0122-154">The data contract is composed of a class that represents a strongly-typed record in the query result set.</span></span> <span data-ttu-id="f0122-155">クラス定義の詳細については、この例では省略されます。</span><span class="sxs-lookup"><span data-stu-id="f0122-155">The details of the class definition are omitted in this example.</span></span> <span data-ttu-id="f0122-156">クラスには、結果セット内の列を表すプロパティが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f0122-156">The class contains properties that represent the columns in the result set.</span></span>  
  
 <span data-ttu-id="f0122-157">次の例では、PollingId"AcctActivity"が使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0122-157">In the following example, the PollingId “AcctActivity” is used.</span></span>  
  
```  
namespace microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity {  
    using System.Runtime.Serialization;  
  
    [System.Diagnostics.DebuggerStepThroughAttribute()]  
    [System.CodeDom.Compiler.GeneratedCodeAttribute("System.Runtime.Serialization", "3.0.0.0")]  
    [System.Runtime.Serialization.DataContractAttribute(Name="POLLINGSTMTRECORD", Namespace="http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity")]  
    public partial class POLLINGSTMTRECORD : object, System.Runtime.Serialization.IExtensibleDataObject {…}  
     }  
}  
```  
  
### <a name="wcf-service-class"></a><span data-ttu-id="f0122-158">WCF サービス クラス</span><span class="sxs-lookup"><span data-stu-id="f0122-158">WCF Service Class</span></span>  
 <span data-ttu-id="f0122-159">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をサービス コントラクト (インターフェイス) から実装された WCF サービス クラスのスタブを持つファイルも生成されます。</span><span class="sxs-lookup"><span data-stu-id="f0122-159">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates a file that has a stub for the WCF service class implemented from the service contract (interface).</span></span> <span data-ttu-id="f0122-160">ファイルの名前は、OracleDBBindingService.cs です。</span><span class="sxs-lookup"><span data-stu-id="f0122-160">The name of the file is OracleDBBindingService.cs.</span></span> <span data-ttu-id="f0122-161">このクラスに直接 POLLINGSTMT 操作を処理するロジックを挿入することができます。</span><span class="sxs-lookup"><span data-stu-id="f0122-161">You can insert the logic to process the POLLINGSTMT operation directly into this class.</span></span> <span data-ttu-id="f0122-162">Svcutil.exe を使用して、サービス コントラクト インターフェイスを生成する場合、必要がありますこのクラスの実装自分でします。</span><span class="sxs-lookup"><span data-stu-id="f0122-162">If you use svcutil.exe to generate the service contract interface, you must implement this class yourself.</span></span> <span data-ttu-id="f0122-163">次のコードによって生成される WCF サービス クラスを示しています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="f0122-163">The following code shows the WCF service class generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
```  
namespace OracleDBBindingNamespace {  
  
    public class OracleDBBindingService : POLLINGSTMT_OperationGroup {  
  
        // CODEGEN: Generating message contract since the wrapper namespace (http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMTAcctActivity)   
        // of message POLLINGSTMT does not match the default value (http://Microsoft.LobServices.OracleDB/2007/03)  
        public virtual void POLLINGSTMT(POLLINGSTMT request) {  
            throw new System.NotImplementedException("The method or operation is not implemented.");  
        }  
    }  
}  
```  
  
## <a name="receiving-the-pollingstmt-operation"></a><span data-ttu-id="f0122-164">POLLINGSTMT 操作の受信</span><span class="sxs-lookup"><span data-stu-id="f0122-164">Receiving the POLLINGSTMT Operation</span></span>  
  
#### <a name="to-receive-polling-data-from-the-oracle-database-adapter"></a><span data-ttu-id="f0122-165">Oracle データベース アダプターのポーリングのデータを受信するには</span><span class="sxs-lookup"><span data-stu-id="f0122-165">To receive polling data from the Oracle Database adapter</span></span>  
  
1. <span data-ttu-id="f0122-166">使用して、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]または WCF を生成する svcutil.exe サービス コントラクト (インターフェイス) と POLLINGSTMT 操作用にヘルパー クラス。</span><span class="sxs-lookup"><span data-stu-id="f0122-166">Use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or svcutil.exe to generate a WCF service contract (interface) and helper classes for the POLLINGSTMT operation.</span></span> <span data-ttu-id="f0122-167">詳細については、次を参照してください。 [WCF クライアントまたは Oracle データベース ソリューションの成果物の WCF サービス コントラクトを生成](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="f0122-167">For more information, see [Generate a WCF client or a WCF service contract for Oracle Database solution artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span> <span data-ttu-id="f0122-168">設定する必要がありますには、少なくとも、 **PollingStatement**アダプターに接続するときにプロパティをバインドします。</span><span class="sxs-lookup"><span data-stu-id="f0122-168">At a minimum, you must set the **PollingStatement** binding property when you connect to the adapter.</span></span> <span data-ttu-id="f0122-169">必要に応じて、接続 URI で PollingId パラメーターを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="f0122-169">You can optionally specify a PollingId parameter in the connection URI.</span></span> <span data-ttu-id="f0122-170">使用する場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]構成のために必要な設定のすべてのバインディング パラメーター。</span><span class="sxs-lookup"><span data-stu-id="f0122-170">If you are using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], you should set all of the binding parameters necessary for your configuration.</span></span> <span data-ttu-id="f0122-171">これは、生成された構成ファイルで設定は正しくことを保証します。</span><span class="sxs-lookup"><span data-stu-id="f0122-171">This guarantees that they are properly set in the generated configuration file.</span></span>  
  
2. <span data-ttu-id="f0122-172">手順 1. で生成されたインターフェイスとヘルパー クラスからの WCF サービスを実装します。</span><span class="sxs-lookup"><span data-stu-id="f0122-172">Implement a WCF service from the interface and helper classes generated in step 1.</span></span> <span data-ttu-id="f0122-173">このクラスの POLLINGSTMT メソッドは、POLLINGSTMT 操作から受信したデータの処理エラーが発生した場合、ポーリング トランザクションを中止する例外をスローできます。それ以外の場合、メソッドは何も返しません。</span><span class="sxs-lookup"><span data-stu-id="f0122-173">The POLLINGSTMT method of this class can throw an exception to abort the polling transaction, if an error is encountered processing the data received from the POLLINGSTMT operation; otherwise the method does not return anything.</span></span> <span data-ttu-id="f0122-174">次のように、WCF サービス クラスを属性する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0122-174">You must attribute the WCF service class as follows:</span></span>  
  
   ```  
   [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
   ```  
  
   1. <span data-ttu-id="f0122-175">使用した場合、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]インターフェイスを生成するには、直接のロジックを実装できる、 **POLLINGSTMT**に生成されたメソッド**OracleDBBindingService**クラス。</span><span class="sxs-lookup"><span data-stu-id="f0122-175">If you used the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate the interface, you can implement your logic directly in the **POLLINGSTMT** method in the generated **OracleDBBindingService** class.</span></span> <span data-ttu-id="f0122-176">このクラスは、OracleDBBindingService.cs で確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0122-176">This class can be found in OracleDBBindingService.cs.</span></span> <span data-ttu-id="f0122-177">この例では、このコードはサブ クラス、 **OracleDBBindingService**クラス。</span><span class="sxs-lookup"><span data-stu-id="f0122-177">This code in this example sub-classes the **OracleDBBindingService** class.</span></span>  
  
      ```  
      [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
      public class PollingStmtService : OracleDBBindingService  
      {  
          public override void POLLINGSTMT(POLLINGSTMT request)  
          {  
              Console.WriteLine("\nNew Polling Records Received");  
              Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
              for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
              {  
                  Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                      request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                      request.POLLINGSTMTRECORD[i].AMOUNT,  
                                      request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                      request.POLLINGSTMTRECORD[i].DESCRIPTION);  
              }  
          }  
      }  
      ```  
  
   2. <span data-ttu-id="f0122-178">Svcutil.exe を使用してインターフェイスを生成した場合は、インターフェイスを実装する WCF サービスを作成しのロジックを実装する必要があります、 **POLLINGSTMT**このクラスのメソッド。</span><span class="sxs-lookup"><span data-stu-id="f0122-178">If you used svcutil.exe to generate the interface, you must create a WCF service that implements the interface and implement your logic in the **POLLINGSTMT** method of this class.</span></span>  
  
3. <span data-ttu-id="f0122-179">手順 2 で作成した WCF サービスのインスタンスを作成します。</span><span class="sxs-lookup"><span data-stu-id="f0122-179">Create an instance of the WCF service created in step 2.</span></span>  
  
   ```  
   // create service instance  
   PollingStmtService pollingInstance = new PollingStmtService();  
   ```  
  
4. <span data-ttu-id="f0122-180">インスタンスを作成**System.ServiceModel.ServiceHost** WCF サービスと基本の接続 URI を使用しています。</span><span class="sxs-lookup"><span data-stu-id="f0122-180">Create an instance of **System.ServiceModel.ServiceHost** by using the WCF service and a base connection URI.</span></span> <span data-ttu-id="f0122-181">基本の接続 URI には、userinfoparams またはクエリ文字列を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="f0122-181">The base connection URI cannot contain userinfoparams or a query_string.</span></span>  
  
   ```  
   // Enable service host  
   Uri[] baseUri = new Uri[] { new Uri("oracledb://Adapter") };  
   ServiceHost srvHost = new ServiceHost(pollingInstance, baseUri);  
   ```  
  
5. <span data-ttu-id="f0122-182">作成、 **OracleDBBinding**し、そのバインドのプロパティを設定してポーリング操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="f0122-182">Create an **OracleDBBinding** and configure the polling operation by setting its binding properties.</span></span> <span data-ttu-id="f0122-183">コードで明示的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="f0122-183">You can do this either explicitly in code or declaratively in configuration.</span></span> <span data-ttu-id="f0122-184">少なくとも、ポーリング ステートメントとポーリング間隔を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f0122-184">At a minimum, you must specify the polling statement and polling interval.</span></span> <span data-ttu-id="f0122-185">この例では、する資格情報を指定の URI の一部としても設定する必要がありますので、 **AcceptCredentialsInUri**に**true**します。</span><span class="sxs-lookup"><span data-stu-id="f0122-185">In this example, you specify the credentials as part of the URI so you must also set the **AcceptCredentialsInUri** to **true**.</span></span>  
  
   ```  
   // Create and configure a binding for the service endpoint. NOTE: binding  
   // parameters are set here for clarity, but these are already set in the  
   // the generated configuration file  
   OracleDBBinding binding = new OracleDBBinding();  
  
   // The credentials are included in the connection URI, so set this property to true  
   binding.AcceptCredentialsInUri = true;  
  
   // Same as statement specified in Configure Adapter dialog box  
   binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
   binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
   // Be sure to set the interval long enough to complete processing before  
   // the next poll  
   binding.PollingInterval = 15;  
   // Polling is transactional; be sure to set an adequate isolation level   
   // for your environment  
   binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
   ```  
  
6. <span data-ttu-id="f0122-186">サービス ホストにサービス エンドポイントを追加します。</span><span class="sxs-lookup"><span data-stu-id="f0122-186">Add a service endpoint to the service host.</span></span> <span data-ttu-id="f0122-187">これを行うには :</span><span class="sxs-lookup"><span data-stu-id="f0122-187">To do this:</span></span>  
  
   -   <span data-ttu-id="f0122-188">手順 5. で作成したバインドを使用します。</span><span class="sxs-lookup"><span data-stu-id="f0122-188">Use the binding created in step 5.</span></span>  
  
   -   <span data-ttu-id="f0122-189">接続の資格情報を含む URI を指定し、必要に応じて、PollingId 場合。</span><span class="sxs-lookup"><span data-stu-id="f0122-189">Specify a connection URI that contains credentials and, if needed, a PollingId.</span></span>  
  
   -   <span data-ttu-id="f0122-190">"POLLINGSTMT_OperationGroup"としてコントラクトを指定します。</span><span class="sxs-lookup"><span data-stu-id="f0122-190">Specify the contract as "POLLINGSTMT_OperationGroup".</span></span>  
  
   ```  
   // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
   Uri serviceUri = new Uri("oracledb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
   srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
   ```  
  
7. <span data-ttu-id="f0122-191">ポーリングのデータを受信するには、サービス ホストを開きます。</span><span class="sxs-lookup"><span data-stu-id="f0122-191">To receive polling data, open the service host.</span></span> <span data-ttu-id="f0122-192">アダプターは、クエリが結果セットを返すたびにデータを返します。</span><span class="sxs-lookup"><span data-stu-id="f0122-192">The adapter will return data whenever the query returns a result set.</span></span>  
  
   ```  
   // Open the service host to begin polling  
   srvHost.Open();  
   ```  
  
8. <span data-ttu-id="f0122-193">ポーリングを終了するには、サービス ホストを閉じます。</span><span class="sxs-lookup"><span data-stu-id="f0122-193">To terminate polling, close the service host.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="f0122-194">アダプターは、サービス ホストが閉じられるまでポーリングを続行します。</span><span class="sxs-lookup"><span data-stu-id="f0122-194">The adapter will continue to poll until the service host is closed.</span></span>  
  
   ```  
   srvHost.Close();  
   ```  
  
### <a name="example"></a><span data-ttu-id="f0122-195">例</span><span class="sxs-lookup"><span data-stu-id="f0122-195">Example</span></span>  
 <span data-ttu-id="f0122-196">次の例では、SCOTT/ACCOUNTACTIVITY テーブルに対して実行されるポーリング クエリを示します。</span><span class="sxs-lookup"><span data-stu-id="f0122-196">The following example shows a polling query that executes against the /SCOTT/ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="f0122-197">ポーリング後ステートメントは、処理済みレコードを別のテーブル/SCOTT/ACCOUNTHISTORY に移動する Oracle 関数を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f0122-197">The post-poll statement invokes an Oracle function that moves the processed records to another table /SCOTT/ACCOUNTHISTORY.</span></span> <span data-ttu-id="f0122-198">接続 URI の"AccountActivity"PollingId パラメーターを設定して POLLINGSTMT 操作の名前空間が変更されます。</span><span class="sxs-lookup"><span data-stu-id="f0122-198">The namespace of the POLLINGSTMT operation is modified by setting the PollingId parameter to "AccountActivity" in the connection URI.</span></span> <span data-ttu-id="f0122-199">この例では、生成されたをサブクラス化して POLLINGSTMT 操作用の WCF サービスを作成**OracleDBBindingService**クラス。 ただし、生成されたクラス内で直接、ロジックを実装できます。</span><span class="sxs-lookup"><span data-stu-id="f0122-199">In this example, the WCF service for the POLLINGSTMT operation is created by sub-classing the generated **OracleDBBindingService** class; however, you can implement your logic directly in the generated class.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add these three references to use the Oracle adapter  
using System.ServiceModel;  
using Microsoft.ServiceModel.Channels;  
using Microsoft.Adapters.OracleDB;  
  
using microsoft.lobservices.oracledb._2007._03.POLLINGSTMTAcctActivity;  
using OracleDBBindingNamespace;  
  
namespace OraclePollingSM  
{  
    [ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
  
    public class PollingStmtService : OracleDBBindingService  
    {  
        public override void POLLINGSTMT(POLLINGSTMT request)  
        {  
            Console.WriteLine("\nNew Polling Records Received");  
            Console.WriteLine("Tx Id\tAccount\tAmount\tDate\t\t\tDescription");  
            for (int i = 0; i < request.POLLINGSTMTRECORD.Length; i++)  
            {  
                Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", request.POLLINGSTMTRECORD[i].TID,  
                                    request.POLLINGSTMTRECORD[i].ACCOUNT,  
                                    request.POLLINGSTMTRECORD[i].AMOUNT,  
                                    request.POLLINGSTMTRECORD[i].TRANSDATE,  
                                    request.POLLINGSTMTRECORD[i].DESCRIPTION);  
  
            }  
            Console.WriteLine("\nHit <RETURN> to stop polling");  
         }  
    }  
  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            ServiceHost srvHost = null;  
  
            // This URI is used to specify the address for the ServiceEndpoint  
            // It must contain credentials and the PollingId (if any) that was used to generate  
            // the WCF service callback interface  
            Uri serviceUri = new Uri("OracleDb://User=SCOTT;Password=TIGER@Adapter?PollingId=AcctActivity");  
  
            // This URI is used to initialize the ServiceHost. It cannot contain  
            // userinfoparms (credentials) or a query_string (PollingId); otherwise,  
            // an exception is thrown when the ServiceHost is initialized.  
            Uri[] baseUri = new Uri[] { new Uri("OracleDb://Adapter") };  
  
            Console.WriteLine("Sample started, initializing service host -- please wait");  
  
            // create an instanc of the WCF service callback class  
            PollingStmtService pollingInstance = new PollingStmtService();  
  
            try  
            {  
                // Create a ServiceHost with the service callback instance and a base URI (address)  
                srvHost = new ServiceHost(pollingInstance, baseUri);  
  
                // Create and configure a binding for the service endpoint. Note: binding  
                // parameters are set here for clarity but these are already set in the  
                // generated configuration file  
                //  
                // The following properties are set  
                //    AcceptCredentialsInUri (true) to enable credentials in the connection URI for AddServiceEndpoint  
                //    PollingStatement  
                //    PostPollStatement calls PROCESS_ACTIVITY on Oracle. This procedure moves the queried records to  
                //                      the ACCOUNTHISTORY table  
                //    PollingInterval (15 seconds)  
                //    TransactionIsolationLevel   
  
                OracleDBBinding binding = new OracleDBBinding();  
  
                // The Credentials are included in the Connection Uri so set this property true  
                binding.AcceptCredentialsInUri = true;  
  
                // Same as statement specified in Configure Adapter dialog box  
                binding.InboundOperationType = InboundOperation.Polling;  
                binding.PollingStatement = "SELECT * FROM ACCOUNTACTIVITY FOR UPDATE";  
                binding.PostPollStatement = "BEGIN ACCOUNT_PKG.PROCESS_ACTIVITY(); END;";  
  
                // Be sure to set the interval long enough to complete processing before  
                // the next poll  
                binding.PollingInterval = 15;  
  
                // Polling is transactional, be sure to set an adequate isolation level   
                // for your environment  
                binding.TransactionIsolationLevel = TransactionIsolationLevel.ReadCommitted;  
  
                // Add service endpoint: be sure to specify POLLINGSTMT_OperationGroup as the contract  
                srvHost.AddServiceEndpoint("POLLINGSTMT_OperationGroup", binding, serviceUri);  
  
                Console.WriteLine("Opening the service host");  
                // Open the service host to begin polling  
                srvHost.Open();  
  
                // Wait to receive request  
                Console.WriteLine("\nPolling started. Returned records will be written to the console.");  
                Console.WriteLine("Hit <RETURN> to stop polling");  
                Console.ReadLine();  
            }  
            catch (Exception e)  
            {  
                Console.WriteLine("Exception :" + e.Message);  
                Console.ReadLine();  
  
                /* If there is an Oracle Error it will be specified in the inner exception */  
                if (e.InnerException != null)  
                {  
                    Console.WriteLine("InnerException: " + e.InnerException.Message);  
                    Console.ReadLine();  
                }  
            }  
            finally  
            {  
                // IMPORTANT: you must close the ServiceHost to stop polling  
                if (srvHost.State == CommunicationState.Opened)  
                    srvHost.Close();  
                else  
                    srvHost.Abort();  
            }  
  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f0122-200">参照</span><span class="sxs-lookup"><span data-stu-id="f0122-200">See Also</span></span>  
 [<span data-ttu-id="f0122-201">WCF サービス モデルを使用して Oracle データベース アプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="f0122-201">Develop Oracle Database applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)