---
title: ドキュメント仕様の種類が見つかりません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb2a458-d0f4-420d-8d35-0e739167464f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4c63f34d28bf3f53e34f44373d14f6cd6b979f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389343"
---
# <a name="document-spec-type-not-found"></a><span data-ttu-id="9f1bb-102">ドキュメント仕様の種類が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="9f1bb-102">Document spec type not found</span></span>
## <a name="details"></a><span data-ttu-id="9f1bb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9f1bb-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9f1bb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9f1bb-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9f1bb-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9f1bb-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9f1bb-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9f1bb-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9f1bb-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9f1bb-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9f1bb-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9f1bb-108">EDI</span></span> |
|    <span data-ttu-id="9f1bb-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9f1bb-109">Component</span></span>    |                                       <span data-ttu-id="9f1bb-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="9f1bb-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="9f1bb-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9f1bb-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="9f1bb-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9f1bb-112">Message Text</span></span>   |                            <span data-ttu-id="9f1bb-113">ドキュメント仕様の種類が{0}が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="9f1bb-113">Document spec type {0} not found</span></span>                            |
  
## <a name="explanation"></a><span data-ttu-id="9f1bb-114">説明</span><span class="sxs-lookup"><span data-stu-id="9f1bb-114">Explanation</span></span>  
 <span data-ttu-id="9f1bb-115">このエラーは、スキーマが見つからないことを示します。</span><span class="sxs-lookup"><span data-stu-id="9f1bb-115">This error indicates the schema is not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9f1bb-116">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9f1bb-116">User Action</span></span>  
 <span data-ttu-id="9f1bb-117">このエラーを解決するには、ドキュメント スキーマを展開します。</span><span class="sxs-lookup"><span data-stu-id="9f1bb-117">To resolve this error, deploy the document schema:</span></span>  
  
1.  <span data-ttu-id="9f1bb-118">開始**Microsoft Visual Studio**します。</span><span class="sxs-lookup"><span data-stu-id="9f1bb-118">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="9f1bb-119">作成または既存のプロジェクトを開く</span><span class="sxs-lookup"><span data-stu-id="9f1bb-119">Create or open an existing project</span></span>  
  
3.  <span data-ttu-id="9f1bb-120">スキーマをプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="9f1bb-120">Add the schema to the project.</span></span>  
  
4.  <span data-ttu-id="9f1bb-121">Visual Studio でプロジェクトをデプロイします。</span><span class="sxs-lookup"><span data-stu-id="9f1bb-121">Deploy the project in Visual Studio.</span></span>