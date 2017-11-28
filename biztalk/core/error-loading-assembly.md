---
title: "アセンブリを読み込み中にエラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 600973e0-3142-455f-9afa-74430af31e38
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13be3acf6974565c86cc87b14ed58929553d5220
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-loading-assembly"></a><span data-ttu-id="67bbe-102">アセンブリを読み込み中にエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="67bbe-102">Error loading assembly</span></span>
## <a name="details"></a><span data-ttu-id="67bbe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="67bbe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="67bbe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="67bbe-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="67bbe-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="67bbe-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="67bbe-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="67bbe-106">Event ID</span></span>|<span data-ttu-id="67bbe-107">0</span><span class="sxs-lookup"><span data-stu-id="67bbe-107">0</span></span>|  
|<span data-ttu-id="67bbe-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="67bbe-108">Event Source</span></span>|<span data-ttu-id="67bbe-109">0</span><span class="sxs-lookup"><span data-stu-id="67bbe-109">0</span></span>|  
|<span data-ttu-id="67bbe-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="67bbe-110">Component</span></span>|<span data-ttu-id="67bbe-111">0</span><span class="sxs-lookup"><span data-stu-id="67bbe-111">0</span></span>|  
|<span data-ttu-id="67bbe-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="67bbe-112">Symbolic Name</span></span>|<span data-ttu-id="67bbe-113">0</span><span class="sxs-lookup"><span data-stu-id="67bbe-113">0</span></span>|  
|<span data-ttu-id="67bbe-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="67bbe-114">Message Text</span></span>|<span data-ttu-id="67bbe-115">このエラーは、読み込み先がネットワーク共有にある場合、完全に信頼されていない可能性があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="67bbe-115">This error indicates the location may not be fully trusted if it is on a network share.</span></span> <span data-ttu-id="67bbe-116">ゾーンのコード アクセス セキュリティ ポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="67bbe-116">Check the Code Access Security policy for the Zone.</span></span> <span data-ttu-id="67bbe-117">または、読み込んだファイルが BizTalk .NET アセンブリではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67bbe-117">Or the file may not be a BizTalk .NET assembly.</span></span> <span data-ttu-id="67bbe-118">アセンブリを確認して、[アセンブリ: BizTalkAssembly] カスタム属性です。</span><span class="sxs-lookup"><span data-stu-id="67bbe-118">Check the assembly for the [assembly: BizTalkAssembly] custom attribute.</span></span> <span data-ttu-id="67bbe-119">または、読み込んだファイルが .NET アセンブリではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67bbe-119">Or the file may not be a .NET assembly.</span></span> <span data-ttu-id="67bbe-120">ファイルが .dll または .exe の場合、これはアンマネージ コードです。</span><span class="sxs-lookup"><span data-stu-id="67bbe-120">If the file is a .dll or  exe, it may be unmanaged code</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="67bbe-121">説明</span><span class="sxs-lookup"><span data-stu-id="67bbe-121">Explanation</span></span>  
 <span data-ttu-id="67bbe-122">このエラーは、読み込み先がネットワーク共有にある場合、完全に信頼されていない可能性があることを示しています。</span><span class="sxs-lookup"><span data-stu-id="67bbe-122">This error indicates the location may not be fully trusted if it is on a network share.</span></span> <span data-ttu-id="67bbe-123">ゾーンのコード アクセス セキュリティ ポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="67bbe-123">Check the Code Access Security policy for the Zone.</span></span> <span data-ttu-id="67bbe-124">または、読み込んだファイルが BizTalk .NET アセンブリではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67bbe-124">Or the file may not be a BizTalk .NET assembly.</span></span> <span data-ttu-id="67bbe-125">アセンブリを確認して、[*アセンブリ: BizTalkAssembly*] カスタム属性です。</span><span class="sxs-lookup"><span data-stu-id="67bbe-125">Check the assembly for the [*assembly: BizTalkAssembly*] custom attribute.</span></span> <span data-ttu-id="67bbe-126">または、読み込んだファイルが .NET アセンブリではない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67bbe-126">Or the file may not be a .NET assembly.</span></span> <span data-ttu-id="67bbe-127">ファイルが .dll または .exe の場合は、アンマネージ コードがある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67bbe-127">If the file is a .dll or  exe, it may be unmanaged code.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="67bbe-128">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="67bbe-128">User Action</span></span>  
 <span data-ttu-id="67bbe-129">信頼できる送信元の場合、その送信元に完全信頼を付与します。</span><span class="sxs-lookup"><span data-stu-id="67bbe-129">Grant Full trust level to the location if it’s from a reliable source.</span></span>  <span data-ttu-id="67bbe-130">dll が有効な BizTalk .NET アセンブリであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="67bbe-130">Ensure the dll is a valid BizTalk .net assembly.</span></span>