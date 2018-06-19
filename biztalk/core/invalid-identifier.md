---
title: 識別子が無効です |Microsoft ドキュメント
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
ms.openlocfilehash: 148b2c2d0b2ec4fb54e15fd8cb50b5dcf0af310a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257234"
---
# <a name="invalid-identifier"></a><span data-ttu-id="3f981-102">無効な識別子です</span><span class="sxs-lookup"><span data-stu-id="3f981-102">Invalid identifier</span></span>
## <a name="details"></a><span data-ttu-id="3f981-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3f981-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3f981-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3f981-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="3f981-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3f981-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="3f981-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3f981-106">Event ID</span></span>|<span data-ttu-id="3f981-107">0</span><span class="sxs-lookup"><span data-stu-id="3f981-107">0</span></span>|  
|<span data-ttu-id="3f981-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3f981-108">Event Source</span></span>|<span data-ttu-id="3f981-109">0</span><span class="sxs-lookup"><span data-stu-id="3f981-109">0</span></span>|  
|<span data-ttu-id="3f981-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3f981-110">Component</span></span>|<span data-ttu-id="3f981-111">0</span><span class="sxs-lookup"><span data-stu-id="3f981-111">0</span></span>|  
|<span data-ttu-id="3f981-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3f981-112">Symbolic Name</span></span>|<span data-ttu-id="3f981-113">0</span><span class="sxs-lookup"><span data-stu-id="3f981-113">0</span></span>|  
|<span data-ttu-id="3f981-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3f981-114">Message Text</span></span>|<span data-ttu-id="3f981-115">"{0}" は有効な識別子ではありません。</span><span class="sxs-lookup"><span data-stu-id="3f981-115">"{0}" is not a valid identifier.</span></span> <span data-ttu-id="3f981-116">元の名前を復元しています。</span><span class="sxs-lookup"><span data-stu-id="3f981-116">Restoring original name.</span></span> <span data-ttu-id="3f981-117">(有効な識別子では文字または数字の 0 個以上続く文字から成るし、スペースを含めることはできません)。</span><span class="sxs-lookup"><span data-stu-id="3f981-117">(A valid identifier consists of a letter followed by zero or more letters or digits and cannot contain spaces.)</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3f981-118">説明</span><span class="sxs-lookup"><span data-stu-id="3f981-118">Explanation</span></span>  
 <span data-ttu-id="3f981-119">このエラーは、スキーマの公開時に定義した Web メソッドが有効な .NET 識別子ではないことを示します。</span><span class="sxs-lookup"><span data-stu-id="3f981-119">This error indicates the web methods defined when publishing a schema is not a valid .net identifier.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3f981-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3f981-120">User Action</span></span>  
 <span data-ttu-id="3f981-121">Web メソッドの名前を有効な .NET 識別子に変更します。</span><span class="sxs-lookup"><span data-stu-id="3f981-121">Rename the web methods to a valid .net identifier.</span></span> <span data-ttu-id="3f981-122">有効な識別子の先頭は文字にする必要があり、全体は文字か数字のみで構成されている必要があります。スペースを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="3f981-122">A valid identifier consists of a letter followed by zero or more letters or digits and cannot contain spaces.</span></span>