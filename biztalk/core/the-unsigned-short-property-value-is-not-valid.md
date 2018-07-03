---
title: 符号なし短整数プロパティの値が無効です |Microsoft Docs
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
ms.openlocfilehash: 198596c03d6ef7c5cd3b9005458f6eea18bd9b9a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011739"
---
# <a name="the-unsigned-short-property-value-is-not-valid"></a><span data-ttu-id="dd3ae-102">符号なし短整数プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="dd3ae-102">The unsigned Short property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="dd3ae-103">詳細</span><span class="sxs-lookup"><span data-stu-id="dd3ae-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="dd3ae-104">製品名</span><span class="sxs-lookup"><span data-stu-id="dd3ae-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="dd3ae-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="dd3ae-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="dd3ae-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="dd3ae-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="dd3ae-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="dd3ae-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="dd3ae-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="dd3ae-108"> EDI</span></span> |
|    <span data-ttu-id="dd3ae-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dd3ae-109">Component</span></span>    |                                       <span data-ttu-id="dd3ae-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="dd3ae-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="dd3ae-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="dd3ae-111">Symbolic Name</span></span>  |                                <span data-ttu-id="dd3ae-112">Err_InvalidUnsignedShort</span><span class="sxs-lookup"><span data-stu-id="dd3ae-112">Err_InvalidUnsignedShort</span></span>                                |
|  <span data-ttu-id="dd3ae-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="dd3ae-113">Message Text</span></span>   |                    <span data-ttu-id="dd3ae-114">符号なし短整数プロパティの値が無効です。</span><span class="sxs-lookup"><span data-stu-id="dd3ae-114">The unsigned Short property value is not valid.</span></span>                     |
  
## <a name="explanation"></a><span data-ttu-id="dd3ae-115">説明</span><span class="sxs-lookup"><span data-stu-id="dd3ae-115">Explanation</span></span>  
 <span data-ttu-id="dd3ae-116">このエラー/警告/情報イベントは、メッセージをバッチ処理するかどうかを判断する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="dd3ae-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dd3ae-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="dd3ae-117">User Action</span></span>  
 <span data-ttu-id="dd3ae-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、符号なし短整数を指定する XSD に無効な値を持つコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dd3ae-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of unsigned Short with an invalid value.</span></span>