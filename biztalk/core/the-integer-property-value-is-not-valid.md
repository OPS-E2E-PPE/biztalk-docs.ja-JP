---
title: "整数プロパティの値が無効です |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 31d4e9a7-4336-40f1-997a-9f79d86b26d2
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acbb350d9dd8fe77e42bb7e8b3cdf4617c87a2f7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-integer-property-value-is-not-valid"></a><span data-ttu-id="4b40a-102">整数プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="4b40a-102">The integer property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="4b40a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4b40a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="4b40a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4b40a-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="4b40a-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4b40a-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="4b40a-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4b40a-106">Event ID</span></span>|-|  
|<span data-ttu-id="4b40a-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4b40a-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4b40a-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4b40a-108"> EDI</span></span>|  
|<span data-ttu-id="4b40a-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4b40a-109">Component</span></span>|<span data-ttu-id="4b40a-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="4b40a-110">EDI Engine</span></span>|  
|<span data-ttu-id="4b40a-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4b40a-111">Symbolic Name</span></span>|<span data-ttu-id="4b40a-112">Err_InvalidInteger</span><span class="sxs-lookup"><span data-stu-id="4b40a-112">Err_InvalidInteger</span></span>|  
|<span data-ttu-id="4b40a-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4b40a-113">Message Text</span></span>|<span data-ttu-id="4b40a-114">整数プロパティの値が無効です。</span><span class="sxs-lookup"><span data-stu-id="4b40a-114">The integer property value is not valid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="4b40a-115">説明</span><span class="sxs-lookup"><span data-stu-id="4b40a-115">Explanation</span></span>  
 <span data-ttu-id="4b40a-116">このエラー/警告/情報イベントは、メッセージをバッチ処理するかどうかを判断する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="4b40a-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4b40a-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4b40a-117">User Action</span></span>  
 <span data-ttu-id="4b40a-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、整数を指定する XSD に無効な値を持つコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4b40a-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of integer with an invalid value.</span></span>