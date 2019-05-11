---
title: CreateEx メソッド |Microsoft Docs
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
ms.openlocfilehash: 23163739b18febd5642a704a6910241928e85730
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390117"
---
# <a name="createex-method"></a><span data-ttu-id="eff69-102">CreateEx メソッド</span><span class="sxs-lookup"><span data-stu-id="eff69-102">CreateEx Method</span></span>
<span data-ttu-id="eff69-103">一意なキーと指定されたプロパティのセットを使用して新しいレコードを作成します。</span><span class="sxs-lookup"><span data-stu-id="eff69-103">Creates a new record using a set of unique keys and specified properties.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eff69-104">構文</span><span class="sxs-lookup"><span data-stu-id="eff69-104">Syntax</span></span>  
  
```  
CreateEx  
(key1, key2, ..., keyn, interactiveMode, properties)  
```  
  
## <a name="parameters"></a><span data-ttu-id="eff69-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eff69-105">Parameters</span></span>  
  
|<span data-ttu-id="eff69-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="eff69-106">Parameter</span></span>|<span data-ttu-id="eff69-107">説明</span><span class="sxs-lookup"><span data-stu-id="eff69-107">Description</span></span>|  
|---------------|-----------------|  
|`Key in/out parameter`|<span data-ttu-id="eff69-108">個々 のキー パラメーター (key1、key2、...keyn) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eff69-108">Individual key parameters (key1, key2, ... keyn), which must be supplied.</span></span><br /><br /> <span data-ttu-id="eff69-109">このキーのセットがサーバー データベースに存在する必要があります、これは、一意でなければなりません。</span><span class="sxs-lookup"><span data-stu-id="eff69-109">This set of keys must not exist in the server database, that is, they must be unique.</span></span><br /><br /> <span data-ttu-id="eff69-110">これらのキーは、特定のコンポーネント インターフェイスに定義された CreateEx Keys のセットに対応します。</span><span class="sxs-lookup"><span data-stu-id="eff69-110">These keys correspond to the set of CreateEx Keys as defined for the particular component interface.</span></span>|  
|`interactiveMode`|<span data-ttu-id="eff69-111">エラー処理します。</span><span class="sxs-lookup"><span data-stu-id="eff69-111">Error handling.</span></span><br /><br /> <span data-ttu-id="eff69-112">Microsoft BizTalk Adapter for PeopleSoft Enterprise が PeopleSoft が提供する Api、;、コンポーネント インターフェイスで個々 のフィールドを読み書きするを使用してコンポーネント インターフェイスでプロパティにアクセスするときただし、これらの変更は、一度に 1 つずつ PeopleSoft サーバーに反映されませんが。</span><span class="sxs-lookup"><span data-stu-id="eff69-112">When accessing properties in a component interface, Microsoft BizTalk Adapter for PeopleSoft Enterprise uses PeopleSoft-provided APIs, which read and write individual fields in the component interface; however, these changes are not propagated to the PeopleSoft server one at a time.</span></span> <span data-ttu-id="eff69-113">代わりに、psjoa.jar (BizTalk Adapter for PeopleSoft Enterprise と連携する) では、すべての変更をパッケージ化し、1 つのパッケージ内のサーバーに変更を送信します。</span><span class="sxs-lookup"><span data-stu-id="eff69-113">Instead, the psjoa.jar (with which the BizTalk Adapter for PeopleSoft Enterprise interacts) packages all the changes and sends the changes to the server in one package.</span></span><br /><br /> <span data-ttu-id="eff69-114">個々 の更新プログラムのいずれかが失敗した場合、汎用的なエラーが返されますが、実際のエラーを特定していません。</span><span class="sxs-lookup"><span data-stu-id="eff69-114">If any of the individual updates fail, a generic error is returned, which does not pinpoint the actual error.</span></span> <span data-ttu-id="eff69-115">対話モードを TRUE に設定、すべてのフィールドの更新プログラムは、サーバーに個別に送信されます。</span><span class="sxs-lookup"><span data-stu-id="eff69-115">With the interactive mode set to TRUE, every field update is sent to the server individually.</span></span> <span data-ttu-id="eff69-116">これは、パフォーマンスに大きな影響がありますが (たとえば、フィールドを設定するために無効な値が使用されます) 場合、更新が失敗した場合は、特定のエラー情報は提供します。</span><span class="sxs-lookup"><span data-stu-id="eff69-116">This has a substantial impact on performance, but it does provide specific error information if the update fails (for example, if an invalid value is used for setting a field).</span></span><br /><br /> <span data-ttu-id="eff69-117">InteractiveMode は最大のパフォーマンスを提供し、フィールド更新レベルでエラーを報告を提供します。</span><span class="sxs-lookup"><span data-stu-id="eff69-117">The interactiveMode provides maximum performance and provides error reporting at the field update level.</span></span> <span data-ttu-id="eff69-118">この機能を正しく使用するには、interactiveMode を FALSE に設定すると、通常の呼び出しが行われることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eff69-118">To use this feature properly, it is recommended that normal calls be made with the interactiveMode set to FALSE.</span></span> <span data-ttu-id="eff69-119">あるは影響はないパフォーマンスにします。</span><span class="sxs-lookup"><span data-stu-id="eff69-119">There should be no impact on performance.</span></span> <span data-ttu-id="eff69-120">エラーが返された場合、interactiveMode フラグを TRUE に設定と同じ呼び出しを再試行できます。</span><span class="sxs-lookup"><span data-stu-id="eff69-120">If an error is returned, the same call can be retried with the interactiveMode flag set to TRUE.</span></span> <span data-ttu-id="eff69-121">呼び出しが失敗したときに、サーバーより正確なエラー メッセージを返します。</span><span class="sxs-lookup"><span data-stu-id="eff69-121">When the call fails, the server returns a more precise error message.</span></span>|  
|`properties`|<span data-ttu-id="eff69-122">コンポーネント インターフェイスのすべてのプロパティを含む構造体。</span><span class="sxs-lookup"><span data-stu-id="eff69-122">A structure that contains all the properties of the component interface.</span></span> <span data-ttu-id="eff69-123">ときに、`CreateEx`メソッドが呼び出されると、これらのプロパティは、指定されたキーで作成されたレコードに挿入されます。</span><span class="sxs-lookup"><span data-stu-id="eff69-123">When the `CreateEx` method is called, these properties are inserted into the record created with the specified key(s).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eff69-124">コメント</span><span class="sxs-lookup"><span data-stu-id="eff69-124">Remarks</span></span>  
 <span data-ttu-id="eff69-125">場合によってを呼び出す一般的`CreateEx()`せず、明示的なキーのセットが、`CreateEx`関数は、キーを返します。</span><span class="sxs-lookup"><span data-stu-id="eff69-125">In some situations, it is common practice to call `CreateEx()` without a set of explicit keys, but the `CreateEx` function returns the keys.</span></span> <span data-ttu-id="eff69-126">この動作は、実行されるサーバーで PeopleCode でサポートされます。</span><span class="sxs-lookup"><span data-stu-id="eff69-126">This behavior is supported with PeopleCode that gets triggered on the server.</span></span> <span data-ttu-id="eff69-127">たとえば、注文書を作成するクライアント可能性があります、次に利用できる PO 番号がわからない。</span><span class="sxs-lookup"><span data-stu-id="eff69-127">For example, to create a purchase order, the client may not know what the next available PO number is.</span></span> <span data-ttu-id="eff69-128">[次へ] を指定すると、PO 番号キーとして、呼び出し peoplecode、次に利用できる PO 番号を決定します。</span><span class="sxs-lookup"><span data-stu-id="eff69-128">By specifying NEXT as the PO number key, the call triggers PeopleCode, which determines the next available PO number.</span></span> <span data-ttu-id="eff69-129">この情報は、入力/出力のキー パラメーターを使用して、呼び出し元のクライアントに返す必要があります。</span><span class="sxs-lookup"><span data-stu-id="eff69-129">This information must be returned to the calling client, using the in/out key parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eff69-130">このメカニズムが機能するには、キーはレベル 0 のプロパティをあるも必要があります。</span><span class="sxs-lookup"><span data-stu-id="eff69-130">For this mechanism to work, the key must also be a property at level 0.</span></span> <span data-ttu-id="eff69-131">それ以外の場合、元のキーが返されます。</span><span class="sxs-lookup"><span data-stu-id="eff69-131">Otherwise, the original key is returned.</span></span>  
  
 <span data-ttu-id="eff69-132">BizTalk Adapter for PeopleSoft Enterprise`CreateEx()`コンポーネント インターフェイスで PeopleSoft の作成と保存の機能が有効になっている場合、メソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="eff69-132">The BizTalk Adapter for PeopleSoft Enterprise `CreateEx()` method is provided if the PeopleSoft Create and Save functions in the component interface are enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff69-133">参照</span><span class="sxs-lookup"><span data-stu-id="eff69-133">See Also</span></span>  
 [<span data-ttu-id="eff69-134">付録 a:コンポーネント インターフェイス メソッド</span><span class="sxs-lookup"><span data-stu-id="eff69-134">Appendix A: Component Interface Methods</span></span>](../core/appendix-a-component-interface-methods.md)