---
title: 'シングル サインオン: イベント 10707 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59629786-4f98-4861-aba3-153670bafc12
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81f4d484aa7a69f23cb66a921f1c630db9fcf790
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2018
---
# <a name="single-sign-on-event-10707"></a><span data-ttu-id="f077f-102">シングル サインオン: イベント 10707</span><span class="sxs-lookup"><span data-stu-id="f077f-102">Single Sign-On: Event 10707</span></span>
## <a name="details"></a><span data-ttu-id="f077f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f077f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f077f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f077f-104">Product Name</span></span>|<span data-ttu-id="f077f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f077f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="f077f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f077f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="f077f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f077f-107">Event ID</span></span>|<span data-ttu-id="f077f-108">10707</span><span class="sxs-lookup"><span data-stu-id="f077f-108">10707</span></span>|  
|<span data-ttu-id="f077f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f077f-109">Event Source</span></span>|<span data-ttu-id="f077f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f077f-110">ENTSSO</span></span>|  
|<span data-ttu-id="f077f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f077f-111">Component</span></span>|<span data-ttu-id="f077f-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f077f-112">N\A</span></span>|  
|<span data-ttu-id="f077f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f077f-113">Symbolic Name</span></span>|<span data-ttu-id="f077f-114">SSO_WARN_PS_NO_APP_SYNC</span><span class="sxs-lookup"><span data-stu-id="f077f-114">SSO_WARN_PS_NO_APP_SYNC</span></span>|  
|<span data-ttu-id="f077f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f077f-115">Message Text</span></span>|<span data-ttu-id="f077f-116">このアダプターのパスワード同期フラグは、パスワード同期を許可し、グローバル フラグと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="f077f-116">Password sync flags for this adapter must allow password sync and must match the global flags.</span></span> <span data-ttu-id="f077f-117">アダプター フラグとグローバル フラグを確認してください。%r</span><span class="sxs-lookup"><span data-stu-id="f077f-117">Check the adapter flags and the global flags.%r</span></span><br /><br /> <span data-ttu-id="f077f-118">アダプター: %1</span><span class="sxs-lookup"><span data-stu-id="f077f-118">Adapter: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f077f-119">説明</span><span class="sxs-lookup"><span data-stu-id="f077f-119">Explanation</span></span>  
 <span data-ttu-id="f077f-120">この警告イベントは、このアダプターのパスワード同期フラグが、パスワード同期を許可し、グローバル フラグと一致している必要があることを示します。</span><span class="sxs-lookup"><span data-stu-id="f077f-120">This Warning event indicates that password sync flags for this adapter must allow password sync and must match the global flags.</span></span>  
  
 <span data-ttu-id="f077f-121">パスワード同期アダプターのパスワード同期は、2 つのフラグによって制御されます。1 つは外部システムへのパスワードの送信を許可するフラグ (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) で、もう 1 つは外部システムからのパスワードの受信を許可するフラグ (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB) です。</span><span class="sxs-lookup"><span data-stu-id="f077f-121">Password sync for a password sync adapter is controlled by two flags, one allows sending of password to external systems (SSO_FLAG_FULL_SYNC_FROM_WINDOWS_TO_EXTERNAL) and another which allows receiving of passwords from external systems (SSO_FLAG_PARTIAL_SYNC_FROM_EXTERNAL_TO_DB).</span></span> <span data-ttu-id="f077f-122">パスワード同期を正常に実行するには、"グローバル フラグ" と特定のアダプター フラグの両方でこれらを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f077f-122">For successfull password sync these must be set for both the “global flags” and also for the specific adapter flags.</span></span> <span data-ttu-id="f077f-123">この警告イベントは、外部パスワード同期アダプターによってパスワード同期が要求され、これらのフラグのいずれかが、グローバル フラグおよびアダプター フラグの両方で設定されていない場合に発行されます。</span><span class="sxs-lookup"><span data-stu-id="f077f-123">This warning event is issued when password sync is requested by an external password sync adapter and neither of these flags is set for both the “global flags” and the adapter flags.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f077f-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f077f-124">User Action</span></span>  
 <span data-ttu-id="f077f-125">この警告を解決するには、次の操作を行います:</span><span class="sxs-lookup"><span data-stu-id="f077f-125">To resolve this warning, do the following:</span></span>  
  
-   <span data-ttu-id="f077f-126">SSO 管理 MMC スナップインを使用して (システム &#124; 文字です。プロパティと &#124; 文字です。オプション) またはコマンド ライン ツール  `ssomanage –enable winsync/extsync` グローバル フラグを有効にします。</span><span class="sxs-lookup"><span data-stu-id="f077f-126">Use the SSO Admin MMC Snap-In (System &#124; Properties &#124; Options) or command line tool  `ssomanage –enable winsync/extsync` to enable the global flags.</span></span>  
  
## <a name="more-info"></a><span data-ttu-id="f077f-127">詳細</span><span class="sxs-lookup"><span data-stu-id="f077f-127">More info</span></span>
  
-   <span data-ttu-id="f077f-128">**エンタープライズ シングル サインオン フラグ** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f077f-128">**Enterprise Single Sign-On Flags** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>  
  
-   [<span data-ttu-id="f077f-129">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="f077f-129">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)