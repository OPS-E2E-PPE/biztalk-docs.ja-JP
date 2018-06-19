---
title: 'シングル サインオン: イベント 10830 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd149be1-0a4f-4d39-9b0e-35202dc140cb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5944fe4e0af6c5e0484fd344d08ef839901e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276426"
---
# <a name="single-sign-on-event-10830"></a><span data-ttu-id="c9d8c-102">シングル サインオン: イベント 10830</span><span class="sxs-lookup"><span data-stu-id="c9d8c-102">Single Sign-On: Event 10830</span></span>
## <a name="details"></a><span data-ttu-id="c9d8c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c9d8c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c9d8c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c9d8c-104">Product Name</span></span>|<span data-ttu-id="c9d8c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c9d8c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="c9d8c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c9d8c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="c9d8c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c9d8c-107">Event ID</span></span>|<span data-ttu-id="c9d8c-108">10830</span><span class="sxs-lookup"><span data-stu-id="c9d8c-108">10830</span></span>|  
|<span data-ttu-id="c9d8c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c9d8c-109">Event Source</span></span>|<span data-ttu-id="c9d8c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c9d8c-110">ENTSSO</span></span>|  
|<span data-ttu-id="c9d8c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c9d8c-111">Component</span></span>|<span data-ttu-id="c9d8c-112">なし</span><span class="sxs-lookup"><span data-stu-id="c9d8c-112">N/A</span></span>|  
|<span data-ttu-id="c9d8c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c9d8c-113">Symbolic Name</span></span>|<span data-ttu-id="c9d8c-114">ENTSSO_E_PSADMIN_ADAPTER_SAME_COMPUTER</span><span class="sxs-lookup"><span data-stu-id="c9d8c-114">ENTSSO_E_PSADMIN_ADAPTER_SAME_COMPUTER</span></span>|  
|<span data-ttu-id="c9d8c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c9d8c-115">Message Text</span></span>|<span data-ttu-id="c9d8c-116">指定されたアダプターは、グループ アダプターと同じコンピューター上に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d8c-116">The specified adapter must be on the same computer as the group adapter.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c9d8c-117">説明</span><span class="sxs-lookup"><span data-stu-id="c9d8c-117">Explanation</span></span>  
 <span data-ttu-id="c9d8c-118">グループ アダプター内の各アダプターは、グループ アダプターと同じコンピューター名で構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9d8c-118">Each adapter in a group adapter must be configured with the same computer name as the group adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c9d8c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c9d8c-119">User Action</span></span>  
 <span data-ttu-id="c9d8c-120">詳細については、次を参照してください[パスワード同期。](../core/password-synchronization2.md)</span><span class="sxs-lookup"><span data-stu-id="c9d8c-120">For more information, see [Password Synchronization](../core/password-synchronization2.md)</span></span>  
  
 <span data-ttu-id="c9d8c-121">のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c9d8c-121">.</span></span>