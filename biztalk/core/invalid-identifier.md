---
title: 識別子が無効です |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f87e1e42-457f-4d04-a1d2-6b796f3fa7b7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e277a1b2a02ee622f37007a2d2a001570bded79
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381345"
---
# <a name="invalid-identifier"></a><span data-ttu-id="39585-102">無効な識別子です</span><span class="sxs-lookup"><span data-stu-id="39585-102">Invalid identifier</span></span>
## <a name="details"></a><span data-ttu-id="39585-103">詳細</span><span class="sxs-lookup"><span data-stu-id="39585-103">Details</span></span>  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="39585-104">製品名</span><span class="sxs-lookup"><span data-stu-id="39585-104">Product Name</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| <span data-ttu-id="39585-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="39585-105">Product Version</span></span> |                                                        [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                         |
|    <span data-ttu-id="39585-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="39585-106">Event ID</span></span>     |                                                                                     <span data-ttu-id="39585-107">0</span><span class="sxs-lookup"><span data-stu-id="39585-107">0</span></span>                                                                                     |
|  <span data-ttu-id="39585-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="39585-108">Event Source</span></span>   |                                                                                     <span data-ttu-id="39585-109">0</span><span class="sxs-lookup"><span data-stu-id="39585-109">0</span></span>                                                                                     |
|    <span data-ttu-id="39585-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="39585-110">Component</span></span>    |                                                                                     <span data-ttu-id="39585-111">0</span><span class="sxs-lookup"><span data-stu-id="39585-111">0</span></span>                                                                                     |
|  <span data-ttu-id="39585-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="39585-112">Symbolic Name</span></span>  |                                                                                     <span data-ttu-id="39585-113">0</span><span class="sxs-lookup"><span data-stu-id="39585-113">0</span></span>                                                                                     |
|  <span data-ttu-id="39585-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="39585-114">Message Text</span></span>   | <span data-ttu-id="39585-115">"{0}"は有効な識別子ではありません。</span><span class="sxs-lookup"><span data-stu-id="39585-115">"{0}" is not a valid identifier.</span></span> <span data-ttu-id="39585-116">元の名前を復元します。</span><span class="sxs-lookup"><span data-stu-id="39585-116">Restoring original name.</span></span> <span data-ttu-id="39585-117">(有効な識別子は文字または数字の 0 個以上続く文字から成るし、スペースを含めることはできません)。</span><span class="sxs-lookup"><span data-stu-id="39585-117">(A valid identifier consists of a letter followed by zero or more letters or digits and cannot contain spaces.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="39585-118">説明</span><span class="sxs-lookup"><span data-stu-id="39585-118">Explanation</span></span>  
 <span data-ttu-id="39585-119">このエラーは、スキーマの公開が有効な .net 識別子ではない場合に定義されている web メソッドを示します。</span><span class="sxs-lookup"><span data-stu-id="39585-119">This error indicates the web methods defined when publishing a schema is not a valid .net identifier.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="39585-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="39585-120">User Action</span></span>  
 <span data-ttu-id="39585-121">有効な .net 識別子には、web メソッドを変更します。</span><span class="sxs-lookup"><span data-stu-id="39585-121">Rename the web methods to a valid .net identifier.</span></span> <span data-ttu-id="39585-122">有効な識別子では、文字または数字の 0 個以上続く文字で構成され、スペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="39585-122">A valid identifier consists of a letter followed by zero or more letters or digits and cannot contain spaces.</span></span>