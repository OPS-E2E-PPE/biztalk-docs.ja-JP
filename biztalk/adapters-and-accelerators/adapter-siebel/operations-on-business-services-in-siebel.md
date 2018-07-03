---
title: Siebel ビジネス サービスに対する操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24fa8ee0bd51ddf919e5f88a47ceae9d0743fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001371"
---
# <a name="operations-on-business-services-in-siebel"></a><span data-ttu-id="f2ced-102">Siebel ビジネス サービスに対する操作</span><span class="sxs-lookup"><span data-stu-id="f2ced-102">Operations on Business Services in Siebel</span></span>
<span data-ttu-id="f2ced-103">Siebel ビジネス サービスは、Siebel に直接呼び出すことができるビジネス メソッドのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="f2ced-103">A Siebel business service is a collection of business methods that can be directly invoked in Siebel.</span></span> <span data-ttu-id="f2ced-104">一方、ビジネス コンポーネントとビジネス オブジェクトが特定のデータ、および Siebel のテーブルに関連付けられていると、ビジネス サービスは、特定のタスクを実行するオブジェクトを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="f2ced-104">Whereas business components and business objects are associated to specific data and tables in Siebel, business services invoke the objects to perform specific tasks.</span></span>  
  
 <span data-ttu-id="f2ced-105">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]操作名し、サポート、IN、OUT および INOUT パラメーターとビジネス サービス メソッドは、明らかになります。</span><span class="sxs-lookup"><span data-stu-id="f2ced-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the business service methods as operation names and supports IN, OUT, and INOUT parameters.</span></span> <span data-ttu-id="f2ced-106">たとえば、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]サーフェス、 **ATPRunCheck**操作としてメソッド。</span><span class="sxs-lookup"><span data-stu-id="f2ced-106">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the **ATPRunCheck** method as an operation.</span></span> <span data-ttu-id="f2ced-107">このメソッドが属する、 **ATP**ビジネス サービス。</span><span class="sxs-lookup"><span data-stu-id="f2ced-107">This method belongs to the **ATP** business service.</span></span>  
  
 <span data-ttu-id="f2ced-108">特定の条件、 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel ビジネス サービスを使用しているときに。</span><span class="sxs-lookup"><span data-stu-id="f2ced-108">Certain conditions that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] imposes while using the Siebel business services:</span></span>  
  
- <span data-ttu-id="f2ced-109">Siebel ビジネス サービス メソッドが指定されたデータ型がない引数を受け取る場合、アダプターは、テキストとして、引数を公開します。</span><span class="sxs-lookup"><span data-stu-id="f2ced-109">If a Siebel business service method takes an argument that does not have the data type specified, the adapter exposes the argument as TEXT.</span></span>  
  
- <span data-ttu-id="f2ced-110">Siebel ビジネス サービス メソッドの引数は、次の種類のできます。</span><span class="sxs-lookup"><span data-stu-id="f2ced-110">A Siebel business service method argument can be of the following types:</span></span>  
  
  - <span data-ttu-id="f2ced-111">文字列 (xsd:string として公開)</span><span class="sxs-lookup"><span data-stu-id="f2ced-111">String (exposed as xsd:string)</span></span>  
  
  - <span data-ttu-id="f2ced-112">数 (xsd として公開します 10 進数)。</span><span class="sxs-lookup"><span data-stu-id="f2ced-112">Number (exposed as xsd: decimal)</span></span>  
  
  - <span data-ttu-id="f2ced-113">日付 (時刻部分が 00時 00分: 00 に設定する必要がありますでパターン ファセットを示すの xsd:DateTime として公開)</span><span class="sxs-lookup"><span data-stu-id="f2ced-113">Date (exposed as xsd:DateTime, with pattern facet indicating that time part must be set to 00:00:00)</span></span>  
  
  - <span data-ttu-id="f2ced-114">階層 (xsd:string として公開)</span><span class="sxs-lookup"><span data-stu-id="f2ced-114">Hierarchy (exposed as xsd:string)</span></span>  
  
  - <span data-ttu-id="f2ced-115">(Xsd:string として公開) の統合オブジェクト</span><span class="sxs-lookup"><span data-stu-id="f2ced-115">Integration Object (exposed as xsd:string)</span></span>  
  
    <span data-ttu-id="f2ced-116">また、ビジネス サービス メソッドでは、引数に渡された値が、対応する型に準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="f2ced-116">Also, the business service method verifies whether the value passed for an argument complies with the corresponding type.</span></span> <span data-ttu-id="f2ced-117">したがって、ビジネス サービス メソッドを受け入れるか、対応する引数の型に準拠していない値を返す場合、アダプターが例外をスローします。</span><span class="sxs-lookup"><span data-stu-id="f2ced-117">So, if a business service method accepts or returns values that do not comply with the corresponding argument type, the adapter may throw an exception.</span></span> <span data-ttu-id="f2ced-118">ビジネス サービス メソッドを呼び出す際に、アダプターが成功した場合、スキーマの検証が失敗します。</span><span class="sxs-lookup"><span data-stu-id="f2ced-118">If the adapter does succeed in invoking the business service method, the schema validation may fail.</span></span>  
  
  <span data-ttu-id="f2ced-119">詳細については。</span><span class="sxs-lookup"><span data-stu-id="f2ced-119">For information about:</span></span>  
  
- <span data-ttu-id="f2ced-120">BizTalk Server を使用してビジネス サービスに対する操作を実行するを参照してください[呼び出すビジネス サービス メソッドを使用して BizTalk Server と Siebel アダプター](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)します。</span><span class="sxs-lookup"><span data-stu-id="f2ced-120">Performing operations on business services using BizTalk Server, see [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
- <span data-ttu-id="f2ced-121">メッセージの構造と SOAP アクションのビジネス サービスに対する操作の実行を参照してください[ビジネス サービス操作のメッセージ スキーマ](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md))。</span><span class="sxs-lookup"><span data-stu-id="f2ced-121">Message structures and SOAP actions to perform operations on business services, see [Message Schemas for Business Service Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ced-122">参照</span><span class="sxs-lookup"><span data-stu-id="f2ced-122">See Also</span></span>  
 [<span data-ttu-id="f2ced-123">アダプターを使用して SAP システムへの接続します。</span><span class="sxs-lookup"><span data-stu-id="f2ced-123">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)