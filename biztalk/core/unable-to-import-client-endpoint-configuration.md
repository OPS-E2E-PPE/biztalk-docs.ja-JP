---
title: "クライアント エンドポイント構成をインポートできません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8375e153-ed1c-4bf4-b461-ac026a4b3478
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30be7958ca07dde47d147711da06a276e86ff714
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-import-client-endpoint-configuration"></a><span data-ttu-id="f6316-102">クライアント エンドポイント構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="f6316-102">Unable to import client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="f6316-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f6316-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6316-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f6316-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f6316-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f6316-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="f6316-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f6316-106">Event ID</span></span>|<span data-ttu-id="f6316-107">0</span><span class="sxs-lookup"><span data-stu-id="f6316-107">0</span></span>|  
|<span data-ttu-id="f6316-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f6316-108">Event Source</span></span>|<span data-ttu-id="f6316-109">0</span><span class="sxs-lookup"><span data-stu-id="f6316-109">0</span></span>|  
|<span data-ttu-id="f6316-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f6316-110">Component</span></span>|<span data-ttu-id="f6316-111">0</span><span class="sxs-lookup"><span data-stu-id="f6316-111">0</span></span>|  
|<span data-ttu-id="f6316-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f6316-112">Symbolic Name</span></span>|<span data-ttu-id="f6316-113">0</span><span class="sxs-lookup"><span data-stu-id="f6316-113">0</span></span>|  
|<span data-ttu-id="f6316-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f6316-114">Message Text</span></span>|<span data-ttu-id="f6316-115">クライアント エンドポイント構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="f6316-115">Unable to import client endpoint configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6316-116">説明</span><span class="sxs-lookup"><span data-stu-id="f6316-116">Explanation</span></span>  
 <span data-ttu-id="f6316-117">このエラーについては、複数の説明が考えられます。</span><span class="sxs-lookup"><span data-stu-id="f6316-117">There could be more than one explanation for this error.</span></span> <span data-ttu-id="f6316-118">構成ファイルに無効な文字が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6316-118">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="f6316-119">ルート要素が欠落している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6316-119">The root element may be missing.</span></span> <span data-ttu-id="f6316-120">ルート レベルのデータが無効な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f6316-120">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6316-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f6316-121">User Action</span></span>  
 <span data-ttu-id="f6316-122">構成ファイルが正しいかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="f6316-122">Verify the validity of the configuration file.</span></span> <span data-ttu-id="f6316-123">サービス構成エディターで、構成ファイルを開く (**svcConfigEditor.exe**) の各プロパティを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f6316-123">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>