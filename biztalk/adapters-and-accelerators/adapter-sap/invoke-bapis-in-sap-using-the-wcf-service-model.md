---
title: WCF サービス モデルを使用して SAP での Bapi を呼び出す |Microsoft ドキュメント
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
ms.openlocfilehash: 437c88516cfb771e0e5ae10807391235d602eb37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218514"
---
# <a name="invoke-bapis-in-sap-using-the-wcf-service-model"></a><span data-ttu-id="fd938-102">WCF サービス モデルを使用して SAP での Bapi を呼び出し</span><span class="sxs-lookup"><span data-stu-id="fd938-102">Invoke BAPIs in SAP using the WCF Service Model</span></span>
<span data-ttu-id="fd938-103">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]として Bapi を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd938-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces BAPIs as:</span></span>  
  
-   <span data-ttu-id="fd938-104">**RFC 操作**です。</span><span class="sxs-lookup"><span data-stu-id="fd938-104">**RFC operations**.</span></span> <span data-ttu-id="fd938-105">[RFC] ノードに表示された Bapi の他の任意の RFC のように、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="fd938-105">BAPIs like any other RFC are surfaced under the RFC node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
-   <span data-ttu-id="fd938-106">**SAP ビジネス オブジェクトのメソッド**です。</span><span class="sxs-lookup"><span data-stu-id="fd938-106">**Methods of SAP business objects**.</span></span> <span data-ttu-id="fd938-107">BAPI ノードの下のビジネス オブジェクトによって、ビジネス オブジェクトのメソッドとしての Bapi の表示、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="fd938-107">As methods of business objects, BAPIs are surfaced by business object under the BAPI node in the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
 <span data-ttu-id="fd938-108">RFC 操作、またはビジネス オブジェクトのメソッドとして BAPI を呼び出すと、各 BAPI は常に、LUW SAP システムでの一部です。</span><span class="sxs-lookup"><span data-stu-id="fd938-108">Whether you invoke a BAPI as an RFC operation or as a business object method, each BAPI is always part of an LUW on the SAP system.</span></span>  
  
 <span data-ttu-id="fd938-109">方法の概要については[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]サポートの Bapi を参照してください[SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd938-109">For an overview of how the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports BAPIs, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
 <span data-ttu-id="fd938-110">Bapi のビジネス オブジェクト メソッドとして呼び出す WCF サービス モデルを使用する場合は、SAP business の各オブジェクトは、WCF クライアント クラスで表されるされ、そのビジネス オブジェクトの Bapi は、クライアント上のメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="fd938-110">When you use the WCF service model to invoke BAPIs as business object methods, each SAP business object is represented by a WCF client class and the BAPIs of that business object are represented as methods on the client.</span></span> <span data-ttu-id="fd938-111">使用することができます、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]をコードで起動するそれぞれの BAPI のメソッドを格納する、特定のビジネス オブジェクトの WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="fd938-111">You can use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class for specific business objects that contains methods for each BAPI that you want to invoke in your code.</span></span> <span data-ttu-id="fd938-112">[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]も各 BAPI によって使用されているパラメーターとデータ型をカプセル化する .NET 型を生成します。</span><span class="sxs-lookup"><span data-stu-id="fd938-112">The [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] also generates .NET types to encapsulate the parameters and data types that are used by each BAPI.</span></span> <span data-ttu-id="fd938-113">この WCF クライアント クラスのインスタンスを作成し、ターゲット Bapi を起動するには、そのメソッドを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fd938-113">You can then create an instance of this WCF client class and call its methods to invoke the target BAPIs.</span></span>  
  
 <span data-ttu-id="fd938-114">次のセクションでは、ビジネス オブジェクトのメソッドとして Bapi を呼び出すし、WCF サービス モデルでの BAPI のトランザクションのサポートについて説明する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fd938-114">The following sections show you how to invoke BAPIs as methods of business objects and discuss how BAPI transactions are supported in the WCF service model.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="fd938-115">WCF クライアント クラス</span><span class="sxs-lookup"><span data-stu-id="fd938-115">The WCF Client Class</span></span>  
 <span data-ttu-id="fd938-116">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]ビジネス オブジェクトごとに、別のサービス コントラクトを表示します。</span><span class="sxs-lookup"><span data-stu-id="fd938-116">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces a different service contract, for each business object.</span></span> <span data-ttu-id="fd938-117">これは、各ビジネス オブジェクトの一意の WCF クライアント クラスを作成することを意味します。</span><span class="sxs-lookup"><span data-stu-id="fd938-117">This means that for each business object a unique WCF client class is created.</span></span> <span data-ttu-id="fd938-118">このクラスの名前は、ビジネス オブジェクトの種類に基づいています。</span><span class="sxs-lookup"><span data-stu-id="fd938-118">The name of this class is based on the business object type.</span></span> <span data-ttu-id="fd938-119">たとえば、Sales Order ビジネス オブジェクト (ビジネス オブジェクトの種類 BUS2032) には、WCF クライアント クラスは**BapiBUS2032Client**です。</span><span class="sxs-lookup"><span data-stu-id="fd938-119">For example for the Sales Order business object (business object type BUS2032), the WCF client class is **BapiBUS2032Client**.</span></span> <span data-ttu-id="fd938-120">ビジネス オブジェクト内の各ターゲット BAPI は、生成された WCF クライアント クラスのメソッドとして表されます。</span><span class="sxs-lookup"><span data-stu-id="fd938-120">Each target BAPI in the business object is represented as a method in the generated WCF client class.</span></span> <span data-ttu-id="fd938-121">各メソッドには。</span><span class="sxs-lookup"><span data-stu-id="fd938-121">In each method:</span></span>  
  
