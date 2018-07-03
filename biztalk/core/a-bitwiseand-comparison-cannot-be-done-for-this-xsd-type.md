---
title: この XSD 型に対して BitwiseAnd 比較を行うことはできません |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82bc2351-c002-458a-9d35-5fdcc91c6a0e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d057efc9f0fd9e1cd5625f191f811c53b2e1ad4f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019503"
---
# <a name="a-bitwiseand-comparison-cannot-be-done-for-this-xsd-type"></a><span data-ttu-id="4c311-102">この種の XSD に対して BitwiseAnd 比較を行うことはできません</span><span class="sxs-lookup"><span data-stu-id="4c311-102">A BitwiseAnd comparison cannot be done for this XSD type</span></span>
## <a name="details"></a><span data-ttu-id="4c311-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4c311-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="4c311-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4c311-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="4c311-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4c311-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="4c311-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4c311-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="4c311-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4c311-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4c311-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="4c311-108"> EDI</span></span> |
|    <span data-ttu-id="4c311-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4c311-109">Component</span></span>    |                                       <span data-ttu-id="4c311-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="4c311-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="4c311-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4c311-111">Symbolic Name</span></span>  |                             <span data-ttu-id="4c311-112">Err_InvalidBitwiseComparision</span><span class="sxs-lookup"><span data-stu-id="4c311-112">Err_InvalidBitwiseComparision</span></span>                              |
|  <span data-ttu-id="4c311-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4c311-113">Message Text</span></span>   |               <span data-ttu-id="4c311-114">この XSD 型に対して BitwiseAnd 比較を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="4c311-114">A BitwiseAnd comparison cannot be done for this XSD type.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="4c311-115">説明</span><span class="sxs-lookup"><span data-stu-id="4c311-115">Explanation</span></span>  
 <span data-ttu-id="4c311-116">このエラー/警告/情報イベントは、メッセージをバッチ処理する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="4c311-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4c311-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4c311-117">User Action</span></span>  
 <span data-ttu-id="4c311-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、ビットごとの比較ができない CSD 型を持っているコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4c311-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an CSD type that can’t be bitwise compared.</span></span>