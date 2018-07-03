---
title: WCF サービス モデルを使用して SAP の Bapi を呼び出す |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAPIs, invoking by using the WCF service model
- WCF service model, invoking BAPIs
ms.assetid: be3c48d6-2213-4ae5-97f4-634fbc423022
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6f5cab88b0f672f9f09bdeb7795c0a58213f92f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002443"
---
# <a name="invoke-bapis-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="cc4c0-102">WCF サービス モデルを使用して SAP の Bapi を呼び出す</span><span class="sxs-lookup"><span data-stu-id="cc4c0-102">Invoke BAPIs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="cc4c0-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]として Bapi 明らかになります。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces BAPIs as:</span></span>  
  
- <span data-ttu-id="cc4c0-104">**RFC 操作**します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-104">**RFC operations**.</span></span> <span data-ttu-id="cc4c0-105">[RFC] ノードに表示されますなどその他の任意の RFC、Bapi、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-105">BAPIs like any other RFC are surfaced under the RFC node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
- <span data-ttu-id="cc4c0-106">**SAP ビジネス オブジェクトのメソッド**します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-106">**Methods of SAP business objects**.</span></span> <span data-ttu-id="cc4c0-107">BAPI ノードの下のビジネス オブジェクトによって表示される Bapi、ビジネス オブジェクトのメソッドとして、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-107">As methods of business objects, BAPIs are surfaced by business object under the BAPI node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
  <span data-ttu-id="cc4c0-108">RFC 操作として、またはビジネス オブジェクト メソッドとして BAPI を呼び出すかどうか各 BAPI、常に、LUW で SAP システムの一部です。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-108">Whether you invoke a BAPI as an RFC operation or as a business object method, each BAPI is always part of an LUW on the SAP system.</span></span>  
  
  <span data-ttu-id="cc4c0-109">方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポート Bapi を参照してください[SAP の Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-109">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
  <span data-ttu-id="cc4c0-110">WCF サービス モデルを使用してビジネス オブジェクト メソッドとして Bapi を呼び出すと、各 SAP ビジネス オブジェクトは、WCF クライアント クラスで表されるし、そのビジネス オブジェクトの Bapi はクライアント上のメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-110">When you use the WCF service model to invoke BAPIs as business object methods, each SAP business object is represented by a WCF client class and the BAPIs of that business object are represented as methods on the client.</span></span> <span data-ttu-id="cc4c0-111">使用することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]をコードで呼び出す各 BAPI のメソッドを格納する、特定のビジネス オブジェクトの WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-111">You can use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class for specific business objects that contains methods for each BAPI that you want to invoke in your code.</span></span> <span data-ttu-id="cc4c0-112">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]も各 BAPI によって使用されているパラメーターおよびデータ型をカプセル化する .NET 型を生成します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-112">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates .NET types to encapsulate the parameters and data types that are used by each BAPI.</span></span> <span data-ttu-id="cc4c0-113">この WCF クライアント クラスのインスタンスを作成し、ターゲットの Bapi を呼び出すメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-113">You can then create an instance of this WCF client class and call its methods to invoke the target BAPIs.</span></span>  
  
  <span data-ttu-id="cc4c0-114">次のセクションでは、ビジネス オブジェクトのメソッドとして Bapi を呼び出すし、WCF サービス モデルでの BAPI トランザクションのサポート方法について説明する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-114">The following sections show you how to invoke BAPIs as methods of business objects and discuss how BAPI transactions are supported in the WCF service model.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="cc4c0-115">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="cc4c0-115">The WCF Client Class</span></span>  
 <span data-ttu-id="cc4c0-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]さまざまなサービス コントラクトはビジネス オブジェクトごとに、明らかになります。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a different service contract, for each business object.</span></span> <span data-ttu-id="cc4c0-117">これは、各ビジネス オブジェクトの一意の WCF クライアント クラスが作成されたことを意味します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-117">This means that for each business object a unique WCF client class is created.</span></span> <span data-ttu-id="cc4c0-118">このクラスの名前は、ビジネス オブジェクトの種類に基づきます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-118">The name of this class is based on the business object type.</span></span> <span data-ttu-id="cc4c0-119">たとえば、Sales Order ビジネス オブジェクト (ビジネス オブジェクト タイプ BUS2032) の WCF クライアント クラスは**BapiBUS2032Client**します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-119">For example for the Sales Order business object (business object type BUS2032), the WCF client class is **BapiBUS2032Client**.</span></span> <span data-ttu-id="cc4c0-120">ビジネス オブジェクト内の各ターゲット BAPI が生成された WCF クライアント クラスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-120">Each target BAPI in the business object is represented as a method in the generated WCF client class.</span></span> <span data-ttu-id="cc4c0-121">各メソッドには。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-121">In each method:</span></span>  
  
