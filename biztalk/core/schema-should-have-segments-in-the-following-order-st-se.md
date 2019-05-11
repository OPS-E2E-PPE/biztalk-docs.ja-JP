---
title: スキーマは、ST の次の順序でセグメントをある必要があります.SE |Microsoft Docs
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
ms.openlocfilehash: b975f28221941ef84f0683fae1597816640d48a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396902"
---
# <a name="schema-should-have-segments-in-the-following-order-st--se"></a><span data-ttu-id="ce3c5-102">スキーマは、ST の次の順序でセグメントをある必要があります.SE</span><span class="sxs-lookup"><span data-stu-id="ce3c5-102">Schema should have segments in the following order ST .... SE</span></span>
## <a name="details"></a><span data-ttu-id="ce3c5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="ce3c5-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ce3c5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="ce3c5-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ce3c5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="ce3c5-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ce3c5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="ce3c5-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ce3c5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="ce3c5-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ce3c5-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ce3c5-108">EDI</span></span> |
|    <span data-ttu-id="ce3c5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="ce3c5-109">Component</span></span>    |                                       <span data-ttu-id="ce3c5-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="ce3c5-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="ce3c5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="ce3c5-111">Symbolic Name</span></span>  |                    <span data-ttu-id="ce3c5-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span><span class="sxs-lookup"><span data-stu-id="ce3c5-112">SchemaCode116ETransactionSetSchemaStSeOutOfOrder</span></span>                    |
|  <span data-ttu-id="ce3c5-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="ce3c5-113">Message Text</span></span>   |             <span data-ttu-id="ce3c5-114">スキーマは、ST の次の順序でセグメントをある必要があります.SE</span><span class="sxs-lookup"><span data-stu-id="ce3c5-114">Schema should have segments in the following order ST .... SE</span></span>              |
  
## <a name="explanation"></a><span data-ttu-id="ce3c5-115">説明</span><span class="sxs-lookup"><span data-stu-id="ce3c5-115">Explanation</span></span>  
 <span data-ttu-id="ce3c5-116">このエラー/警告/情報イベントは、カスタム ドキュメント スキーマが無効である、正しい順序でヘッダーとトレーラーがないためにことを示します。</span><span class="sxs-lookup"><span data-stu-id="ce3c5-116">This Error/Warning/Information event indicates that a custom document schema is invalid because the headers and trailers were not in the correct order.</span></span> <span data-ttu-id="ce3c5-117">BizTalk Server は、スキーマが展開されているときに、この検証を実行します。</span><span class="sxs-lookup"><span data-stu-id="ce3c5-117">BizTalk Server performs this validation when the schema is deployed.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce3c5-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="ce3c5-118">User Action</span></span>  
 <span data-ttu-id="ce3c5-119">このエラーを解決するには、ヘッダーとトレーラーが正しい順番とし、スキーマを再配置できるように、カスタマイズされたドキュメント スキーマを変更します。</span><span class="sxs-lookup"><span data-stu-id="ce3c5-119">To resolve this error, change the customized document schema so that the headers and trailers are in the correct order, and then redeploy the schema.</span></span>