-   <span data-ttu-id="fd938-122">SAP のエクスポートのパラメーターは、として表示された**アウト**パラメーター</span><span class="sxs-lookup"><span data-stu-id="fd938-122">SAP export parameters are surfaced as **out** parameters</span></span>  
  
-   <span data-ttu-id="fd938-123">SAP 呼び出しのパラメーターは、として表示された**ref**パラメーター。</span><span class="sxs-lookup"><span data-stu-id="fd938-123">SAP calling parameters are surfaced as **ref** parameters.</span></span>  
  
-   <span data-ttu-id="fd938-124">構造体など、SAP の複合型は、SAP の種類のフィールドに対応するプロパティを持つ .NET クラスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd938-124">Complex SAP types such as structures are surfaced as .NET classes with properties that correspond to the fields of the SAP type.</span></span> <span data-ttu-id="fd938-125">これらのクラスは、次の名前空間で定義されます: microsoft.lobservices.sap._2007._03.Types.Rfc です。</span><span class="sxs-lookup"><span data-stu-id="fd938-125">These classes are defined in the following namespace: microsoft.lobservices.sap._2007._03.Types.Rfc.</span></span>  
  
 <span data-ttu-id="fd938-126">BAPI_TRANSACTION_COMMIT と BAPI_TRANSACTION_ROLLBACK がビジネス オブジェクトごとに表示され、WCF クライアントでこれらを常に含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd938-126">BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK are surfaced for each business object and you should always include these in your WCF client.</span></span>  
  
 <span data-ttu-id="fd938-127">次のコードは、販売注文のビジネス オブジェクトに対して生成される WCF クライアント クラスの一部を示しています。</span><span class="sxs-lookup"><span data-stu-id="fd938-127">The following code shows part of a WCF client class generated for the Sales Order business object.</span></span> <span data-ttu-id="fd938-128">このクライアントには、CREATEFROMDAT2、BAPI_TRANSACTION_COMMIT および BAPI_TRANSACTION_ROLLBACK を呼び出すメソッドが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fd938-128">This client contains methods to invoke CREATEFROMDAT2, BAPI_TRANSACTION_COMMIT and BAPI_TRANSACTION_ROLLBACK.</span></span> <span data-ttu-id="fd938-129">わかりやすくするためには、コンス トラクターおよびその他のコードを省略されています。</span><span class="sxs-lookup"><span data-stu-id="fd938-129">For clarity the constructors and other code has been omitted.</span></span>  
  
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
  
