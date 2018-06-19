---
title: 'シングル サインオン: イベント 10547 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f6162461b1eb04993ca681049fe1fbb797ca014
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270722"
---
# <a name="single-sign-on-event-10547"></a><span data-ttu-id="b23ed-102">シングル サインオン: イベント 10547</span><span class="sxs-lookup"><span data-stu-id="b23ed-102">Single Sign-On: Event 10547</span></span>
## <a name="details"></a><span data-ttu-id="b23ed-103">詳細</span><span class="sxs-lookup"><span data-stu-id="b23ed-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="b23ed-104">製品名</span><span class="sxs-lookup"><span data-stu-id="b23ed-104">Product Name</span></span>|<span data-ttu-id="b23ed-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="b23ed-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="b23ed-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="b23ed-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="b23ed-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="b23ed-107">Event ID</span></span>|<span data-ttu-id="b23ed-108">10547</span><span class="sxs-lookup"><span data-stu-id="b23ed-108">10547</span></span>|  
|<span data-ttu-id="b23ed-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="b23ed-109">Event Source</span></span>|<span data-ttu-id="b23ed-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b23ed-110">ENTSSO</span></span>|  
|<span data-ttu-id="b23ed-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="b23ed-111">Component</span></span>|<span data-ttu-id="b23ed-112">CO</span><span class="sxs-lookup"><span data-stu-id="b23ed-112">CO</span></span>|  
|<span data-ttu-id="b23ed-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="b23ed-113">Symbolic Name</span></span>|<span data-ttu-id="b23ed-114">SSO_WARN_UPDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="b23ed-114">SSO_WARN_UPDATE_FAILED</span></span>|  
|<span data-ttu-id="b23ed-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="b23ed-115">Message Text</span></span>|<span data-ttu-id="b23ed-116">再暗号化の間に SSO データベース内の資格情報を更新できませんでした</span><span class="sxs-lookup"><span data-stu-id="b23ed-116">Failed to update the credentials in the SSO database during re-encryption</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="b23ed-117">説明</span><span class="sxs-lookup"><span data-stu-id="b23ed-117">Explanation</span></span>  
 <span data-ttu-id="b23ed-118">この警告イベントは、新しい暗号化の結果で資格情報を更新できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="b23ed-118">This Warning event indicates that it was not possible to update the credentials with the result of the new encryption.</span></span> <span data-ttu-id="b23ed-119">新しいシークレットの入力または古いシークレットの復元によってマスター シークレットを変更すると、SSO データベースに格納されている古いシークレットで暗号化されたすべてのシークレットが復号化され、新しいシークレットで再暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="b23ed-119">When the master secret is changed, either by generating a new secret or by restoring an old secret, a re-encryption is performed on the SSO database to decrypt all the secrets encrypted with the old secret, and re-encrypt them with the new secret.</span></span> <span data-ttu-id="b23ed-120">再暗号化の過程で資格情報が削除された場合、このイベントが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b23ed-120">This event can occur if the credentials were deleted as they were in the process of being re-encrypted.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b23ed-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b23ed-121">User Action</span></span>  
 <span data-ttu-id="b23ed-122">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="b23ed-122">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="b23ed-123">別の再暗号化が行われるまでしばらく待ちます。自動的に行われない場合は、SSO サービスを再起動すると、必要な場合は新しい再暗号化が実行されます。</span><span class="sxs-lookup"><span data-stu-id="b23ed-123">Wait for another re-encryption to occur after a short delay; if that does not occur automatically, restart the SSO service which will trigger a new re-encryption if one is required.</span></span>  
  
 <span data-ttu-id="b23ed-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="b23ed-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="b23ed-125">SSO について</span><span class="sxs-lookup"><span data-stu-id="b23ed-125">Understanding SSO</span></span>](../core/understanding-sso.md)