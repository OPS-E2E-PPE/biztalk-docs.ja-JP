---
title: CreateEx メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CreateEx method
ms.assetid: b62bbe25-b24d-42a7-a44c-c83521a6f0a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b163bfbe7811c37208297aa0a61bfe91cabacde4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238290"
---
# <a name="createex-method"></a><span data-ttu-id="0b0f9-102">CreateEx メソッド</span><span class="sxs-lookup"><span data-stu-id="0b0f9-102">CreateEx Method</span></span>
<span data-ttu-id="0b0f9-103">一意なキーと指定されたプロパティを使用して新しいレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-103">Creates a new record using a set of unique keys and specified properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b0f9-104">構文</span><span class="sxs-lookup"><span data-stu-id="0b0f9-104">Syntax</span></span>  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b0f9-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b0f9-105">Parameters</span></span>  
  
|<span data-ttu-id="0b0f9-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0b0f9-106">Parameter</span></span>|<span data-ttu-id="0b0f9-107">Description</span><span class="sxs-lookup"><span data-stu-id="0b0f9-107">Description</span></span>|  
|---------------|-----------------|  
|`Key in/out parameter`|<span data-ttu-id="0b0f9-108">個々のキー パラメーター (key1、key2、... keyn)。このパラメーターは必須です。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-108">Individual key parameters (key1, key2, ... keyn), which must be supplied.</span></span><br /><br /> <span data-ttu-id="0b0f9-109">このキー セットは、サーバー データベースに存在しないものである、つまり、一意である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-109">This set of keys must not exist in the server database, that is, they must be unique.</span></span><br /><br /> <span data-ttu-id="0b0f9-110">これらのキーは、特定のコンポーネント インターフェイスで定義された CreateEx Keys のセットに対応します。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-110">These keys correspond to the set of CreateEx Keys as defined for the particular component interface.</span></span>|  
|`interactiveMode`|<span data-ttu-id="0b0f9-111">エラー処理。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-111">Error handling.</span></span><br /><br /> <span data-ttu-id="0b0f9-112">コンポーネント インターフェイスでプロパティにアクセスする場合、Microsoft BizTalk Adapter for PeopleSoft Enterprise では、PeopleSoft から提供されている API を使用してコンポーネント インターフェイス内の個々のフィールドを読み書きします。ただし、これらの変更は一度に 1 つずつ PeopleSoft サーバーに伝達されるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-112">When accessing properties in a component interface, Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft-provided APIs, which read and write individual fields in the component interface; however, these changes are not propagated to the PeopleSoft server one at a time.</span></span> <span data-ttu-id="0b0f9-113">代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と対話) が、すべての変更を 1 つのパッケージにしてサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-113">Instead, the psjoa.jar (with which the BizTalk Adapter for PeopleSoft Enterprise interacts) packages all the changes and sends the changes to the server in one package.</span></span><br /><br /> <span data-ttu-id="0b0f9-114">個別の更新が失敗した場合、汎用エラーが返されます。このエラーは、実際のエラーを特定しません。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-114">If any of the individual updates fail, a generic error is returned, which does not pinpoint the actual error.</span></span> <span data-ttu-id="0b0f9-115">対話モードを TRUE に設定することで、すべてのフィールド更新がサーバーに個別に送信されます。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-115">With the interactive mode set to TRUE, every field update is sent to the server individually.</span></span> <span data-ttu-id="0b0f9-116">これによってパフォーマンスに大きな影響が及びますが、更新が失敗した場合 (たとえば、フィールドの設定に無効な値が使用された場合) には、具体的なエラー情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-116">This has a substantial impact on performance, but it does provide specific error information if the update fails (for example, if an invalid value is used for setting a field).</span></span><br /><br /> <span data-ttu-id="0b0f9-117">interactiveMode は最大のパフォーマンスを発揮し、フィールド更新レベルでエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-117">The interactiveMode provides maximum performance and provides error reporting at the field update level.</span></span> <span data-ttu-id="0b0f9-118">この機能を正しく使用できるように、interactiveMode を FALSE に設定して通常の呼び出しを行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-118">To use this feature properly, it is recommended that normal calls be made with the interactiveMode set to FALSE.</span></span> <span data-ttu-id="0b0f9-119">パフォーマンスへの影響はありません。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-119">There should be no impact on performance.</span></span> <span data-ttu-id="0b0f9-120">エラーが返された場合は、interactiveMode フラグを TRUE に設定して同じ呼び出しを再試行できます。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-120">If an error is returned, the same call can be retried with the interactiveMode flag set to TRUE.</span></span> <span data-ttu-id="0b0f9-121">呼び出しが失敗した場合、サーバーはより正確なエラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-121">When the call fails, the server returns a more precise error message.</span></span>|  
|`properties`|<span data-ttu-id="0b0f9-122">コンポーネント インターフェイスのすべてのプロパティを含む構造体。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-122">A structure that contains all the properties of the component interface.</span></span> <span data-ttu-id="0b0f9-123">`CreateEx` メソッドが呼び出されると、これらのプロパティは、指定されたキーで作成されたレコードに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-123">When the `CreateEx` method is called, these properties are inserted into the record created with the specified key(s).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b0f9-124">解説</span><span class="sxs-lookup"><span data-stu-id="0b0f9-124">Remarks</span></span>  
 <span data-ttu-id="0b0f9-125">明示的なキー セットを指定せずに `CreateEx()` を呼び出すのが一般的な場合もありますが、`CreateEx` 関数はキーを返します。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-125">In some situations, it is common practice to call `CreateEx()` without a set of explicit keys, but the `CreateEx` function returns the keys.</span></span> <span data-ttu-id="0b0f9-126">この動作は、サーバーで実行される PeopleCode でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-126">This behavior is supported with PeopleCode that gets triggered on the server.</span></span> <span data-ttu-id="0b0f9-127">たとえば、注文書を作成する場合、クライアントには次に利用できる PO 番号がわからないことがあります。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-127">For example, to create a purchase order, the client may not know what the next available PO number is.</span></span> <span data-ttu-id="0b0f9-128">PO 番号キーに NEXT を指定して呼び出すことで PeopleCode が実行され、次に利用できる PO 番号が設定されます。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-128">By specifying NEXT as the PO number key, the call triggers PeopleCode, which determines the next available PO number.</span></span> <span data-ttu-id="0b0f9-129">この情報は、in/out キー パラメーターを使用して呼び出し元のクライアントに返される必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-129">This information must be returned to the calling client, using the in/out key parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b0f9-130">このしくみが機能するには、キーはレベル 0 のプロパティもする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-130">For this mechanism to work, the key must also be a property at level 0.</span></span> <span data-ttu-id="0b0f9-131">それ以外の場合、元のキーが返されます。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-131">Otherwise, the original key is returned.</span></span>  
  
 <span data-ttu-id="0b0f9-132">BizTalk Adapter for PeopleSoft Enterprise の `CreateEx()` メソッドが提供されるのは、コンポーネント インターフェイスで PeopleSoft の Create 関数および Save 関数が有効になっている場合です。</span><span class="sxs-lookup"><span data-stu-id="0b0f9-132">The BizTalk Adapter for PeopleSoft Enterprise `CreateEx()` method is provided if the PeopleSoft Create and Save functions in the component interface are enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b0f9-133">参照</span><span class="sxs-lookup"><span data-stu-id="0b0f9-133">See Also</span></span>  
 [<span data-ttu-id="0b0f9-134">付録 a: コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="0b0f9-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)