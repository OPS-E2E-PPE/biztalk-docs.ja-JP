---
title: 日時プロパティの値が無効です |Microsoft Docs
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
ms.openlocfilehash: 44cd97dc2cb185082ee2717d11ac7a09b9a0b66c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975411"
---
# <a name="the-datetime-property-value-is-not-valid"></a><span data-ttu-id="68875-102">日時プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="68875-102">The datetime property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="68875-103">詳細</span><span class="sxs-lookup"><span data-stu-id="68875-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="68875-104">製品名</span><span class="sxs-lookup"><span data-stu-id="68875-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="68875-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="68875-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="68875-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="68875-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="68875-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="68875-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="68875-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="68875-108"> EDI</span></span> |
|    <span data-ttu-id="68875-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="68875-109">Component</span></span>    |                                       <span data-ttu-id="68875-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="68875-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="68875-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="68875-111">Symbolic Name</span></span>  |                                  <span data-ttu-id="68875-112">Err_InvalidDateTime</span><span class="sxs-lookup"><span data-stu-id="68875-112">Err_InvalidDateTime</span></span>                                   |
|  <span data-ttu-id="68875-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="68875-113">Message Text</span></span>   |                       <span data-ttu-id="68875-114">日時プロパティの値が無効です。</span><span class="sxs-lookup"><span data-stu-id="68875-114">The datetime property value is not valid.</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="68875-115">説明</span><span class="sxs-lookup"><span data-stu-id="68875-115">Explanation</span></span>  
 <span data-ttu-id="68875-116">このエラー/警告/情報イベントは、メッセージをバッチ処理するかどうかを判断する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="68875-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="68875-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="68875-117">User Action</span></span>  
 <span data-ttu-id="68875-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、日付を指定する XSD に無効な値を持つコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="68875-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of date and the value is invalid date.</span></span>