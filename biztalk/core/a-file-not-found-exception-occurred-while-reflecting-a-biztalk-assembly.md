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
ms.openlocfilehash: 00000896eb4cb97e44ed51602675fc65495552be
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="89971-102">BizTalk アセンブリの反映中に、ファイルが見つからないことを示す例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="89971-102">A file not found exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="89971-103">詳細</span><span class="sxs-lookup"><span data-stu-id="89971-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="89971-104">製品名</span><span class="sxs-lookup"><span data-stu-id="89971-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="89971-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="89971-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="89971-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="89971-106">Event ID</span></span>|<span data-ttu-id="89971-107">0</span><span class="sxs-lookup"><span data-stu-id="89971-107">0</span></span>|  
|<span data-ttu-id="89971-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="89971-108">Event Source</span></span>|<span data-ttu-id="89971-109">0</span><span class="sxs-lookup"><span data-stu-id="89971-109">0</span></span>|  
|<span data-ttu-id="89971-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="89971-110">Component</span></span>|<span data-ttu-id="89971-111">0</span><span class="sxs-lookup"><span data-stu-id="89971-111">0</span></span>|  
|<span data-ttu-id="89971-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="89971-112">Symbolic Name</span></span>|<span data-ttu-id="89971-113">0</span><span class="sxs-lookup"><span data-stu-id="89971-113">0</span></span>|  
|<span data-ttu-id="89971-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="89971-114">Message Text</span></span>|<span data-ttu-id="89971-115">BizTalk アセンブリ "{0}" の反映中に、ファイルが見つからないことを示す例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="89971-115">A file not found exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="89971-116">この問題は、1 つまたは複数の依存関係が使用できない場合に発生することがあります。</span><span class="sxs-lookup"><span data-stu-id="89971-116">This problem may occur if one or more dependencies are not available.</span></span> <span data-ttu-id="89971-117">この問題を解決するには次のいずれかの操作を試してください: 1。</span><span class="sxs-lookup"><span data-stu-id="89971-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="89971-118">アセンブリの依存関係を同じフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="89971-118">Copy the dependencies of the assembly to the same folder.</span></span> <span data-ttu-id="89971-119">2.</span><span class="sxs-lookup"><span data-stu-id="89971-119">2.</span></span> <span data-ttu-id="89971-120">足りない依存関係をグローバル アセンブリ キャッシュにインストールします。</span><span class="sxs-lookup"><span data-stu-id="89971-120">Install the missing dependencies into the Global Assembly Cache.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="89971-121">説明</span><span class="sxs-lookup"><span data-stu-id="89971-121">Explanation</span></span>  
 <span data-ttu-id="89971-122">このエラーは、公開されている BizTalk アセンブリが、グローバル アセンブリ キャッシュ (GAC) または同じディレクトリにないアセンブリを参照していることを示します。</span><span class="sxs-lookup"><span data-stu-id="89971-122">This error indicates the BizTalk Assembly that is being published references another assembly that is not in the Global Assembly Cache (GAC) or in the same directory.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89971-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="89971-123">User Action</span></span>  
 <span data-ttu-id="89971-124">エラー メッセージに指定された操作に加え、参照アセンブリをグローバル アセンブリ キャッシュに移動するか、BizTalk アセンブリと同じ場所にコピーします。</span><span class="sxs-lookup"><span data-stu-id="89971-124">In addition to the actions specified in the error message, move the reference assembly to the Global Assembly Cache or copy it to the same location as the BizTalk assembly</span></span>  
  
1.  <span data-ttu-id="89971-125">をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Visual Studio**、順にクリック**Visual Studio**です。</span><span class="sxs-lookup"><span data-stu-id="89971-125">Click **Start**, point to **All Programs**, point to **Visual Studio**, and then click **Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="89971-126">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="89971-126">Open a command prompt.</span></span>  
  
3.  <span data-ttu-id="89971-127">アセンブリの場所を参照し、入力**gacutil/I/\<***アセンブリ名***\>.dll**</span><span class="sxs-lookup"><span data-stu-id="89971-127">Browse to the location of the assembly, and enter **gacutil /I /\<***assembly name***\>.dll**</span></span>