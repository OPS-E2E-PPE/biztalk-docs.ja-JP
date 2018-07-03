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
ms.openlocfilehash: 2f3faa6a12bee397edcadb3f15c12a47d763fdce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987187"
---
# <a name="unable-to-import-client-endpoint-configuration"></a><span data-ttu-id="57b7e-102">クライアント エンドポイント構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="57b7e-102">Unable to import client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="57b7e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="57b7e-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="57b7e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="57b7e-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="57b7e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="57b7e-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="57b7e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="57b7e-106">Event ID</span></span>     |                                         <span data-ttu-id="57b7e-107">0</span><span class="sxs-lookup"><span data-stu-id="57b7e-107">0</span></span>                                          |
|  <span data-ttu-id="57b7e-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="57b7e-108">Event Source</span></span>   |                                         <span data-ttu-id="57b7e-109">0</span><span class="sxs-lookup"><span data-stu-id="57b7e-109">0</span></span>                                          |
|    <span data-ttu-id="57b7e-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="57b7e-110">Component</span></span>    |                                         <span data-ttu-id="57b7e-111">0</span><span class="sxs-lookup"><span data-stu-id="57b7e-111">0</span></span>                                          |
|  <span data-ttu-id="57b7e-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="57b7e-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="57b7e-113">0</span><span class="sxs-lookup"><span data-stu-id="57b7e-113">0</span></span>                                          |
|  <span data-ttu-id="57b7e-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="57b7e-114">Message Text</span></span>   |                   <span data-ttu-id="57b7e-115">クライアント エンドポイント構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="57b7e-115">Unable to import client endpoint configuration</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="57b7e-116">説明</span><span class="sxs-lookup"><span data-stu-id="57b7e-116">Explanation</span></span>  
 <span data-ttu-id="57b7e-117">このエラーについては、複数の説明が考えられます。</span><span class="sxs-lookup"><span data-stu-id="57b7e-117">There could be more than one explanation for this error.</span></span> <span data-ttu-id="57b7e-118">構成ファイルに無効な文字が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57b7e-118">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="57b7e-119">ルート要素が欠落している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57b7e-119">The root element may be missing.</span></span> <span data-ttu-id="57b7e-120">ルート レベルのデータが無効な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="57b7e-120">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="57b7e-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="57b7e-121">User Action</span></span>  
 <span data-ttu-id="57b7e-122">構成ファイルが正しいかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="57b7e-122">Verify the validity of the configuration file.</span></span> <span data-ttu-id="57b7e-123">構成ファイル、サービス構成エディターを開く (**svcConfigEditor.exe**) 各プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="57b7e-123">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>