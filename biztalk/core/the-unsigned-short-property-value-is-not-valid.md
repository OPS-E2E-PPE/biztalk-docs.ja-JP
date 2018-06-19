---
title: 符号なし短整数プロパティの値が有効ではありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31600ed6-20bc-4382-9eb3-4d6fa9646411
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a62a37bc136f317e05db0e66cf3c2c86af97df41
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279794"
---
# <a name="the-unsigned-short-property-value-is-not-valid"></a><span data-ttu-id="3ac4d-102">符号なし短整数プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="3ac4d-102">The unsigned Short property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="3ac4d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3ac4d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3ac4d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3ac4d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3ac4d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3ac4d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="3ac4d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3ac4d-106">Event ID</span></span>|-|  
|<span data-ttu-id="3ac4d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3ac4d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3ac4d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="3ac4d-108"> EDI</span></span>|  
|<span data-ttu-id="3ac4d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3ac4d-109">Component</span></span>|<span data-ttu-id="3ac4d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="3ac4d-110">EDI Engine</span></span>|  
|<span data-ttu-id="3ac4d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3ac4d-111">Symbolic Name</span></span>|<span data-ttu-id="3ac4d-112">Err_InvalidUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="3ac4d-112">Err_InvalidUnsignedShort</span></span>|  
|<span data-ttu-id="3ac4d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3ac4d-113">Message Text</span></span>|<span data-ttu-id="3ac4d-114">符号なし短整数プロパティの値が無効です。</span><span class="sxs-lookup"><span data-stu-id="3ac4d-114">The unsigned Short property value is not valid.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3ac4d-115">説明</span><span class="sxs-lookup"><span data-stu-id="3ac4d-115">Explanation</span></span>  
 <span data-ttu-id="3ac4d-116">このエラー/警告/情報イベントは、メッセージをバッチ処理するかどうかを判断する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="3ac4d-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3ac4d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3ac4d-117">User Action</span></span>  
 <span data-ttu-id="3ac4d-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、符号なし短整数を指定する XSD に無効な値を持つコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="3ac4d-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of unsigned Short with an invalid value.</span></span>