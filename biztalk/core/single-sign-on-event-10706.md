---
title: シングル サインオン:イベント 10706 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7484ddf2b669976919b493230995c4ba233b3662
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397270"
---
# <a name="single-sign-on-event-10706"></a><span data-ttu-id="2a7bf-102">シングル サインオン:イベント 10706</span><span class="sxs-lookup"><span data-stu-id="2a7bf-102">Single Sign-On: Event 10706</span></span>
## <a name="details"></a><span data-ttu-id="2a7bf-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2a7bf-103">Details</span></span>  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2a7bf-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2a7bf-104">Product Name</span></span>   |                                                 <span data-ttu-id="2a7bf-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="2a7bf-105">Enterprise Single Sign-On</span></span>                                                 |
| <span data-ttu-id="2a7bf-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2a7bf-106">Product Version</span></span> |                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                 |
|    <span data-ttu-id="2a7bf-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2a7bf-107">Event ID</span></span>     |                                                           <span data-ttu-id="2a7bf-108">10706</span><span class="sxs-lookup"><span data-stu-id="2a7bf-108">10706</span></span>                                                           |
|  <span data-ttu-id="2a7bf-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2a7bf-109">Event Source</span></span>   |                                                          <span data-ttu-id="2a7bf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2a7bf-110">ENTSSO</span></span>                                                           |
|    <span data-ttu-id="2a7bf-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2a7bf-111">Component</span></span>    |                                                            <span data-ttu-id="2a7bf-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="2a7bf-112">N\A</span></span>                                                            |
|  <span data-ttu-id="2a7bf-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2a7bf-113">Symbolic Name</span></span>  |                                                <span data-ttu-id="2a7bf-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span><span class="sxs-lookup"><span data-stu-id="2a7bf-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span></span>                                                 |
|  <span data-ttu-id="2a7bf-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2a7bf-115">Message Text</span></span>   | <span data-ttu-id="2a7bf-116">グループ アダプターには、パスワード同期をグローバル フラグによって許可される必要があります。</span><span class="sxs-lookup"><span data-stu-id="2a7bf-116">Group adapters require password sync to be allowed by the global flags.</span></span> <span data-ttu-id="2a7bf-117">グローバル flags.%r を確認してください。</span><span class="sxs-lookup"><span data-stu-id="2a7bf-117">Check the global flags.%r</span></span><br /><br /> <span data-ttu-id="2a7bf-118">アダプタ: %1</span><span class="sxs-lookup"><span data-stu-id="2a7bf-118">Adapter: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="2a7bf-119">説明</span><span class="sxs-lookup"><span data-stu-id="2a7bf-119">Explanation</span></span>  
 <span data-ttu-id="2a7bf-120">この警告イベントは、外部パスワード同期アダプターによってパスワード同期を要求し、グローバル フラグも設定されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="2a7bf-120">This Warning event indicates that password sync is requested by an external password sync adapter and neither of the global flags is set.</span></span> <span data-ttu-id="2a7bf-121">これには、いずれかの外部システムへのパスワードの送信を許可する 2 つのフラグがあります。SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL で、もう SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB の外部システムからパスワードの受信を許可します。</span><span class="sxs-lookup"><span data-stu-id="2a7bf-121">There are two flags, one that allows sending of password to external system: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL and another that allows receiving of passwords from external systems SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB.</span></span>  

## <a name="user-action"></a><span data-ttu-id="2a7bf-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2a7bf-122">User Action</span></span>  
 <span data-ttu-id="2a7bf-123">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2a7bf-123">To resolve this warning, do the following:</span></span>  

-   <span data-ttu-id="2a7bf-124">SSO 管理 MMC スナップインで、(システム 使用 &#124; 文字です。プロパティと &#124; 文字です。オプション) またはコマンド ライン ツール  `ssomanage –enable winsync/extsync` グローバル フラグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2a7bf-124">Use the SSO Admin MMC Snap-In, (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  

## <a name="more-info"></a><span data-ttu-id="2a7bf-125">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2a7bf-125">More info</span></span>

- <span data-ttu-id="2a7bf-126">**エンタープライズ シングル サインオン フラグ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="2a7bf-126">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>

- [<span data-ttu-id="2a7bf-127">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="2a7bf-127">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)