## <a name="bapi-transactions-in-the-wcf-service-model"></a><span data-ttu-id="fd938-130">WCF サービス モデルでの BAPI のトランザクション</span><span class="sxs-lookup"><span data-stu-id="fd938-130">BAPI Transactions in the WCF Service Model</span></span>  
 <span data-ttu-id="fd938-131">すべての BAPI RFC、またはビジネス オブジェクトのメソッドとしてメソッドが呼び出されたかどうかの一部であるトランザクション (LUW)、SAP システムで同じ SAP 接続経由で受信したすべての BAPI の SAP システムでの同じ BAPI トランザクションの一部であります。</span><span class="sxs-lookup"><span data-stu-id="fd938-131">Every BAPI, whether it is invoked as an RFC or as a business object method, is part of a transaction (LUW) on the SAP system; and every BAPI received over the same SAP connection is part of the same BAPI transaction on the SAP system.</span></span> <span data-ttu-id="fd938-132">SAP がコミットまたは、BAPI_TRANSACTION_COMMIT または接続で BAPI_TRANSACTION_ROLLBACK を受信したときに、BAPI トランザクションをロールバックします。</span><span class="sxs-lookup"><span data-stu-id="fd938-132">SAP commits or rolls back the BAPI transaction when it receives a BAPI_TRANSACTION_COMMIT or a BAPI_TRANSACTION_ROLLBACK on the connection.</span></span> <span data-ttu-id="fd938-133">コミットまたはロールバックが実行された後、接続経由で受信した次の BAPI は新しいトランザクションを開始します。</span><span class="sxs-lookup"><span data-stu-id="fd938-133">After a commit or rollback has been performed, the next BAPI received over the connection begins a new transaction.</span></span>  
  
 <span data-ttu-id="fd938-134">アダプターは、各 WCF チャネルは、専用の SAP 接続がします。</span><span class="sxs-lookup"><span data-stu-id="fd938-134">For the adapter each WCF channel has a dedicated SAP connection.</span></span> <span data-ttu-id="fd938-135">WCF サービス モデルで、各 WCF クライアントに使用される送信メッセージを SAP システムである内部チャネルがあります。</span><span class="sxs-lookup"><span data-stu-id="fd938-135">In the WCF service model, each WCF client has an inner channel that is used send messages to the SAP system.</span></span> <span data-ttu-id="fd938-136">これは、特定の WCF クライアントを使用して呼び出される Bapi SAP システムで一意の BAPI トランザクションの一部であることを意味します。</span><span class="sxs-lookup"><span data-stu-id="fd938-136">This means that the BAPIs that are invoked using a specific WCF client are part of a unique BAPI transaction on the SAP system.</span></span> <span data-ttu-id="fd938-137">これにより、モデルを使用して、WCF サービスをビジネス オブジェクト メソッドとして Bapi を呼び出す際に重要な制限です。</span><span class="sxs-lookup"><span data-stu-id="fd938-137">This imposes a significant limitation when you use the WCF service model to invoke BAPIs as business object methods.</span></span> <span data-ttu-id="fd938-138">SAP business の各オブジェクトは、専用の WCF クライアント クラスで表される、ために、同じトランザクションの一部として 2 つの異なるビジネス オブジェクトから Bapi を呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="fd938-138">Because each SAP business object is represented by a dedicated WCF client class, you cannot invoke BAPIs from two different business objects as part of the same transaction.</span></span> <span data-ttu-id="fd938-139">この問題を回避方法では、RFC 操作として Bapi を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fd938-139">The way around this is to invoke the BAPIs as RFC operations.</span></span> <span data-ttu-id="fd938-140">これは、ため、 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] RFC 操作の場合は、1 つの WCF クライアントを生成し、そのクライアントを使用して呼び出されたすべての操作が同じ WCF チャネル経由で送信されるため、します。</span><span class="sxs-lookup"><span data-stu-id="fd938-140">This is because the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] generates a single WCF client for RFC operations, and, therefore, all operations invoked using that client are sent over the same WCF channel.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fd938-141">同じ BAPI トランザクション内で異なる SAP ビジネス オブジェクトの Bapi を含める場合は、(同じ WCF クライアントを使用) の RFC 操作として呼び出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd938-141">If you want to include BAPIs from different SAP business objects in the same BAPI transaction, you must invoke them as RFC operations (using the same WCF client).</span></span> <span data-ttu-id="fd938-142">ビジネス オブジェクト メソッドとして呼び出すことはできません。</span><span class="sxs-lookup"><span data-stu-id="fd938-142">You cannot invoke them as business object methods.</span></span>  
  
 <span data-ttu-id="fd938-143">コミットまたは SAP システムでの BAPI のトランザクションがロールバックするには、BAPI_TRANSACTION_COMMIT または BAPI_TRANSACTION_ROLLBACK を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fd938-143">You call BAPI_TRANSACTION_COMMIT or BAPI_TRANSACTION_ROLLBACK to commit or roll back the BAPI transaction on the SAP system.</span></span> <span data-ttu-id="fd938-144">アダプターは、これら 2 つの Bapi を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd938-144">The adapter surfaces these two BAPIs:</span></span>  
  
-   <span data-ttu-id="fd938-145">RFC 操作として [基準] ノードの下。</span><span class="sxs-lookup"><span data-stu-id="fd938-145">Under the Basis node as RFC operations.</span></span>  
  
