---
title: "この XSD 型に対して BitwiseAnd 比較を行うことはできません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 82bc2351-c002-458a-9d35-5fdcc91c6a0e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c0f3aa2b3ae7c60f3c104daaa885ab7ae8cc7ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a-bitwiseand-comparison-cannot-be-done-for-this-xsd-type"></a><span data-ttu-id="6b077-102">この種の XSD に対して BitwiseAnd 比較を行うことはできません</span><span class="sxs-lookup"><span data-stu-id="6b077-102">A BitwiseAnd comparison cannot be done for this XSD type</span></span>
## <a name="details"></a><span data-ttu-id="6b077-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6b077-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6b077-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6b077-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="6b077-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6b077-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="6b077-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6b077-106">Event ID</span></span>|-|  
|<span data-ttu-id="6b077-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6b077-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="6b077-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="6b077-108"> EDI</span></span>|  
|<span data-ttu-id="6b077-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6b077-109">Component</span></span>|<span data-ttu-id="6b077-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6b077-110">EDI Engine</span></span>|  
|<span data-ttu-id="6b077-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6b077-111">Symbolic Name</span></span>|<span data-ttu-id="6b077-112">Err_InvalidBitwiseComparision</span><span class="sxs-lookup"><span data-stu-id="6b077-112">Err_InvalidBitwiseComparision</span></span>|  
|<span data-ttu-id="6b077-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6b077-113">Message Text</span></span>|<span data-ttu-id="6b077-114">この XSD 型に対して BitwiseAnd 比較を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="6b077-114">A BitwiseAnd comparison cannot be done for this XSD type.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6b077-115">説明</span><span class="sxs-lookup"><span data-stu-id="6b077-115">Explanation</span></span>  
 <span data-ttu-id="6b077-116">このエラー/警告/情報イベントは、メッセージをバッチ処理する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="6b077-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6b077-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6b077-117">User Action</span></span>  
 <span data-ttu-id="6b077-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、ビットごとの比較ができない CSD 型を持っているコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="6b077-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an CSD type that can’t be bitwise compared.</span></span>