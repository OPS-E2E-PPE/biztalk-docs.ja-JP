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
ms.openlocfilehash: 3161593fb871e93852480f717216391daac67e7e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362419"
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="755af-102">BizTalk アセンブリの反映中にセキュリティ例外が発生しました</span><span class="sxs-lookup"><span data-stu-id="755af-102">A security exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="755af-103">詳細</span><span class="sxs-lookup"><span data-stu-id="755af-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="755af-104">製品名</span><span class="sxs-lookup"><span data-stu-id="755af-104">Product Name</span></span>   |                                                                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                 |
| <span data-ttu-id="755af-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="755af-105">Product Version</span></span> |                                                                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                             |
|    <span data-ttu-id="755af-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="755af-106">Event ID</span></span>     |                                                                                                                                                                         <span data-ttu-id="755af-107">0</span><span class="sxs-lookup"><span data-stu-id="755af-107">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="755af-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="755af-108">Event Source</span></span>   |                                                                                                                                                                         <span data-ttu-id="755af-109">0</span><span class="sxs-lookup"><span data-stu-id="755af-109">0</span></span>                                                                                                                                                                          |
|    <span data-ttu-id="755af-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="755af-110">Component</span></span>    |                                                                                                                                                                         <span data-ttu-id="755af-111">0</span><span class="sxs-lookup"><span data-stu-id="755af-111">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="755af-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="755af-112">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="755af-113">0</span><span class="sxs-lookup"><span data-stu-id="755af-113">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="755af-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="755af-114">Message Text</span></span>   | <span data-ttu-id="755af-115">BizTalk アセンブリの反映中にセキュリティ例外が発生しました"{0}"。</span><span class="sxs-lookup"><span data-stu-id="755af-115">A security exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="755af-116">この問題は、アセンブリが共有ネットワーク フォルダーにある場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="755af-116">This problem may occur if the assembly is located in a shared network folder.</span></span> <span data-ttu-id="755af-117">この問題を解決するには、次のいずれかを試してください。1.</span><span class="sxs-lookup"><span data-stu-id="755af-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="755af-118">アセンブリとその依存関係をローカル コンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="755af-118">Copy the assembly and its dependencies to the local machine.</span></span> <span data-ttu-id="755af-119">2.</span><span class="sxs-lookup"><span data-stu-id="755af-119">2.</span></span> <span data-ttu-id="755af-120">アクセスを許可するように、.NET 構成のランタイム セキュリティ ポリシーを調整します。</span><span class="sxs-lookup"><span data-stu-id="755af-120">Adjust the .NET Configuration Runtime Security policy to permit access.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="755af-121">説明</span><span class="sxs-lookup"><span data-stu-id="755af-121">Explanation</span></span>  
 <span data-ttu-id="755af-122">適切な .NET ポリシーなしのネットワーク共有上にある BizTalk アセンブリを発行しようとして、このエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="755af-122">This error will occur when trying to publish a BizTalk assembly that is on a network share without the right .NET policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="755af-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="755af-123">User Action</span></span>  
 <span data-ttu-id="755af-124">エラー メッセージに記載されている特定の手順を実行できるだけでなく、ローカル アセンブリをコピーします。</span><span class="sxs-lookup"><span data-stu-id="755af-124">In addition to taking the specific steps outlined in the error message, copy the assembly locally.</span></span> <span data-ttu-id="755af-125">または、ローカルのイントラネットに完全な信頼を付与するポリシーを編集します。</span><span class="sxs-lookup"><span data-stu-id="755af-125">Or edit the policy to grant full trust to the local intranet.</span></span>  
  
 <span data-ttu-id="755af-126">**コード アクセス セキュリティ ポリシー ツール (Caspol.exe) を使用します。**</span><span class="sxs-lookup"><span data-stu-id="755af-126">**Using the Code Access Security Policy Tool (Caspol.exe)**</span></span>  
  
 <span data-ttu-id="755af-127">通常のユーザーのアクセス許可を持つユーザー レベルで、ローカル コンピューター上のフォルダーに信頼を付与できます。</span><span class="sxs-lookup"><span data-stu-id="755af-127">You can grant trust to a folder on your local computer at the User level with normal user permissions.</span></span> <span data-ttu-id="755af-128">ネットワークの場所に信頼を付与するは、管理者特権を持っているし、コンピューター レベルでセキュリティ ポリシーを変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="755af-128">To grant trust to a network location, you must have administrator privileges and change the security policy at the Machine level.</span></span> <span data-ttu-id="755af-129">コンピューター ポリシー レベルが、ユーザー ポリシー レベルとは無関係に機能し、場合でも、ユーザーのポリシーは、コンピューター ポリシー レベルがイントラネット ゾーンに完全な信頼を付与しません。</span><span class="sxs-lookup"><span data-stu-id="755af-129">The Machine policy level acts independently of the User policy level, and the machine policy level does not grant full trust to the Intranet zone even if the User policy does.</span></span> <span data-ttu-id="755af-130">ポリシー レベルが一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="755af-130">The policy levels must agree.</span></span>  
  
 <span data-ttu-id="755af-131">**ローカル フォルダーに完全な信頼を付与するには**</span><span class="sxs-lookup"><span data-stu-id="755af-131">**To grant full trust to a local folder**</span></span>  
  
-   <span data-ttu-id="755af-132">Visual Studio コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="755af-132">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 <span data-ttu-id="755af-133">**ネットワーク フォルダーへの完全な信頼を付与するには**</span><span class="sxs-lookup"><span data-stu-id="755af-133">**To grant full trust to a network folder**</span></span>  
  
-   <span data-ttu-id="755af-134">Visual Studio コマンド プロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="755af-134">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```