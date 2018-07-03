---
title: スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE |Microsoft Docs
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
ms.openlocfilehash: c98bc756e4bd75a8a15111c54f433a7f9c6c0509
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015171"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a><span data-ttu-id="bb909-102">スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE</span><span class="sxs-lookup"><span data-stu-id="bb909-102">Schema should have segments in the following order ST .... SE</span></span>
## <a name="details"></a><span data-ttu-id="bb909-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bb909-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="bb909-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bb909-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="bb909-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bb909-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="bb909-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bb909-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="bb909-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bb909-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="bb909-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="bb909-108"> EDI</span></span> |
|    <span data-ttu-id="bb909-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bb909-109">Component</span></span>    |                                       <span data-ttu-id="bb909-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="bb909-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="bb909-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bb909-111">Symbolic Name</span></span>  |                    <span data-ttu-id="bb909-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="bb909-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span></span>                    |
|  <span data-ttu-id="bb909-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bb909-113">Message Text</span></span>   |             <span data-ttu-id="bb909-114">スキーマには ST .... SE の順序でセグメントが記述されている必要がありますSE</span><span class="sxs-lookup"><span data-stu-id="bb909-114">Schema should have segments in the following order ST .... SE</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="bb909-115">説明</span><span class="sxs-lookup"><span data-stu-id="bb909-115">Explanation</span></span>  
 <span data-ttu-id="bb909-116">このエラー/警告/情報イベントは、ヘッダーとトレーラーが正しい順序で記述されていなかったため、カスタム ドキュメント スキーマが無効であることを示します。</span><span class="sxs-lookup"><span data-stu-id="bb909-116">This Error/Warning/Information event indicates that a custom document schema is invalid because the headers and trailers were not in the correct order.</span></span> <span data-ttu-id="bb909-117">スキーマが展開されると、BizTalk Server によってこの検証が実行されます。</span><span class="sxs-lookup"><span data-stu-id="bb909-117">BizTalk Server performs this validation when the schema is deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bb909-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bb909-118">User Action</span></span>  
 <span data-ttu-id="bb909-119">このエラーを解決するには、カスタマイズされたドキュメント スキーマを変更し、ヘッダーとトレーラーを正しい順序で記述して、スキーマを再展開します。</span><span class="sxs-lookup"><span data-stu-id="bb909-119">To resolve this error, change the customized document schema so that the headers and trailers are in the correct order, and then redeploy the schema.</span></span>