- <span data-ttu-id="cc4c0-122">SAP のエクスポートのパラメーターとして表示されますが**アウト**パラメーター</span><span class="sxs-lookup"><span data-stu-id="cc4c0-122">SAP export parameters are surfaced as **out** parameters</span></span>  
  
- <span data-ttu-id="cc4c0-123">として SAP 呼び出しのパラメーターが表示された**ref**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-123">SAP calling parameters are surfaced as **ref** parameters.</span></span>  
  
- <span data-ttu-id="cc4c0-124">構造体などの複雑な SAP 型は、SAP の種類のフィールドに対応するプロパティの .NET クラスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-124">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="cc4c0-125">これらのクラスは、次の名前空間で定義されている: microsoft.lobservices.sap._2007._03.Types.Rfc します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-125">These classes are defined in the following namespace: microsoft.lobservices.sap._2007._03.Types.Rfc.</span></span>  
  
  <span data-ttu-id="cc4c0-126">BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK が各ビジネス オブジェクトの表示し、WCF クライアントでこれらを常に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-126">BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK are surfaced for each business object and you should always include these in your WCF client.</span></span>  
  
  <span data-ttu-id="cc4c0-127">次のコードでは、販売注文のビジネス オブジェクトに対して生成された WCF クライアント クラスの一部を示します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-127">The following code shows part of a WCF client class generated for the Sales Order business object.</span></span> <span data-ttu-id="cc4c0-128">このクライアントには、メソッド呼び出す CREATEFROMDAT2、BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK にはが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-128">This client contains methods to invoke CREATEFROMDAT2, BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK.</span></span> <span data-ttu-id="cc4c0-129">わかりやすくするためには、コンス トラクターと他のコードを省略されています。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-129">For clarity the constructors and other code has been omitted.</span></span>  
  
```  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.CodeDom.Compiler.GeneratedCodeAttribute("System.ServiceModel", "3.0.0.0")]  
public partial class BapiBUS2032Client : System.ServiceModel.ClientBase<BapiBUS2032>, BapiBUS2032 {  
  
    // Code has been removed for clarity  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="SALESDOCUMENT">Number of Generated Document</param>  
    /// <param name="BEHAVE_WHEN_ERROR">Error Handling</param>  
    /// …  
    /// <param name="ORDER_TEXT">Texts</param>  
    /// <param name="PARTNERADDRESSES">BAPI Reference Structure for Addresses (Org./Company)</param>  
    /// <param name="RETURN">Return Messages</param>  
    /// <returns></returns>  
    public string CREATEFROMDAT2(  
                string BEHAVE_WHEN_ERROR,   
                string BINARY_RELATIONSHIPTYPE,   
                string CONVERT,   
                string INT_NUMBER_ASSIGNMENT,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDLS LOGIC_SWITCH,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1 ORDER_HEADER_IN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDHD1X ORDER_HEADER_INX,   
                string SALESDOCUMENTIN,   
                microsoft.lobservices.sap._2007._03.Types.Rfc.BAPI_SENDER SENDER,   
                string TESTRUN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPAREX[] EXTENSIONIN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICCARD[] ORDER_CCARD,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUBLB[] ORDER_CFGS_BLOB,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUINS[] ORDER_CFGS_INST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUPRT[] ORDER_CFGS_PART_OF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUCFG[] ORDER_CFGS_REF,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUREF[] ORDER_CFGS_REFINST,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVAL[] ORDER_CFGS_VALUE,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICUVK[] ORDER_CFGS_VK,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICOND[] ORDER_CONDITIONS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPICONDX[] ORDER_CONDITIONS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITM[] ORDER_ITEMS_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDITMX[] ORDER_ITEMS_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDKEY[] ORDER_KEYS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIPARNR[] ORDER_PARTNERS,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDL[] ORDER_SCHEDULES_IN,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISCHDLX[] ORDER_SCHEDULES_INX,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPISDTEXT[] ORDER_TEXT,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIADDR1[] PARTNERADDRESSES,   
                ref microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2[] RETURN) { ...}  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <param name="WAIT">Using the command `COMMIT AND WAIT`</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_COMMIT(string WAIT) { ... }  
  
    /// <summary>The Metadata for this RFC was generated using the RFC SDK.</summary>  
    /// <param name="RETURN">Confirmations</param>  
    /// <returns></returns>  
    public microsoft.lobservices.sap._2007._03.Types.Rfc.BAPIRET2 BAPI_TRANSACTION_ROLLBACK() { ... }  
}  
```  
  
