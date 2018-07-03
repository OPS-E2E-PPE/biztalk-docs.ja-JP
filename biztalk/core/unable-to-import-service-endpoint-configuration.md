---
title: サービス エンドポイント構成をインポートできません。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dae5154-04e2-4d9b-b2b2-85313683fd9e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d33b9b4963b69ed732c16e266300e398d7884035
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994315"
---
# <a name="unable-to-import-service-endpoint-configuration"></a><span data-ttu-id="7108d-103">サービス エンドポイント構成をインポートできません。</span><span class="sxs-lookup"><span data-stu-id="7108d-103">Unable to import service endpoint configuration.</span></span>
## <a name="details"></a><span data-ttu-id="7108d-104">詳細</span><span class="sxs-lookup"><span data-stu-id="7108d-104">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="7108d-105">製品名</span><span class="sxs-lookup"><span data-stu-id="7108d-105">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="7108d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7108d-106">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="7108d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7108d-107">Event ID</span></span>     |                                         <span data-ttu-id="7108d-108">0</span><span class="sxs-lookup"><span data-stu-id="7108d-108">0</span></span>                                          |
|  <span data-ttu-id="7108d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7108d-109">Event Source</span></span>   |                                         <span data-ttu-id="7108d-110">0</span><span class="sxs-lookup"><span data-stu-id="7108d-110">0</span></span>                                          |
|    <span data-ttu-id="7108d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7108d-111">Component</span></span>    |                                         <span data-ttu-id="7108d-112">0</span><span class="sxs-lookup"><span data-stu-id="7108d-112">0</span></span>                                          |
|  <span data-ttu-id="7108d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7108d-113">Symbolic Name</span></span>  |                                         <span data-ttu-id="7108d-114">0</span><span class="sxs-lookup"><span data-stu-id="7108d-114">0</span></span>                                          |
|  <span data-ttu-id="7108d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7108d-115">Message Text</span></span>   |                  <span data-ttu-id="7108d-116">サービス エンドポイント構成をインポートできません</span><span class="sxs-lookup"><span data-stu-id="7108d-116">Unable to import service endpoint configuration</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="7108d-117">説明</span><span class="sxs-lookup"><span data-stu-id="7108d-117">Explanation</span></span>  
 <span data-ttu-id="7108d-118">このエラーについては、複数の説明が考えられます。</span><span class="sxs-lookup"><span data-stu-id="7108d-118">There could be more than one explanation for this error.</span></span> <span data-ttu-id="7108d-119">構成ファイルに無効な文字が含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7108d-119">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="7108d-120">ルート要素が欠落している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7108d-120">The root element may be missing.</span></span> <span data-ttu-id="7108d-121">ルート レベルのデータが無効な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="7108d-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7108d-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7108d-122">User Action</span></span>  
 <span data-ttu-id="7108d-123">構成ファイルが正しいかどうかを検証します。</span><span class="sxs-lookup"><span data-stu-id="7108d-123">Verify the validity of the configuration file.</span></span> <span data-ttu-id="7108d-124">構成ファイル、サービス構成エディターを開く (**svcConfigEditor.exe**) 各プロパティを確認します。</span><span class="sxs-lookup"><span data-stu-id="7108d-124">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>