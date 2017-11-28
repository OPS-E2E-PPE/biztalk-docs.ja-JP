---
title: "符号なし整数プロパティの値が無効です |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 63b0398f-7848-4971-8c08-95923d80cbe3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e5f6ac36eb2b7322a2252f4759539d721dc2e63
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-unsigned-integer-property-value-is-not-valid"></a><span data-ttu-id="438f5-102">符号なし整数プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="438f5-102">The unsigned integer property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="438f5-103">詳細</span><span class="sxs-lookup"><span data-stu-id="438f5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="438f5-104">製品名</span><span class="sxs-lookup"><span data-stu-id="438f5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="438f5-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="438f5-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="438f5-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="438f5-106">Event ID</span></span>|-|  
|<span data-ttu-id="438f5-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="438f5-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="438f5-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="438f5-108"> EDI</span></span>|  
|<span data-ttu-id="438f5-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="438f5-109">Component</span></span>|<span data-ttu-id="438f5-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="438f5-110">EDI Engine</span></span>|  
|<span data-ttu-id="438f5-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="438f5-111">Symbolic Name</span></span>|<span data-ttu-id="438f5-112">Err_InvalidUnsignedInteger</span><span class="sxs-lookup"><span data-stu-id="438f5-112">Err_InvalidUnsignedInteger</span></span>|  
|<span data-ttu-id="438f5-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="438f5-113">Message Text</span></span>|<span data-ttu-id="438f5-114">符号なし整数プロパティの値が無効です。</span><span class="sxs-lookup"><span data-stu-id="438f5-114">The unsigned integer property value is not valid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="438f5-115">説明</span><span class="sxs-lookup"><span data-stu-id="438f5-115">Explanation</span></span>  
 <span data-ttu-id="438f5-116">このエラー/警告/情報イベントは、メッセージをバッチ処理するかどうかを判断する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="438f5-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="438f5-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="438f5-117">User Action</span></span>  
 <span data-ttu-id="438f5-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、符号なし整数を指定する XSD に無効な値を持つコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="438f5-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of unsigned integer with an invalid value.</span></span>