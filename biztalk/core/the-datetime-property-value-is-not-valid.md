---
title: Datetime プロパティ値が有効ではありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0dc527e-82d5-40dc-941e-f2e056163017
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f6f784bc04e243de3bbb3cfb1c1acc760c35015
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279138"
---
# <a name="the-datetime-property-value-is-not-valid"></a><span data-ttu-id="77b9d-102">日時プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="77b9d-102">The datetime property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="77b9d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="77b9d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="77b9d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="77b9d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="77b9d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="77b9d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="77b9d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77b9d-106">Event ID</span></span>|-|  
|<span data-ttu-id="77b9d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="77b9d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="77b9d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="77b9d-108"> EDI</span></span>|  
|<span data-ttu-id="77b9d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77b9d-109">Component</span></span>|<span data-ttu-id="77b9d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="77b9d-110">EDI Engine</span></span>|  
|<span data-ttu-id="77b9d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="77b9d-111">Symbolic Name</span></span>|<span data-ttu-id="77b9d-112">Err_InvalidDateTime</span><span class="sxs-lookup"><span data-stu-id="77b9d-112">Err_InvalidDateTime</span></span>|  
|<span data-ttu-id="77b9d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="77b9d-113">Message Text</span></span>|<span data-ttu-id="77b9d-114">日時プロパティの値が無効です。</span><span class="sxs-lookup"><span data-stu-id="77b9d-114">The datetime property value is not valid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="77b9d-115">説明</span><span class="sxs-lookup"><span data-stu-id="77b9d-115">Explanation</span></span>  
 <span data-ttu-id="77b9d-116">このエラー/警告/情報イベントは、メッセージをバッチ処理するかどうかを判断する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="77b9d-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77b9d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="77b9d-117">User Action</span></span>  
 <span data-ttu-id="77b9d-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、日付を指定する XSD に無効な値を持つコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="77b9d-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of date and the value is invalid date.</span></span>