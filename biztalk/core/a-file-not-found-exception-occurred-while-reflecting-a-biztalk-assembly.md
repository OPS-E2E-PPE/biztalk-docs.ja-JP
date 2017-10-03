---
title: "ファイルが見つからない BizTalk アセンブリの反映中に例外が発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f13e4539fca9a14e7827afcb092af76e03f8acc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="f77a8-102">BizTalk アセンブリの反映中に、ファイルが見つからないことを示す例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="f77a8-102">A file not found exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="f77a8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f77a8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f77a8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f77a8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f77a8-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f77a8-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="f77a8-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f77a8-106">Event ID</span></span>|<span data-ttu-id="f77a8-107">0</span><span class="sxs-lookup"><span data-stu-id="f77a8-107">0</span></span>|  
|<span data-ttu-id="f77a8-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f77a8-108">Event Source</span></span>|<span data-ttu-id="f77a8-109">0</span><span class="sxs-lookup"><span data-stu-id="f77a8-109">0</span></span>|  
|<span data-ttu-id="f77a8-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f77a8-110">Component</span></span>|<span data-ttu-id="f77a8-111">0</span><span class="sxs-lookup"><span data-stu-id="f77a8-111">0</span></span>|  
|<span data-ttu-id="f77a8-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f77a8-112">Symbolic Name</span></span>|<span data-ttu-id="f77a8-113">0</span><span class="sxs-lookup"><span data-stu-id="f77a8-113">0</span></span>|  
|<span data-ttu-id="f77a8-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f77a8-114">Message Text</span></span>|<span data-ttu-id="f77a8-115">BizTalk アセンブリ "{0}" の反映中に、ファイルが見つからないことを示す例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="f77a8-115">A file not found exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="f77a8-116">この問題は、1 つまたは複数の依存関係が使用できない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="f77a8-116">This problem may occur if one or more dependencies are not available.</span></span> <span data-ttu-id="f77a8-117">この問題を解決するには次のいずれかの操作を試してください: 1。</span><span class="sxs-lookup"><span data-stu-id="f77a8-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="f77a8-118">アセンブリの依存関係を同じフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="f77a8-118">Copy the dependencies of the assembly to the same folder.</span></span> <span data-ttu-id="f77a8-119">2.</span><span class="sxs-lookup"><span data-stu-id="f77a8-119">2.</span></span> <span data-ttu-id="f77a8-120">足りない依存関係をグローバル アセンブリ キャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="f77a8-120">Install the missing dependencies into the Global Assembly Cache.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f77a8-121">説明</span><span class="sxs-lookup"><span data-stu-id="f77a8-121">Explanation</span></span>  
 <span data-ttu-id="f77a8-122">このエラーは、公開されている BizTalk アセンブリが、グローバル アセンブリ キャッシュ (GAC) または同じディレクトリにないアセンブリを参照していることを示します。</span><span class="sxs-lookup"><span data-stu-id="f77a8-122">This error indicates the BizTalk Assembly that is being published references another assembly that is not in the Global Assembly Cache (GAC) or in the same directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f77a8-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f77a8-123">User Action</span></span>  
 <span data-ttu-id="f77a8-124">エラー メッセージに指定された操作に加え、参照アセンブリをグローバル アセンブリ キャッシュに移動するか、BizTalk アセンブリと同じ場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="f77a8-124">In addition to the actions specified in the error message, move the reference assembly to the Global Assembly Cache or copy it to the same location as the BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="f77a8-125">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント **[!INCLUDE[vs2010](../includes/vs2010-md.md)]** 、順にクリック **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**です。</span><span class="sxs-lookup"><span data-stu-id="f77a8-125">Click **Start**, point to **All Programs**, point to **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**, and then click **[!INCLUDE[vs2010](../includes/vs2010-md.md)]**.</span></span>  
  
2.  <span data-ttu-id="f77a8-126">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="f77a8-126">Open a command prompt.</span></span>  
  
3.  <span data-ttu-id="f77a8-127">アセンブリの場所を参照し、入力**gacutil/I/\<***アセンブリ名***> .dll**</span><span class="sxs-lookup"><span data-stu-id="f77a8-127">Browse to the location of the assembly, and enter **gacutil /I /\<***assembly name***>.dll**</span></span>