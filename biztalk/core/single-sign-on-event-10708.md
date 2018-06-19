---
title: 'シングル サインオン: イベント 10708 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63675191-41cb-43fc-9355-e4ddc3f354c5
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d600c39b2e79e619e5adfbda2ffc152169ccd5d4
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
ms.locfileid: "22271698"
---
# <a name="single-sign-on-event-10708"></a><span data-ttu-id="58523-102">シングル サインオン: イベント 10708</span><span class="sxs-lookup"><span data-stu-id="58523-102">Single Sign-On: Event 10708</span></span>
## <a name="details"></a><span data-ttu-id="58523-103">詳細</span><span class="sxs-lookup"><span data-stu-id="58523-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58523-104">製品名</span><span class="sxs-lookup"><span data-stu-id="58523-104">Product Name</span></span>|<span data-ttu-id="58523-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="58523-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="58523-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="58523-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="58523-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="58523-107">Event ID</span></span>|<span data-ttu-id="58523-108">10708</span><span class="sxs-lookup"><span data-stu-id="58523-108">10708</span></span>|  
|<span data-ttu-id="58523-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="58523-109">Event Source</span></span>|<span data-ttu-id="58523-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="58523-110">ENTSSO</span></span>|  
|<span data-ttu-id="58523-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="58523-111">Component</span></span>|<span data-ttu-id="58523-112">N\A</span><span class="sxs-lookup"><span data-stu-id="58523-112">N\A</span></span>|  
|<span data-ttu-id="58523-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="58523-113">Symbolic Name</span></span>|<span data-ttu-id="58523-114">SSO_WARN_PS_NO_WIN_SYNC</span><span class="sxs-lookup"><span data-stu-id="58523-114">SSO_WARN_PS_NO_WIN_SYNC</span></span>|  
|<span data-ttu-id="58523-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="58523-115">Message Text</span></span>|<span data-ttu-id="58523-116">Windows からのパスワード同期は許可されていません。</span><span class="sxs-lookup"><span data-stu-id="58523-116">Password sync from Windows is not allowed.</span></span> <span data-ttu-id="58523-117">グローバル フラグを確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="58523-117">Check the global flags.%r</span></span><br /><br /> <span data-ttu-id="58523-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="58523-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="58523-119">クライアント ユーザー: %2</span><span class="sxs-lookup"><span data-stu-id="58523-119">Client User: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="58523-120">説明</span><span class="sxs-lookup"><span data-stu-id="58523-120">Explanation</span></span>  
 <span data-ttu-id="58523-121">この警告イベントは、パスワード同期が Windows によって要求され、どのグローバル フラグも設定されていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="58523-121">This Warning event indicates that password sync is requested by Windows and neither of the global flags is set.</span></span> <span data-ttu-id="58523-122">外部システムへのパスワードの送信を可能にする 2 つのフラグ: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL で、もう許可する SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB の外部システムからのパスワードの受信ができます。</span><span class="sxs-lookup"><span data-stu-id="58523-122">There are two flags, one that allows sending of password to external system: SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL and another that allows receiving of passwords from external systems SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="58523-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="58523-123">User Action</span></span>  
 <span data-ttu-id="58523-124">この警告を解決するには、次の操作を行います:</span><span class="sxs-lookup"><span data-stu-id="58523-124">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="58523-125">SSO 管理 MMC スナップインで、(システム 使用 &#124; 文字です。プロパティと &#124; 文字です。オプション) またはコマンド ライン ツール  `ssomanage –enable winsync/extsync` グローバル フラグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="58523-125">Use the SSO Admin MMC Snap-In, (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="58523-126">詳細</span><span class="sxs-lookup"><span data-stu-id="58523-126">More info</span></span>
  
-   <span data-ttu-id="58523-127">**エンタープライズ シングル サインオン フラグ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="58523-127">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
  
-   [<span data-ttu-id="58523-128">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="58523-128">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)