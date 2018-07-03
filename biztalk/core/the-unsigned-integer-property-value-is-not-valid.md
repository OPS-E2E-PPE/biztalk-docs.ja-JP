---
title: 符号なし整数プロパティの値が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63b0398f-7848-4971-8c08-95923d80cbe3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6af46fc5719e8ccbe52dbfb419e104915d051e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973939"
---
# <a name="the-unsigned-integer-property-value-is-not-valid"></a><span data-ttu-id="10ed9-102">符号なし整数プロパティの値が無効です</span><span class="sxs-lookup"><span data-stu-id="10ed9-102">The unsigned integer property value is not valid</span></span>
## <a name="details"></a><span data-ttu-id="10ed9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="10ed9-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="10ed9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="10ed9-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="10ed9-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="10ed9-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="10ed9-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="10ed9-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="10ed9-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="10ed9-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="10ed9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="10ed9-108"> EDI</span></span> |
|    <span data-ttu-id="10ed9-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="10ed9-109">Component</span></span>    |                                       <span data-ttu-id="10ed9-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="10ed9-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="10ed9-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="10ed9-111">Symbolic Name</span></span>  |                               <span data-ttu-id="10ed9-112">Err_InvalidUnsignedInteger</span><span class="sxs-lookup"><span data-stu-id="10ed9-112">Err_InvalidUnsignedInteger</span></span>                               |
|  <span data-ttu-id="10ed9-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="10ed9-113">Message Text</span></span>   |                   <span data-ttu-id="10ed9-114">符号なし整数プロパティの値が無効です。</span><span class="sxs-lookup"><span data-stu-id="10ed9-114">The unsigned integer property value is not valid.</span></span>                    |
  
## <a name="explanation"></a><span data-ttu-id="10ed9-115">説明</span><span class="sxs-lookup"><span data-stu-id="10ed9-115">Explanation</span></span>  
 <span data-ttu-id="10ed9-116">このエラー/警告/情報イベントは、メッセージをバッチ処理するかどうかを判断する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="10ed9-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide whether to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="10ed9-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="10ed9-117">User Action</span></span>  
 <span data-ttu-id="10ed9-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、符号なし整数を指定する XSD に無効な値を持つコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="10ed9-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an XSD type of unsigned integer with an invalid value.</span></span>