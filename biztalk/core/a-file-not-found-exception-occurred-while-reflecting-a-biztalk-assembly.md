---
title: ファイルが BizTalk アセンブリの反映中に例外が発生しましたが見つかりません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 223147eb-785f-4dfc-b2a6-7d50dfaf8092
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804428d71c33d0c45d75443bbc5118a2dfed9ac0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362408"
---
# <a name="a-file-not-found-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="c6194-102">BizTalk アセンブリの反映中に、ファイルが見つからないことを示す例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="c6194-102">A file not found exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="c6194-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c6194-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                                                                                        |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c6194-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c6194-104">Product Name</span></span>   |                                                                                                                           [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                           |
| <span data-ttu-id="c6194-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c6194-105">Product Version</span></span> |                                                                                                                                       [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                       |
|    <span data-ttu-id="c6194-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c6194-106">Event ID</span></span>     |                                                                                                                                                                   <span data-ttu-id="c6194-107">0</span><span class="sxs-lookup"><span data-stu-id="c6194-107">0</span></span>                                                                                                                                                                    |
|  <span data-ttu-id="c6194-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c6194-108">Event Source</span></span>   |                                                                                                                                                                   <span data-ttu-id="c6194-109">0</span><span class="sxs-lookup"><span data-stu-id="c6194-109">0</span></span>                                                                                                                                                                    |
|    <span data-ttu-id="c6194-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c6194-110">Component</span></span>    |                                                                                                                                                                   <span data-ttu-id="c6194-111">0</span><span class="sxs-lookup"><span data-stu-id="c6194-111">0</span></span>                                                                                                                                                                    |
|  <span data-ttu-id="c6194-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c6194-112">Symbolic Name</span></span>  |                                                                                                                                                                   <span data-ttu-id="c6194-113">0</span><span class="sxs-lookup"><span data-stu-id="c6194-113">0</span></span>                                                                                                                                                                    |
|  <span data-ttu-id="c6194-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c6194-114">Message Text</span></span>   | <span data-ttu-id="c6194-115">ファイルが BizTalk アセンブリの反映中に例外が発生しましたが見つかりません。"{0}"。</span><span class="sxs-lookup"><span data-stu-id="c6194-115">A file not found exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="c6194-116">この問題は、1 つまたは複数の依存関係が利用できない場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c6194-116">This problem may occur if one or more dependencies are not available.</span></span> <span data-ttu-id="c6194-117">この問題を解決するには、次のいずれかを試してください。1.</span><span class="sxs-lookup"><span data-stu-id="c6194-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="c6194-118">アセンブリの依存関係を同じフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c6194-118">Copy the dependencies of the assembly to the same folder.</span></span> <span data-ttu-id="c6194-119">2.</span><span class="sxs-lookup"><span data-stu-id="c6194-119">2.</span></span> <span data-ttu-id="c6194-120">グローバル アセンブリ キャッシュに見つからない依存関係をインストールします。</span><span class="sxs-lookup"><span data-stu-id="c6194-120">Install the missing dependencies into the Global Assembly Cache.</span></span> |

## <a name="explanation"></a><span data-ttu-id="c6194-121">説明</span><span class="sxs-lookup"><span data-stu-id="c6194-121">Explanation</span></span>  
 <span data-ttu-id="c6194-122">このエラーは、公開された参照されている BizTalk アセンブリがないで、グローバル アセンブリ キャッシュ (GAC) または同じディレクトリに別のアセンブリを示します。</span><span class="sxs-lookup"><span data-stu-id="c6194-122">This error indicates the BizTalk Assembly that is being published references another assembly that is not in the Global Assembly Cache (GAC) or in the same directory.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c6194-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c6194-123">User Action</span></span>  
 <span data-ttu-id="c6194-124">エラー メッセージで指定されたアクションだけでなく、参照アセンブリをグローバル アセンブリ キャッシュに移動または BizTalk アセンブリと同じ場所にコピー</span><span class="sxs-lookup"><span data-stu-id="c6194-124">In addition to the actions specified in the error message, move the reference assembly to the Global Assembly Cache or copy it to the same location as the BizTalk assembly</span></span>  

1. <span data-ttu-id="c6194-125">クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Visual Studio**、順にクリックします**Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="c6194-125">Click **Start**, point to **All Programs**, point to **Visual Studio**, and then click **Visual Studio**.</span></span>  

2. <span data-ttu-id="c6194-126">コマンド プロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="c6194-126">Open a command prompt.</span></span>  

3. <span data-ttu-id="c6194-127">アセンブリの場所を参照し、入力**gacutil/I/\<**<em>アセンブリ名</em>**\>.dll**</span><span class="sxs-lookup"><span data-stu-id="c6194-127">Browse to the location of the assembly, and enter **gacutil /I /\<**<em>assembly name</em>**\>.dll**</span></span>
