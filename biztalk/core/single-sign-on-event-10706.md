---
title: "シングル サインオン: イベント 10706 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d73db77e-5bb6-431c-a8ca-5682d7ab3d6a
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5703c81d87376349561f644da558b8594cd51b79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10706"></a><span data-ttu-id="1cd9a-102">シングル サインオン: イベント 10706</span><span class="sxs-lookup"><span data-stu-id="1cd9a-102">Single Sign-On: Event 10706</span></span>
## <a name="details"></a><span data-ttu-id="1cd9a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1cd9a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1cd9a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1cd9a-104">Product Name</span></span>|<span data-ttu-id="1cd9a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1cd9a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="1cd9a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1cd9a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="1cd9a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1cd9a-107">Event ID</span></span>|<span data-ttu-id="1cd9a-108">10706</span><span class="sxs-lookup"><span data-stu-id="1cd9a-108">10706</span></span>|  
|<span data-ttu-id="1cd9a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1cd9a-109">Event Source</span></span>|<span data-ttu-id="1cd9a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1cd9a-110">ENTSSO</span></span>|  
|<span data-ttu-id="1cd9a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1cd9a-111">Component</span></span>|<span data-ttu-id="1cd9a-112">N\A</span><span class="sxs-lookup"><span data-stu-id="1cd9a-112">N\A</span></span>|  
|<span data-ttu-id="1cd9a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1cd9a-113">Symbolic Name</span></span>|<span data-ttu-id="1cd9a-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span><span class="sxs-lookup"><span data-stu-id="1cd9a-114">SSO_WARN_PS_NO_GLOBAL_SYNC</span></span>|  
|<span data-ttu-id="1cd9a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1cd9a-115">Message Text</span></span>|<span data-ttu-id="1cd9a-116">グループ アダプターはグローバル フラグによってパスワード同期を許可される必要があります。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-116">Group adapters require password sync to be allowed by the global flags.</span></span> <span data-ttu-id="1cd9a-117">グローバル フラグを確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="1cd9a-117">Check the global flags.%r</span></span><br /><br /> <span data-ttu-id="1cd9a-118">アダプタ: %1</span><span class="sxs-lookup"><span data-stu-id="1cd9a-118">Adapter: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1cd9a-119">説明</span><span class="sxs-lookup"><span data-stu-id="1cd9a-119">Explanation</span></span>  
 <span data-ttu-id="1cd9a-120">この警告イベントは、外部パスワード同期アダプターによってパスワード同期が要求され、いずれのグローバル フラグも設定されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-120">This Warning event indicates that password sync is requested by an external password sync adapter and neither of the global flags is set.</span></span> <span data-ttu-id="1cd9a-121">いずれかの外部システムへのパスワードの送信を許可する 2 つのフラグ: する SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB の外部システムからパスワードの受信を許可する SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL で、もうです。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-121">There are two flags, one that allows sending of password to external system: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL and another that allows receiving of passwords from external systems SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cd9a-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1cd9a-122">User Action</span></span>  
 <span data-ttu-id="1cd9a-123">この警告を解決するには、次の操作を行います: </span><span class="sxs-lookup"><span data-stu-id="1cd9a-123">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="1cd9a-124">SSO 管理 MMC スナップインで、(システム (&) #124; を使用します。プロパティ & #124 です。オプション) またはコマンド ライン ツール`ssomanage –enable winsync/extsync`グローバル フラグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="1cd9a-124">Use the SSO Admin MMC Snap-In, (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="1cd9a-125">詳細</span><span class="sxs-lookup"><span data-stu-id="1cd9a-125">More info</span></span>
  
-   <span data-ttu-id="1cd9a-126">**エンタープライズ シングル サインオン フラグ**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="1cd9a-126">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="1cd9a-127">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="1cd9a-127">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)