## <a name="bapi-transactions-in-the-wcf-service-model"></a><span data-ttu-id="cc4c0-130">WCF サービス モデルでの BAPI トランザクション</span><span class="sxs-lookup"><span data-stu-id="cc4c0-130">BAPI Transactions in the WCF Service Model</span></span>  
 <span data-ttu-id="cc4c0-131">すべての BAPI RFC、またはビジネス オブジェクトのメソッドとして呼び出されるかどうかの一部であるトランザクション (LUW) SAP システム同じ SAP 接続経由で受信したすべての BAPI SAP システムで同じ BAPI トランザクションの一部であります。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-131">Every BAPI, whether it is invoked as an RFC or as a business object method, is part of a transaction (LUW) on the SAP system; and every BAPI received over the same SAP connection is part of the same BAPI transaction on the SAP system.</span></span> <span data-ttu-id="cc4c0-132">SAP では、コミットまたは、BAPI_TRANSACTION_COMMIT または接続での BAPI_TRANSACTION_ROLLBACK の受信時に、BAPI トランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-132">SAP commits or rolls back the BAPI transaction when it receives a BAPI_TRANSACTION_COMMIT or a BAPI_TRANSACTION_ROLLBACK on the connection.</span></span> <span data-ttu-id="cc4c0-133">コミットまたはロールバックが実行されて、[次へ] の BAPI 接続経由で受信した新しいトランザクションが開始されます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-133">After a commit or rollback has been performed, the next BAPI received over the connection begins a new transaction.</span></span>  
  
 <span data-ttu-id="cc4c0-134">アダプターの各 WCF チャネルは、専用の SAP 接続が。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-134">For the adapter each WCF channel has a dedicated SAP connection.</span></span> <span data-ttu-id="cc4c0-135">WCF サービス モデルでは、各 WCF クライアントは、SAP システムへの送信に使用されるメッセージの内部チャネルが。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-135">In the WCF service model, each WCF client has an inner channel that is used send messages to the SAP system.</span></span> <span data-ttu-id="cc4c0-136">これは、特定の WCF クライアントを使用して呼び出される Bapi SAP システムで一意の BAPI トランザクションの一部であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-136">This means that the BAPIs that are invoked using a specific WCF client are part of a unique BAPI transaction on the SAP system.</span></span> <span data-ttu-id="cc4c0-137">これは、WCF サービス モデルを使用してビジネス オブジェクト メソッドとして Bapi を呼び出すときに、重大な制限事項です。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-137">This imposes a significant limitation when you use the WCF service model to invoke BAPIs as business object methods.</span></span> <span data-ttu-id="cc4c0-138">各 SAP ビジネス オブジェクトは、専用の WCF クライアント クラスによって表される、ため、同じトランザクションの一部として 2 つの異なるビジネス オブジェクトからの Bapi を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-138">Because each SAP business object is represented by a dedicated WCF client class, you cannot invoke BAPIs from two different business objects as part of the same transaction.</span></span> <span data-ttu-id="cc4c0-139">RFC 操作として Bapi を呼び出すにはこの問題を回避します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-139">The way around this is to invoke the BAPIs as RFC operations.</span></span> <span data-ttu-id="cc4c0-140">ため、これは、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] RFC の操作の 1 つの WCF クライアントを生成し、そのため、そのクライアントを使用して呼び出されたすべての操作が同じ WCF チャネル経由で送信されます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-140">This is because the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates a single WCF client for RFC operations, and, therefore, all operations invoked using that client are sent over the same WCF channel.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cc4c0-141">同じ BAPI トランザクション内で別の SAP ビジネス オブジェクトからの Bapi を含める場合は、(同じ WCF クライアントを使用) の RFC 操作として呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-141">If you want to include BAPIs from different SAP business objects in the same BAPI transaction, you must invoke them as RFC operations (using the same WCF client).</span></span> <span data-ttu-id="cc4c0-142">ビジネス オブジェクト メソッドとして呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-142">You cannot invoke them as business object methods.</span></span>  
  
 <span data-ttu-id="cc4c0-143">BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK コミットまたは SAP システムでの BAPI トランザクションのロールバックを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-143">You call BAPI_TRANSACTION_COMMIT or BAPI_TRANSACTION_ROLLBACK to commit or roll back the BAPI transaction on the SAP system.</span></span> <span data-ttu-id="cc4c0-144">アダプターでは、これら 2 つの Bapi が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-144">The adapter surfaces these two BAPIs:</span></span>  
  
