---
title: "Siebel ビジネス サービスに対する操作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1ffd133d76b1f8cae3f1732e48f817fe4fb26b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-business-services-in-siebel"></a><span data-ttu-id="ce7e4-102">Siebel ビジネス サービスに対する操作</span><span class="sxs-lookup"><span data-stu-id="ce7e4-102">Operations on Business Services in Siebel</span></span>
<span data-ttu-id="ce7e4-103">Siebel ビジネス サービスは、Siebel の直接呼び出すことができるビジネス メソッドのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-103">A Siebel business service is a collection of business methods that can be directly invoked in Siebel.</span></span> <span data-ttu-id="ce7e4-104">ビジネス コンポーネントとビジネス オブジェクトは、特定のデータと Siebel のテーブルに関連付けられているは、ビジネス サービスは、特定のタスクを実行するオブジェクトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-104">Whereas business components and business objects are associated to specific data and tables in Siebel, business services invoke the objects to perform specific tasks.</span></span>  
  
 <span data-ttu-id="ce7e4-105">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェスのビジネス サービス メソッドのように操作名し、IN、OUT、および INOUT のパラメーターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the business service methods as operation names and supports IN, OUT, and INOUT parameters.</span></span> <span data-ttu-id="ce7e4-106">たとえば、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェス、 **ATPRunCheck**操作としてメソッドです。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-106">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the **ATPRunCheck** method as an operation.</span></span> <span data-ttu-id="ce7e4-107">このメソッドが属する、 **ATP**ビジネス サービス。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-107">This method belongs to the **ATP** business service.</span></span>  
  
 <span data-ttu-id="ce7e4-108">特定の状態です、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel ビジネス サービスを使用しているときに。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-108">Certain conditions that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] imposes while using the Siebel business services:</span></span>  
  
-   <span data-ttu-id="ce7e4-109">Siebel ビジネス サービス メソッドは、指定されたデータ型がない引数を受け取り、アダプターは、引数をテキストとして公開します。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-109">If a Siebel business service method takes an argument that does not have the data type specified, the adapter exposes the argument as TEXT.</span></span>  
  
-   <span data-ttu-id="ce7e4-110">次の種類の Siebel ビジネス サービス メソッドの引数になります。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-110">A Siebel business service method argument can be of the following types:</span></span>  
  
    -   <span data-ttu-id="ce7e4-111">文字列 (xsd:string として公開)</span><span class="sxs-lookup"><span data-stu-id="ce7e4-111">String (exposed as xsd:string)</span></span>  
  
    -   <span data-ttu-id="ce7e4-112">数 (xsd として公開します 10 進数)。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-112">Number (exposed as xsd: decimal)</span></span>  
  
    -   <span data-ttu-id="ce7e4-113">日付 (時刻部分は 00時 00分: 00 に設定する必要がありますでパターン ファセットを示すの xsd:DateTime として公開)</span><span class="sxs-lookup"><span data-stu-id="ce7e4-113">Date (exposed as xsd:DateTime, with pattern facet indicating that time part must be set to 00:00:00)</span></span>  
  
    -   <span data-ttu-id="ce7e4-114">階層 (xsd:string として公開)</span><span class="sxs-lookup"><span data-stu-id="ce7e4-114">Hierarchy (exposed as xsd:string)</span></span>  
  
    -   <span data-ttu-id="ce7e4-115">統合オブジェクト (xsd:string として公開)</span><span class="sxs-lookup"><span data-stu-id="ce7e4-115">Integration Object (exposed as xsd:string)</span></span>  
  
     <span data-ttu-id="ce7e4-116">また、ビジネス サービス メソッドでは、引数に渡された値が、対応する型に準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-116">Also, the business service method verifies whether the value passed for an argument complies with the corresponding type.</span></span> <span data-ttu-id="ce7e4-117">そのため、ビジネス サービス メソッドを受け入れるか、対応する引数の型に準拠していない値を返す場合、アダプターは例外をスロー可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-117">So, if a business service method accepts or returns values that do not comply with the corresponding argument type, the adapter may throw an exception.</span></span> <span data-ttu-id="ce7e4-118">ビジネス サービス メソッドの呼び出しに成功しますが、アダプター スキーマの検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-118">If the adapter does succeed in invoking the business service method, the schema validation may fail.</span></span>  
  
 <span data-ttu-id="ce7e4-119">詳細については。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-119">For information about:</span></span>  
  
-   <span data-ttu-id="ce7e4-120">BizTalk Server を使用してサービスをビジネス上の操作を実行するを参照してください[呼び出すビジネス サービス メソッドを使用して BizTalk Server と Siebel アダプター](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)です。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-120">Performing operations on business services using BizTalk Server, see [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
-   <span data-ttu-id="ce7e4-121">メッセージの構造と SOAP アクションのビジネス サービスでの操作を実行するを参照してください[ビジネス サービス操作のメッセージ スキーマを](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md))。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-121">Message structures and SOAP actions to perform operations on business services, see [Message Schemas for Business Service Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce7e4-122">参照</span><span class="sxs-lookup"><span data-stu-id="ce7e4-122">See Also</span></span>  
 [<span data-ttu-id="ce7e4-123">アダプターを使用して SAP システムへの接続します。</span><span class="sxs-lookup"><span data-stu-id="ce7e4-123">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)