-   <span data-ttu-id="fd938-146">各ビジネス オブジェクト。</span><span class="sxs-lookup"><span data-stu-id="fd938-146">Under each business object.</span></span>  
  
 <span data-ttu-id="fd938-147">アダプターが SAP で BAPI トランザクションをサポートする方法の詳細については、次を参照してください。 [SAP での Bapi の操作](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd938-147">For more information about how the adapter supports BAPI transactions on SAP, see [Operations on BAPIs in SAP](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md).</span></span>  
  
## <a name="how-to-create-an-application-that-invokes-bapis-as-methods-of-business-objects"></a><span data-ttu-id="fd938-148">ビジネス オブジェクトのメソッドとして Bapi を起動するアプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="fd938-148">How to Create an Application that Invokes BAPIs as Methods of Business Objects</span></span>  
 <span data-ttu-id="fd938-149">このセクションでは、ビジネス オブジェクトのメソッドとして Bapi を起動する方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="fd938-149">This section provides information about how to invoke BAPIs as methods of business objects.</span></span> <span data-ttu-id="fd938-150">同じ基本的な手順は、WCF クライアントを対象とする RFC 操作として Bapi を作成し、各 BAPI の呼び出しに使用する点を除いて RFC 操作として Bapi を呼び出すに従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd938-150">The same basic procedure should be followed to invoke BAPIs as RFC operations, except that you create a WCF client that targets the BAPIs as RFC operations and use it to invoke each BAPI.</span></span>  
  
 <span data-ttu-id="fd938-151">BAPI のクライアント アプリケーションを作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="fd938-151">To create a BAPI client application, perform the following steps.</span></span>  
  
#### <a name="to-create-an-bapi-client-application"></a><span data-ttu-id="fd938-152">BAPI クライアント アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="fd938-152">To create an BAPI client application</span></span>  
  
1.  <span data-ttu-id="fd938-153">WCF クライアント クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="fd938-153">Generate a WCF client class.</span></span> <span data-ttu-id="fd938-154">使用して、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラス (またはクラス) を生成するビジネス オブジェクトを対象として Bapi 操作するか。</span><span class="sxs-lookup"><span data-stu-id="fd938-154">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] or the ServiceModel Metadata Utility Tool (svcutil.exe) to generate a WCF client class (or classes) that targets the business objects and BAPIs with which you want to work.</span></span> <span data-ttu-id="fd938-155">必ず、BAPI_TRANSACTION_COMMIT と各ターゲット ビジネス オブジェクトの公開された BAPI_TRANSACTION_ROLLBACK メソッド (Bapi) を含めるようにします。</span><span class="sxs-lookup"><span data-stu-id="fd938-155">Be sure to include the BAPI_TRANSACTION_COMMIT and the BAPI_TRANSACTION_ROLLBACK methods (BAPIs) exposed for each target business object.</span></span> <span data-ttu-id="fd938-156">WCF クライアントを生成する方法の詳細については、次を参照してください。 [SAP ソリューションの成果物のため、WCF クライアントまたは WCF サービス コントラクトを生成する](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd938-156">For more information about how to generate a WCF client, see [Generating a WCF Client or a WCF Service Contract for SAP Solution Artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="fd938-157">手順 1 で生成される WCF クライアント クラスのインスタンスを作成して作成し、WCF クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="fd938-157">Create an instance of the WCF client class generated in step 1, and create and configure a WCF client.</span></span> <span data-ttu-id="fd938-158">WCF クライアントを構成するには、バインディングと、クライアントが使用するエンドポイントのアドレス指定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="fd938-158">Configuring the WCF client involves specifying the binding and endpoint address that the client will use.</span></span> <span data-ttu-id="fd938-159">これは、コードで命令として記述または構成で宣言によって行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fd938-159">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="fd938-160">クライアントのバインディングを指定する方法の詳細については、次を参照してください。 [、SAP システムのクライアントのバインディングを構成する](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd938-160">For more information about how to specify a client binding, see [Configure a Client Binding for the SAP System](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md).</span></span> <span data-ttu-id="fd938-161">次のコードは、Sales Order (BUS2032) SAP ビジネス オブジェクトの構成から WCF クライアントを初期化し、SAP システムの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="fd938-161">The following code initializes the WCF client for the Sales Order (BUS2032) SAP business object from configuration and sets the credentials for the SAP system.</span></span>  
  
    ```  
    BapiBUS2032Client bapiClient = new BapiBUS2032Client("SAPBinding_BapiBUS2032");  
  
    bapiClient.ClientCredentials.UserName.UserName = "YourUserName";  
    bapiClient.ClientCredentials.UserName.Password = "YourPassword";  
    ```  
  
3.  <span data-ttu-id="fd938-162">WCF クライアントを開きます。</span><span class="sxs-lookup"><span data-stu-id="fd938-162">Open the WCF client.</span></span>  
  
    ```  
    bapiClient.Open();  
    ```  
  
4.  <span data-ttu-id="fd938-163">SAP システムでの Bapi の適切なを起動する手順 2. で作成された WCF クライアントでメソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fd938-163">Invoke methods on the WCF client created in step 2 to invoke the appropriate BAPIs on the SAP system.</span></span> <span data-ttu-id="fd938-164">SAP システムでの Bapi の複数を呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fd938-164">You can invoke multiple BAPIs on the SAP system.</span></span>  
  
5.  <span data-ttu-id="fd938-165">トランザクションを終了します。</span><span class="sxs-lookup"><span data-stu-id="fd938-165">End the transaction by:</span></span>  
  
    1.  <span data-ttu-id="fd938-166">トランザクションをコミットする BAPI_TRANSACTION_COMMIT メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="fd938-166">Invoking the BAPI_TRANSACTION_COMMIT method to commit the transaction.</span></span>  
  
        ```  
        bapiClient.BAPI_TRANSACTION_COMMIT("X");  
        ```  
  
    2.  <span data-ttu-id="fd938-167">トランザクションをロールバックする BAPI_TRANSACTION_ROLLBACK メソッドの呼び出し。</span><span class="sxs-lookup"><span data-stu-id="fd938-167">Invoking the BAPI_TRANSACTION_ROLLBACK method to roll back the transaction.</span></span>  
  
        ```  
        bapiClient.BAPI_TRANSACTION_ROLLBACK();  
        ```  
  
6.  <span data-ttu-id="fd938-168">WCF クライアントを閉じます。</span><span class="sxs-lookup"><span data-stu-id="fd938-168">Close the WCF client.</span></span>  
  
    ```  
    bapiClient.Close();   
    ```  
  
### <a name="example"></a><span data-ttu-id="fd938-169">例</span><span class="sxs-lookup"><span data-stu-id="fd938-169">Example</span></span>  
 <span data-ttu-id="fd938-170">次の例では、販売注文のビジネス オブジェクトで CREATEFROMDAT2 BAPI を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fd938-170">The following example invokes the CREATEFROMDAT2 BAPI on the Sales Order business object.</span></span> <span data-ttu-id="fd938-171">BAPI を数回呼び出し、トランザクションをコミットする BAPI_TRANSACTION_COMMIT を呼び出します。</span><span class="sxs-lookup"><span data-stu-id="fd938-171">It invokes the BAPI several times and then invokes BAPI_TRANSACTION_COMMIT to commit the transaction.</span></span> <span data-ttu-id="fd938-172">BAPI を呼び出すときに、エラーが発生する場合は、トランザクションをロールバックして、例外ハンドラーの BAPI_TRANSACTION_ROLLBACK が呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fd938-172">If an error occurs when invoking the BAPI, BAPI_TRANSACTION_ROLLBACK is invoked in the exception handler to roll back the transaction.</span></span>  
  
 <span data-ttu-id="fd938-173">CREATEFROMDAT2 メソッドは多くのパラメーターです。これらは、ここでは簡略化のための例では省略されます。</span><span class="sxs-lookup"><span data-stu-id="fd938-173">The CREATEFROMDAT2 method takes many parameters; these are omitted in the example for the sake of brevity.</span></span> <span data-ttu-id="fd938-174">Microsoft に付属のサンプルでの BAPI のトランザクションを示すサンプルが見つかります[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="fd938-174">You can find a sample that demonstrates BAPI transactions in the samples shipped with the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="fd938-175">詳細については、次を参照してください。 [SAP アダプターのサンプル](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="fd938-175">For more information, see [Samples for the SAP Adapter ](../../adapters-and-accelerators/adapter-sap/samples-for-the-sap-adapter.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fd938-176">参照</span><span class="sxs-lookup"><span data-stu-id="fd938-176">See Also</span></span>  
[<span data-ttu-id="fd938-177">WCF サービス モデルを使用してアプリケーションを開発します。</span><span class="sxs-lookup"><span data-stu-id="fd938-177">Develop applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)  
 [<span data-ttu-id="fd938-178">SAP での Bapi の操作</span><span class="sxs-lookup"><span data-stu-id="fd938-178">Operations on BAPIs in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/operations-on-bapis-in-sap.md)