- <span data-ttu-id="cc4c0-145">RFC 操作として [基準] ノードの下。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-145">Under the Basis node as RFC operations.</span></span>  
  
- <span data-ttu-id="cc4c0-146">各ビジネス オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-146">Under each business object.</span></span>  
  
  <span data-ttu-id="cc4c0-147">アダプターが SAP の BAPI トランザクションをサポートする方法の詳細については、次を参照してください。 [SAP の Bapi に対する操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-147">For more information about how the adapter supports BAPI transactions on SAP, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="how-to-create-an-application-that-invokes-bapis-as-methods-of-business-objects"></a><span data-ttu-id="cc4c0-148">ビジネス オブジェクトのメソッドとして Bapi を起動するアプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="cc4c0-148">How to Create an Application that Invokes BAPIs as Methods of Business Objects</span></span>  
 <span data-ttu-id="cc4c0-149">このセクションでは、ビジネス オブジェクトのメソッドとして Bapi を呼び出す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-149">This section provides information about how to invoke BAPIs as methods of business objects.</span></span> <span data-ttu-id="cc4c0-150">同じ基本手順は、WCF クライアントを対象とする RFC 操作として Bapi を作成し、各 BAPI を呼び出すために使用する点を除いて RFC の操作として Bapi を呼び出すに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-150">The same basic procedure should be followed to invoke BAPIs as RFC operations, except that you create a WCF client that targets the BAPIs as RFC operations and use it to invoke each BAPI.</span></span>  
  
 <span data-ttu-id="cc4c0-151">BAPI のクライアント アプリケーションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-151">To create a BAPI client application, perform the following steps.</span></span>  
  
#### <a name="to-create-an-bapi-client-application"></a><span data-ttu-id="cc4c0-152">BAPI クライアント アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="cc4c0-152">To create an BAPI client application</span></span>  
  
1. <span data-ttu-id="cc4c0-153">WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-153">Generate a WCF client class.</span></span> <span data-ttu-id="cc4c0-154">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラス (またはクラス) を生成するビジネス オブジェクトを対象として Bapi を操作するか。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-154">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class (or classes) that targets the business objects and BAPIs with which you want to work.</span></span> <span data-ttu-id="cc4c0-155">必ず、BAPI_TRANSACTION_COMMIT とターゲットのビジネス オブジェクトごとに公開される BAPI_TRANSACTION_ROLLBACK メソッド (Bapi) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-155">Be sure to include the BAPI_TRANSACTION_COMMIT and the BAPI_TRANSACTION_ROLLBACK methods (BAPIs) exposed for each target business object.</span></span> <span data-ttu-id="cc4c0-156">WCF クライアントを生成する方法の詳細については、次を参照してください。 [SAP ソリューションの成果物の WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-156">For more information about how to generate a WCF client, see [Generating a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2. <span data-ttu-id="cc4c0-157">手順 1 で生成された WCF クライアント クラスのインスタンスを作成し、作成し、WCF クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-157">Create an instance of the WCF client class generated in step 1, and create and configure a WCF client.</span></span> <span data-ttu-id="cc4c0-158">WCF クライアントを構成するには、バインドと、クライアントが使用するエンドポイント アドレスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-158">Configuring the WCF client involves specifying the binding and endpoint address that the client will use.</span></span> <span data-ttu-id="cc4c0-159">コードで強制的に、または構成で宣言的に、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-159">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="cc4c0-160">クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-160">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="cc4c0-161">次のコードでは、構成から販売注文 (BUS2032) SAP ビジネス オブジェクト用の WCF クライアントを初期化し、SAP システムの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-161">The following code initializes the WCF client for the Sales Order (BUS2032) SAP business object from configuration and sets the credentials for the SAP system.</span></span>  
  
   ```  
   BapiBUS2032Client bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
   bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
   bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
   ```  
  
3. <span data-ttu-id="cc4c0-162">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-162">Open the WCF client.</span></span>  
  
   ```  
   bapiClient.Open();  
   ```  
  
4. <span data-ttu-id="cc4c0-163">SAP システムで適切な Bapi を呼び出す手順 2. で作成された WCF クライアントのメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-163">Invoke methods on the WCF client created in step 2 to invoke the appropriate BAPIs on the SAP system.</span></span> <span data-ttu-id="cc4c0-164">SAP システムで複数の Bapi を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-164">You can invoke multiple BAPIs on the SAP system.</span></span>  
  
5. <span data-ttu-id="cc4c0-165">トランザクションを終了するには。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-165">End the transaction by:</span></span>  
  
   1.  <span data-ttu-id="cc4c0-166">トランザクションをコミットする BAPI_TRANSACTION_COMMIT メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-166">Invoking the BAPI_TRANSACTION_COMMIT method to commit the transaction.</span></span>  
  
       ```  
       bapiClient.BAPI_TRANSACTION_COMMIT("X");  
       ```  
  
   2.  <span data-ttu-id="cc4c0-167">トランザクションをロールバックする BAPI_TRANSACTION_ROLLBACK メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-167">Invoking the BAPI_TRANSACTION_ROLLBACK method to roll back the transaction.</span></span>  
  
       ```  
       bapiClient.BAPI_TRANSACTION_ROLLBACK();  
       ```  
  
6. <span data-ttu-id="cc4c0-168">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-168">Close the WCF client.</span></span>  
  
   ```  
   bapiClient.Close();   
   ```  
  
### <a name="example"></a><span data-ttu-id="cc4c0-169">例</span><span class="sxs-lookup"><span data-stu-id="cc4c0-169">Example</span></span>  
 <span data-ttu-id="cc4c0-170">次の例では、販売注文のビジネス オブジェクトで CREATEFROMDAT2 BAPI を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-170">The following example invokes the CREATEFROMDAT2 BAPI on the Sales Order business object.</span></span> <span data-ttu-id="cc4c0-171">複数回、BAPI を呼び出すし、トランザクションをコミットする BAPI_TRANSACTION_COMMIT を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-171">It invokes the BAPI several times and then invokes BAPI_TRANSACTION_COMMIT to commit the transaction.</span></span> <span data-ttu-id="cc4c0-172">BAPI を呼び出すときにエラーが発生する場合は、トランザクションをロールバックして、例外ハンドラーの BAPI_TRANSACTION_ROLLBACK が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-172">If an error occurs when invoking the BAPI, BAPI_TRANSACTION_ROLLBACK is invoked in the exception handler to roll back the transaction.</span></span>  
  
 <span data-ttu-id="cc4c0-173">CREATEFROMDAT2 メソッドは、多くのパラメーターを受け取ります。これらは、簡潔にする例では省略されます。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-173">The CREATEFROMDAT2 method takes many parameters; these are omitted in the example for the sake of brevity.</span></span> <span data-ttu-id="cc4c0-174">Microsoft に付属のサンプルでの BAPI トランザクションを示すサンプルが見つかります[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-174">You can find a sample that demonstrates BAPI transactions in the samples shipped with the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="cc4c0-175">詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="cc4c0-175">For more information, see [Samples for the SAP Adapter ](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Text;  
  
// Add WCF, Adapter LOB SDK, and SAP Adapter namepaces  
using System.ServiceModel;  
using Microsoft.Adapters.SAP;  
using Microsoft.ServiceModel.Channels;  
  
// Include this namespace for Adapter LOB SDK and SAP exceptions  
using Microsoft.ServiceModel.Channels.Common;  
  
using microsoft.lobservices.sap._2007._03.Types.Rfc;  
  
// This Example demonstrates BAPI transactions. Two sales orders are  
// created using the CREATEFROMDAT2 method of a SAP Business Object.   
// After the orders are created, the BAPI transaction is committed.   
// If an exception occurs when sending the BAPIs, the BAPI transaction is   
// rolled back.  
//   
  
namespace SapBapiTxClientSM  
{  
    class Program  
    {  
        static void Main(string[] args)  
        {  
            // Create the BAPI client from the generated endpoint configuration.  
  
            BapiBUS2032Client bapiClient = null;  
  
            Console.WriteLine("BAPI transaction sample started");  
            Console.WriteLine("\nCreating business object client");  
  
            try  
            {  
                bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
                bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
                bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
  
                // Open the BAPI Client  
                bapiClient.Open();  
  
                ...  
  
                // send first BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters ommitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // send second BAPI  
                try  
                {  
                    string salesDocNumber1 = bapiClient.CREATEFROMDAT2(  
                        ...  
                        // parameters omitted  
                        ...                          
                        );  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
                // Commit BAPI Transaction  
                try  
                {  
                    bapiClient.BAPI_TRANSACTION.Commit();  
                }  
                catch (Exception ex)  
                {  
                    bapiClient.BAPI_TRANSACTION_ROLLBACK();  
                    throw;  
                }  
  
                ...  
  
            }  
            catch (ConnectionException cex)  
            {  
                // Get here if problem connecting to the SAP system   
  
                Console.WriteLine("Exception occurred connecting to the SAP system");  
                Console.WriteLine(cex.InnerException.Message);  
            }  
            catch (TargetSystemException tex)  
            {  
                // Get here if the SAP system returns an exception  
  
                Console.WriteLine("Exception occurred on the SAP System");  
                Console.WriteLine(tex.InnerException.Message);  
            }  
            catch (Exception ex)  
            {  
                Console.WriteLine("Exception is: " + ex.Message);  
                if (ex.InnerException != null)  
                {  
                    Console.WriteLine("Inner Exception is: " + ex.InnerException.Message);  
                }  
            }  
            finally  
            {  
            // Close the client when finished  
                if (bapiClient != null)  
                {  
                    if (bapiClient.State == CommunicationState.Opened)  
                        bapiClient.Close();  
                    else  
                        bapiClient.Abort();  
                }  
            }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="cc4c0-176">参照</span><span class="sxs-lookup"><span data-stu-id="cc4c0-176">See Also</span></span>  
[<span data-ttu-id="cc4c0-177">WCF サービス モデルを使用してアプリケーションを開発する</span><span class="sxs-lookup"><span data-stu-id="cc4c0-177">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)  
 [<span data-ttu-id="cc4c0-178">Sap Bapi に対する操作</span><span class="sxs-lookup"><span data-stu-id="cc4c0-178">Operations on BAPIs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)