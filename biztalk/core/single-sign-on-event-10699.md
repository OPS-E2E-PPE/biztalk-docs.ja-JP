---
title: 'シングル サインオン: イベント 10699 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff26533-e4d7-47b5-92d5-bd8c72fab89a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b6ceb4ffe1e25a3828f406b881d4070b74a8d9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271706"
---
# <a name="single-sign-on-event-10699"></a><span data-ttu-id="09cfe-102">シングル サインオン: イベント 10699</span><span class="sxs-lookup"><span data-stu-id="09cfe-102">Single Sign-On: Event 10699</span></span>
## <a name="details"></a><span data-ttu-id="09cfe-103">詳細</span><span class="sxs-lookup"><span data-stu-id="09cfe-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="09cfe-104">製品名</span><span class="sxs-lookup"><span data-stu-id="09cfe-104">Product Name</span></span>|<span data-ttu-id="09cfe-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="09cfe-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="09cfe-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="09cfe-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="09cfe-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="09cfe-107">Event ID</span></span>|<span data-ttu-id="09cfe-108">10699</span><span class="sxs-lookup"><span data-stu-id="09cfe-108">10699</span></span>|  
|<span data-ttu-id="09cfe-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="09cfe-109">Event Source</span></span>|<span data-ttu-id="09cfe-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="09cfe-110">ENTSSO</span></span>|  
|<span data-ttu-id="09cfe-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="09cfe-111">Component</span></span>|<span data-ttu-id="09cfe-112">N\A</span><span class="sxs-lookup"><span data-stu-id="09cfe-112">N\A</span></span>|  
|<span data-ttu-id="09cfe-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="09cfe-113">Symbolic Name</span></span>|<span data-ttu-id="09cfe-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span><span class="sxs-lookup"><span data-stu-id="09cfe-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span></span>|  
|<span data-ttu-id="09cfe-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="09cfe-115">Message Text</span></span>|<span data-ttu-id="09cfe-116">外部パスワード変更をアダプターから受け取りました (再生ファイルから)。%r</span><span class="sxs-lookup"><span data-stu-id="09cfe-116">An external password change was received from an adapter (from replay file).%r</span></span><br /><br /> <span data-ttu-id="09cfe-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="09cfe-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="09cfe-118">アダプター: %2 %r</span><span class="sxs-lookup"><span data-stu-id="09cfe-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="09cfe-119">外部アカウント: %3 %r</span><span class="sxs-lookup"><span data-stu-id="09cfe-119">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="09cfe-120">クライアント ユーザー: %4 %r</span><span class="sxs-lookup"><span data-stu-id="09cfe-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="09cfe-121">レコード番号: %5</span><span class="sxs-lookup"><span data-stu-id="09cfe-121">Record Number: %5</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="09cfe-122">説明</span><span class="sxs-lookup"><span data-stu-id="09cfe-122">Explanation</span></span>  
 <span data-ttu-id="09cfe-123">この情報イベントは、再生ファイルに記録されたアダプターから外部パスワード変更を受け取ったことを示します。</span><span class="sxs-lookup"><span data-stu-id="09cfe-123">This Information event indicates that an external password change was received from an adapter that was recorded to a replay file.</span></span> <span data-ttu-id="09cfe-124">SSO は、保存されていた外部パスワード変更を再生ファイルから再生しています。</span><span class="sxs-lookup"><span data-stu-id="09cfe-124">SSO is replaying the stored external password changes from the replay file.</span></span>  
  
 <span data-ttu-id="09cfe-125">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="09cfe-125">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="09cfe-126">進行ファイルでは、SSO データベースとの接続が再度失われた場合に SSO で再生ファイルをどこまで読み取ることができるかを示します。</span><span class="sxs-lookup"><span data-stu-id="09cfe-126">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="09cfe-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="09cfe-127">User Action</span></span>  
  
-   <span data-ttu-id="09cfe-128">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="09cfe-128">No user action is necessary.</span></span>  
  
 <span data-ttu-id="09cfe-129">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="09cfe-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="09cfe-130">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="09cfe-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="09cfe-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="09cfe-131">Password Synchronization</span></span>](../core/password-synchronization2.md)