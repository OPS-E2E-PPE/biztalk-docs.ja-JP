---
title: 名前空間の型が見つからない |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 515dd9b6b73b43bee22ffc7b67745bb45adcaf6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286458"
---
# <a name="type-cannot-be-found-in-namespace"></a><span data-ttu-id="1e26d-102">種類が名前空間に見つかりません</span><span class="sxs-lookup"><span data-stu-id="1e26d-102">Type cannot be found in namespace</span></span>
## <a name="details"></a><span data-ttu-id="1e26d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1e26d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1e26d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1e26d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="1e26d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1e26d-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="1e26d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1e26d-106">Event ID</span></span>|<span data-ttu-id="1e26d-107">0</span><span class="sxs-lookup"><span data-stu-id="1e26d-107">0</span></span>|  
|<span data-ttu-id="1e26d-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1e26d-108">Event Source</span></span>|<span data-ttu-id="1e26d-109">0</span><span class="sxs-lookup"><span data-stu-id="1e26d-109">0</span></span>|  
|<span data-ttu-id="1e26d-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1e26d-110">Component</span></span>|<span data-ttu-id="1e26d-111">0</span><span class="sxs-lookup"><span data-stu-id="1e26d-111">0</span></span>|  
|<span data-ttu-id="1e26d-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1e26d-112">Symbolic Name</span></span>|<span data-ttu-id="1e26d-113">0</span><span class="sxs-lookup"><span data-stu-id="1e26d-113">0</span></span>|  
|<span data-ttu-id="1e26d-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1e26d-114">Message Text</span></span>|<span data-ttu-id="1e26d-115">エラー:"{0}"の種類が見つかりません「{1}」名前空間</span><span class="sxs-lookup"><span data-stu-id="1e26d-115">Error: Type "{0}" cannot be found in namespace "{1}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1e26d-116">説明</span><span class="sxs-lookup"><span data-stu-id="1e26d-116">Explanation</span></span>  
 <span data-ttu-id="1e26d-117">このエラーは、作成されたアイテムが、指定した名前空間に存在しない種類を参照していることを示します。</span><span class="sxs-lookup"><span data-stu-id="1e26d-117">This error indicates artifacts that are created are referencing types which cannot be found in the namespace specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1e26d-118">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1e26d-118">User Action</span></span>  
 <span data-ttu-id="1e26d-119">存在しない種類を含む参照を追加し、ウィザードを再実行します (使用する予定の WCF サービスを所有している場合)。</span><span class="sxs-lookup"><span data-stu-id="1e26d-119">Add a reference that contain the type that is not found, and run the wizard again (if you own the WCF service that you are trying to consume).</span></span> <span data-ttu-id="1e26d-120">それ以外の場合、サービス プロバイダーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="1e26d-120">Otherwise, contact the service provider.</span></span>