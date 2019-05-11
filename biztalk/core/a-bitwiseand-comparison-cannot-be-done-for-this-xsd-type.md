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
ms.openlocfilehash: 069cb188ce6f6035b64298aaa90d6362d9500702
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362588"
---
# <a name="a-bitwiseand-comparison-cannot-be-done-for-this-xsd-type"></a><span data-ttu-id="dc76c-102">この XSD 型に対して BitwiseAnd 比較を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="dc76c-102">A BitwiseAnd comparison cannot be done for this XSD type</span></span>
## <a name="details"></a><span data-ttu-id="dc76c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="dc76c-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="dc76c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="dc76c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="dc76c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="dc76c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="dc76c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="dc76c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="dc76c-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="dc76c-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="dc76c-108">EDI</span><span class="sxs-lookup"><span data-stu-id="dc76c-108">EDI</span></span> |
|    <span data-ttu-id="dc76c-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="dc76c-109">Component</span></span>    |                                       <span data-ttu-id="dc76c-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="dc76c-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="dc76c-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="dc76c-111">Symbolic Name</span></span>  |                             <span data-ttu-id="dc76c-112">Err_InvalidBitwiseComparision</span><span class="sxs-lookup"><span data-stu-id="dc76c-112">Err_InvalidBitwiseComparision</span></span>                              |
|  <span data-ttu-id="dc76c-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="dc76c-113">Message Text</span></span>   |               <span data-ttu-id="dc76c-114">この XSD 型に対して BitwiseAnd 比較を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="dc76c-114">A BitwiseAnd comparison cannot be done for this XSD type.</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="dc76c-115">説明</span><span class="sxs-lookup"><span data-stu-id="dc76c-115">Explanation</span></span>  
 <span data-ttu-id="dc76c-116">このエラー/警告/情報イベントは、メッセージをバッチ処理する際に、BizTalk Server がコンテキスト プロパティを比較できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="dc76c-116">This Error/Warning/Information event indicates BizTalk Server was unable to compare a context property while trying to decide to Batch a message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc76c-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="dc76c-117">User Action</span></span>  
 <span data-ttu-id="dc76c-118">このエラーを解決するには、アクティブなバッチに含まれているフィルターで、ビットごとの比較ができない CSD 型を持っているコンテキスト プロパティが指定されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="dc76c-118">To resolve this error, ensure that the filter provided in Active batches doesn’t specify a context property which has an CSD type that can’t be bitwise compared.</span></span>