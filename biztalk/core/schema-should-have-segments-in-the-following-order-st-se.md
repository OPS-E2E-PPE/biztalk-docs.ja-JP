---
title: スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4d1c6a-7d48-413a-9ef5-a0c49773dc16
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2563247dc6fc4c092fe2867c6b4d03239c4be7e1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269098"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a><span data-ttu-id="0b8ed-102">スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE</span><span class="sxs-lookup"><span data-stu-id="0b8ed-102">Schema should have segments in the following order ST .... SE</span></span>
## <a name="details"></a><span data-ttu-id="0b8ed-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0b8ed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0b8ed-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0b8ed-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="0b8ed-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0b8ed-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="0b8ed-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0b8ed-106">Event ID</span></span>|-|  
|<span data-ttu-id="0b8ed-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0b8ed-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0b8ed-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="0b8ed-108"> EDI</span></span>|  
|<span data-ttu-id="0b8ed-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0b8ed-109">Component</span></span>|<span data-ttu-id="0b8ed-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="0b8ed-110">EDI Engine</span></span>|  
|<span data-ttu-id="0b8ed-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0b8ed-111">Symbolic Name</span></span>|<span data-ttu-id="0b8ed-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="0b8ed-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span></span>|  
|<span data-ttu-id="0b8ed-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0b8ed-113">Message Text</span></span>|<span data-ttu-id="0b8ed-114">スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE</span><span class="sxs-lookup"><span data-stu-id="0b8ed-114">Schema should have segments in the following order ST .... SE</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0b8ed-115">説明</span><span class="sxs-lookup"><span data-stu-id="0b8ed-115">Explanation</span></span>  
 <span data-ttu-id="0b8ed-116">このエラー/警告/情報イベントは、ヘッダーとトレーラーが正しい順序で記述されていなかったため、カスタム ドキュメント スキーマが無効であることを示します。</span><span class="sxs-lookup"><span data-stu-id="0b8ed-116">This Error/Warning/Information event indicates that a custom document schema is invalid because the headers and trailers were not in the correct order.</span></span> <span data-ttu-id="0b8ed-117">スキーマが展開されると、BizTalk Server によってこの検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="0b8ed-117">BizTalk Server performs this validation when the schema is deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0b8ed-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0b8ed-118">User Action</span></span>  
 <span data-ttu-id="0b8ed-119">このエラーを解決するには、カスタマイズされたドキュメント スキーマを変更し、ヘッダーとトレーラーを正しい順序で記述して、スキーマを再展開します。</span><span class="sxs-lookup"><span data-stu-id="0b8ed-119">To resolve this error, change the customized document schema so that the headers and trailers are in the correct order, and then redeploy the schema.</span></span>