---
title: "BizTalk アセンブリの反映中にセキュリティ例外が発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 301b85c7-8e67-482e-8666-67a91ca5c73d
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca28c534b910479be3ae6ad26bd1e0a27a1637d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="d752c-102">BizTalk アセンブリの反映中にセキュリティ例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="d752c-102">A security exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="d752c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d752c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d752c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d752c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d752c-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d752c-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="d752c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d752c-106">Event ID</span></span>|<span data-ttu-id="d752c-107">0</span><span class="sxs-lookup"><span data-stu-id="d752c-107">0</span></span>|  
|<span data-ttu-id="d752c-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d752c-108">Event Source</span></span>|<span data-ttu-id="d752c-109">0</span><span class="sxs-lookup"><span data-stu-id="d752c-109">0</span></span>|  
|<span data-ttu-id="d752c-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d752c-110">Component</span></span>|<span data-ttu-id="d752c-111">0</span><span class="sxs-lookup"><span data-stu-id="d752c-111">0</span></span>|  
|<span data-ttu-id="d752c-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d752c-112">Symbolic Name</span></span>|<span data-ttu-id="d752c-113">0</span><span class="sxs-lookup"><span data-stu-id="d752c-113">0</span></span>|  
|<span data-ttu-id="d752c-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d752c-114">Message Text</span></span>|<span data-ttu-id="d752c-115">BizTalk アセンブリ "{0}" の反映中にセキュリティ例外が発生しました。</span><span class="sxs-lookup"><span data-stu-id="d752c-115">A security exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="d752c-116">この問題は、アセンブリが共有ネットワーク フォルダーに格納されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d752c-116">This problem may occur if the assembly is located in a shared network folder.</span></span> <span data-ttu-id="d752c-117">この問題を解決するには次のいずれかの操作を試してください: 1。</span><span class="sxs-lookup"><span data-stu-id="d752c-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="d752c-118">アセンブリとその依存関係をローカル コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d752c-118">Copy the assembly and its dependencies to the local machine.</span></span> <span data-ttu-id="d752c-119">2.</span><span class="sxs-lookup"><span data-stu-id="d752c-119">2.</span></span> <span data-ttu-id="d752c-120">.NET 構成のランタイム セキュリティ ポリシーを調整して、アクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d752c-120">Adjust the .NET Configuration Runtime Security policy to permit access.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d752c-121">説明</span><span class="sxs-lookup"><span data-stu-id="d752c-121">Explanation</span></span>  
 <span data-ttu-id="d752c-122">このエラーは、適切な .NET ポリシーが設定されていない状態で、ネットワーク共有上にある BizTalk アセンブリを発行しようとするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="d752c-122">This error will occur when trying to publish a BizTalk assembly that is on a network share without the right .NET policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d752c-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d752c-123">User Action</span></span>  
 <span data-ttu-id="d752c-124">エラー メッセージに指定された手順を実行し、さらにアセンブリをローカルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d752c-124">In addition to taking the specific steps outlined in the error message, copy the assembly locally.</span></span> <span data-ttu-id="d752c-125">または、ローカル イントラネットに完全信頼を付与するようにポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="d752c-125">Or edit the policy to grant full trust to the local intranet.</span></span>  
  
 <span data-ttu-id="d752c-126">**コード アクセス セキュリティ ポリシー ツール (Caspol.exe) を使用します。**</span><span class="sxs-lookup"><span data-stu-id="d752c-126">**Using the Code Access Security Policy Tool (Caspol.exe)**</span></span>  
  
 <span data-ttu-id="d752c-127">通常のユーザー アクセス許可では、ユーザー レベルでローカル コンピューターのフォルダーに信頼を付与できます。</span><span class="sxs-lookup"><span data-stu-id="d752c-127">You can grant trust to a folder on your local computer at the User level with normal user permissions.</span></span> <span data-ttu-id="d752c-128">ネットワークの場所に信頼を付与するには、管理者特権が必要です。また、コンピューター レベルでセキュリティ ポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d752c-128">To grant trust to a network location, you must have administrator privileges and change the security policy at the Machine level.</span></span> <span data-ttu-id="d752c-129">コンピューター ポリシー レベルは、ユーザー ポリシー レベルとは関係なく動作するため、コンピューター ポリシー レベルでは、ユーザー ポリシーとは異なり、イントラネット ゾーンに完全信頼を付与しません。</span><span class="sxs-lookup"><span data-stu-id="d752c-129">The Machine policy level acts independently of the User policy level, and the machine policy level does not grant full trust to the Intranet zone even if the User policy does.</span></span> <span data-ttu-id="d752c-130">ポリシー レベルは一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d752c-130">The policy levels must agree.</span></span>  
  
 <span data-ttu-id="d752c-131">**ローカル フォルダーに完全信頼を付与するには**</span><span class="sxs-lookup"><span data-stu-id="d752c-131">**To grant full trust to a local folder**</span></span>  
  
-   <span data-ttu-id="d752c-132">Visual Studio コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d752c-132">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 <span data-ttu-id="d752c-133">**ネットワーク フォルダーへの完全信頼を付与するには**</span><span class="sxs-lookup"><span data-stu-id="d752c-133">**To grant full trust to a network folder**</span></span>  
  
-   <span data-ttu-id="d752c-134">Visual Studio コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="d752c-134">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```