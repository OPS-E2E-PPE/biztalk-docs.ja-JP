---
title: "無効なスキーム |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb3e70a-d23c-45e9-bde5-edae6731e58a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5736a3738a9598f4c4b419d7e291c3c3e32207f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-scheme"></a><span data-ttu-id="d5767-102">スキームが無効です</span><span class="sxs-lookup"><span data-stu-id="d5767-102">Invalid scheme</span></span>
## <a name="details"></a><span data-ttu-id="d5767-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d5767-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d5767-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d5767-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d5767-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d5767-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="d5767-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d5767-106">Event ID</span></span>|<span data-ttu-id="d5767-107">0</span><span class="sxs-lookup"><span data-stu-id="d5767-107">0</span></span>|  
|<span data-ttu-id="d5767-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d5767-108">Event Source</span></span>|<span data-ttu-id="d5767-109">0</span><span class="sxs-lookup"><span data-stu-id="d5767-109">0</span></span>|  
|<span data-ttu-id="d5767-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d5767-110">Component</span></span>|<span data-ttu-id="d5767-111">0</span><span class="sxs-lookup"><span data-stu-id="d5767-111">0</span></span>|  
|<span data-ttu-id="d5767-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d5767-112">Symbolic Name</span></span>|<span data-ttu-id="d5767-113">0</span><span class="sxs-lookup"><span data-stu-id="d5767-113">0</span></span>|  
|<span data-ttu-id="d5767-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d5767-114">Message Text</span></span>|<span data-ttu-id="d5767-115">無効なスキームです。スキーム"{0}"または「{1}」を指定してください。</span><span class="sxs-lookup"><span data-stu-id="d5767-115">Invalid scheme; expecting scheme "{0}" or "{1}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d5767-116">説明</span><span class="sxs-lookup"><span data-stu-id="d5767-116">Explanation</span></span>  
 <span data-ttu-id="d5767-117">次のいずれかが発生しました。 URI (uniform リソース識別子) フィールドに指定されているアドレスが http:// または https://で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5767-117">One of the following situations has occurred: the address that is specified in the URI (uniform resource identifier) field must start with either http:// or https://.</span></span> <span data-ttu-id="d5767-118">または、スキームが、トランスポート バインディング要素の実装で指定されているスキームと一致しません。</span><span class="sxs-lookup"><span data-stu-id="d5767-118">Or the scheme does not match what is specified in the implementation of the transport binding element.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d5767-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d5767-119">User Action</span></span>  
 <span data-ttu-id="d5767-120">http:// または https:// から始まる有効なプロキシ アドレスの URI を入力します</span><span class="sxs-lookup"><span data-stu-id="d5767-120">Enter a valid proxy address URI that starts with http:// or https://</span></span>