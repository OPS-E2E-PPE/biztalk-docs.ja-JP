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
ms.openlocfilehash: 41b349991d0e0d6949754c804fcd1ebf16ea7ad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012355"
---
# <a name="invalid-identifier"></a><span data-ttu-id="11f0d-102">無効な識別子です</span><span class="sxs-lookup"><span data-stu-id="11f0d-102">Invalid identifier</span></span>
## <a name="details"></a><span data-ttu-id="11f0d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="11f0d-103">Details</span></span>  
  
|                 |                                                                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="11f0d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="11f0d-104">Product Name</span></span>   |                                            [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                             |
| <span data-ttu-id="11f0d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="11f0d-105">Product Version</span></span> |                                                        [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                         |
|    <span data-ttu-id="11f0d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="11f0d-106">Event ID</span></span>     |                                                                                     <span data-ttu-id="11f0d-107">0</span><span class="sxs-lookup"><span data-stu-id="11f0d-107">0</span></span>                                                                                     |
|  <span data-ttu-id="11f0d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="11f0d-108">Event Source</span></span>   |                                                                                     <span data-ttu-id="11f0d-109">0</span><span class="sxs-lookup"><span data-stu-id="11f0d-109">0</span></span>                                                                                     |
|    <span data-ttu-id="11f0d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="11f0d-110">Component</span></span>    |                                                                                     <span data-ttu-id="11f0d-111">0</span><span class="sxs-lookup"><span data-stu-id="11f0d-111">0</span></span>                                                                                     |
|  <span data-ttu-id="11f0d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="11f0d-112">Symbolic Name</span></span>  |                                                                                     <span data-ttu-id="11f0d-113">0</span><span class="sxs-lookup"><span data-stu-id="11f0d-113">0</span></span>                                                                                     |
|  <span data-ttu-id="11f0d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="11f0d-114">Message Text</span></span>   | <span data-ttu-id="11f0d-115">"{0}"は有効な識別子ではありません。</span><span class="sxs-lookup"><span data-stu-id="11f0d-115">"{0}" is not a valid identifier.</span></span> <span data-ttu-id="11f0d-116">元の名前を復元しています。</span><span class="sxs-lookup"><span data-stu-id="11f0d-116">Restoring original name.</span></span> <span data-ttu-id="11f0d-117">(有効な識別子は文字または数字の 0 個以上続く文字から成るし、スペースを含めることはできません)。</span><span class="sxs-lookup"><span data-stu-id="11f0d-117">(A valid identifier consists of a letter followed by zero or more letters or digits and cannot contain spaces.)</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="11f0d-118">説明</span><span class="sxs-lookup"><span data-stu-id="11f0d-118">Explanation</span></span>  
 <span data-ttu-id="11f0d-119">このエラーは、スキーマの公開時に定義した Web メソッドが有効な .NET 識別子ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="11f0d-119">This error indicates the web methods defined when publishing a schema is not a valid .net identifier.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="11f0d-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="11f0d-120">User Action</span></span>  
 <span data-ttu-id="11f0d-121">Web メソッドの名前を有効な .NET 識別子に変更します。</span><span class="sxs-lookup"><span data-stu-id="11f0d-121">Rename the web methods to a valid .net identifier.</span></span> <span data-ttu-id="11f0d-122">有効な識別子の先頭は文字にする必要があり、全体は文字か数字のみで構成されている必要があります。スペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="11f0d-122">A valid identifier consists of a letter followed by zero or more letters or digits and cannot contain spaces.</span></span>