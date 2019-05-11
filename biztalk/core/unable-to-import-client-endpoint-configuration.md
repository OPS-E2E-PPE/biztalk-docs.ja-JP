---
title: クライアント エンドポイント構成をインポートできません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8375e153-ed1c-4bf4-b461-ac026a4b3478
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8337af0d97eaf3ba8b1737ca8641389bda984cee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292752"
---
# <a name="unable-to-import-client-endpoint-configuration"></a><span data-ttu-id="89337-102">クライアント エンドポイント構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="89337-102">Unable to import client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="89337-103">詳細</span><span class="sxs-lookup"><span data-stu-id="89337-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="89337-104">製品名</span><span class="sxs-lookup"><span data-stu-id="89337-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="89337-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="89337-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="89337-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="89337-106">Event ID</span></span>     |                                         <span data-ttu-id="89337-107">0</span><span class="sxs-lookup"><span data-stu-id="89337-107">0</span></span>                                          |
|  <span data-ttu-id="89337-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="89337-108">Event Source</span></span>   |                                         <span data-ttu-id="89337-109">0</span><span class="sxs-lookup"><span data-stu-id="89337-109">0</span></span>                                          |
|    <span data-ttu-id="89337-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="89337-110">Component</span></span>    |                                         <span data-ttu-id="89337-111">0</span><span class="sxs-lookup"><span data-stu-id="89337-111">0</span></span>                                          |
|  <span data-ttu-id="89337-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="89337-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="89337-113">0</span><span class="sxs-lookup"><span data-stu-id="89337-113">0</span></span>                                          |
|  <span data-ttu-id="89337-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="89337-114">Message Text</span></span>   |                   <span data-ttu-id="89337-115">クライアント エンドポイント構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="89337-115">Unable to import client endpoint configuration</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="89337-116">説明</span><span class="sxs-lookup"><span data-stu-id="89337-116">Explanation</span></span>  
 <span data-ttu-id="89337-117">このエラーの 1 つ以上の説明があります。</span><span class="sxs-lookup"><span data-stu-id="89337-117">There could be more than one explanation for this error.</span></span> <span data-ttu-id="89337-118">構成ファイルには、無効な文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="89337-118">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="89337-119">ルート要素がない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89337-119">The root element may be missing.</span></span> <span data-ttu-id="89337-120">ルート レベルのデータは、有効でない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="89337-120">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="89337-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="89337-121">User Action</span></span>  
 <span data-ttu-id="89337-122">構成ファイルの有効性を確認します。</span><span class="sxs-lookup"><span data-stu-id="89337-122">Verify the validity of the configuration file.</span></span> <span data-ttu-id="89337-123">構成ファイル、サービス構成エディターを開く (**svcConfigEditor.exe**) 各プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="89337-123">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>