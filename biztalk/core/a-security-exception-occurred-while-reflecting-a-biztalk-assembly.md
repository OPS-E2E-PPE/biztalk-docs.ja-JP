---
title: BizTalk アセンブリの反映中にセキュリティ例外が発生しました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 301b85c7-8e67-482e-8666-67a91ca5c73d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d07b1e5788ae696e94a3bbe326f2cfe79d1b76f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979931"
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="c390d-102">BizTalk アセンブリの反映中にセキュリティ例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="c390d-102">A security exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="c390d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c390d-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c390d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c390d-104">Product Name</span></span>   |                                                                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                 |
| <span data-ttu-id="c390d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c390d-105">Product Version</span></span> |                                                                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                             |
|    <span data-ttu-id="c390d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c390d-106">Event ID</span></span>     |                                                                                                                                                                         <span data-ttu-id="c390d-107">0</span><span class="sxs-lookup"><span data-stu-id="c390d-107">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="c390d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c390d-108">Event Source</span></span>   |                                                                                                                                                                         <span data-ttu-id="c390d-109">0</span><span class="sxs-lookup"><span data-stu-id="c390d-109">0</span></span>                                                                                                                                                                          |
|    <span data-ttu-id="c390d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c390d-110">Component</span></span>    |                                                                                                                                                                         <span data-ttu-id="c390d-111">0</span><span class="sxs-lookup"><span data-stu-id="c390d-111">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="c390d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c390d-112">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="c390d-113">0</span><span class="sxs-lookup"><span data-stu-id="c390d-113">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="c390d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c390d-114">Message Text</span></span>   | <span data-ttu-id="c390d-115">BizTalk アセンブリの反映中にセキュリティ例外が発生しました"{0}"。</span><span class="sxs-lookup"><span data-stu-id="c390d-115">A security exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="c390d-116">この問題は、アセンブリが共有ネットワーク フォルダーに格納されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c390d-116">This problem may occur if the assembly is located in a shared network folder.</span></span> <span data-ttu-id="c390d-117">この問題を修正する、次のいずれかの操作を試してください: 1。</span><span class="sxs-lookup"><span data-stu-id="c390d-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="c390d-118">アセンブリとその依存関係をローカル コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c390d-118">Copy the assembly and its dependencies to the local machine.</span></span> <span data-ttu-id="c390d-119">2.</span><span class="sxs-lookup"><span data-stu-id="c390d-119">2.</span></span> <span data-ttu-id="c390d-120">.NET 構成のランタイム セキュリティ ポリシーを調整して、アクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c390d-120">Adjust the .NET Configuration Runtime Security policy to permit access.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="c390d-121">説明</span><span class="sxs-lookup"><span data-stu-id="c390d-121">Explanation</span></span>  
 <span data-ttu-id="c390d-122">このエラーは、適切な .NET ポリシーが設定されていない状態で、ネットワーク共有上にある BizTalk アセンブリを発行しようとするときに発生します。</span><span class="sxs-lookup"><span data-stu-id="c390d-122">This error will occur when trying to publish a BizTalk assembly that is on a network share without the right .NET policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c390d-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c390d-123">User Action</span></span>  
 <span data-ttu-id="c390d-124">エラー メッセージに指定された手順を実行し、さらにアセンブリをローカルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c390d-124">In addition to taking the specific steps outlined in the error message, copy the assembly locally.</span></span> <span data-ttu-id="c390d-125">または、ローカル イントラネットに完全信頼を付与するようにポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="c390d-125">Or edit the policy to grant full trust to the local intranet.</span></span>  
  
 <span data-ttu-id="c390d-126">**コード アクセス セキュリティ ポリシー ツール (Caspol.exe) を使用します。**</span><span class="sxs-lookup"><span data-stu-id="c390d-126">**Using the Code Access Security Policy Tool (Caspol.exe)**</span></span>  
  
 <span data-ttu-id="c390d-127">通常のユーザー アクセス許可では、ユーザー レベルでローカル コンピューターのフォルダーに信頼を付与できます。</span><span class="sxs-lookup"><span data-stu-id="c390d-127">You can grant trust to a folder on your local computer at the User level with normal user permissions.</span></span> <span data-ttu-id="c390d-128">ネットワークの場所に信頼を付与するには、管理者特権が必要です。また、コンピューター レベルでセキュリティ ポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c390d-128">To grant trust to a network location, you must have administrator privileges and change the security policy at the Machine level.</span></span> <span data-ttu-id="c390d-129">コンピューター ポリシー レベルは、ユーザー ポリシー レベルとは関係なく動作するため、コンピューター ポリシー レベルでは、ユーザー ポリシーとは異なり、イントラネット ゾーンに完全信頼を付与しません。</span><span class="sxs-lookup"><span data-stu-id="c390d-129">The Machine policy level acts independently of the User policy level, and the machine policy level does not grant full trust to the Intranet zone even if the User policy does.</span></span> <span data-ttu-id="c390d-130">ポリシー レベルは一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c390d-130">The policy levels must agree.</span></span>  
  
 <span data-ttu-id="c390d-131">**ローカル フォルダーに完全な信頼を付与するには**</span><span class="sxs-lookup"><span data-stu-id="c390d-131">**To grant full trust to a local folder**</span></span>  
  
-   <span data-ttu-id="c390d-132">Visual Studio コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c390d-132">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 <span data-ttu-id="c390d-133">**ネットワーク フォルダーへの完全な信頼を付与するには**</span><span class="sxs-lookup"><span data-stu-id="c390d-133">**To grant full trust to a network folder**</span></span>  
  
-   <span data-ttu-id="c390d-134">Visual Studio コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="c390d-134">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```