---
title: 'シングル サインオン: イベント 10683 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 83cd1b96-cd79-4ddc-952b-94a7de216666
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c383a02400523686f00011c5eb6f71c9542ec5e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271546"
---
# <a name="single-sign-on-event-10683"></a><span data-ttu-id="cfaa7-102">シングル サインオン: イベント 10683</span><span class="sxs-lookup"><span data-stu-id="cfaa7-102">Single Sign-On: Event 10683</span></span>
## <a name="details"></a><span data-ttu-id="cfaa7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cfaa7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cfaa7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cfaa7-104">Product Name</span></span>|<span data-ttu-id="cfaa7-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cfaa7-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="cfaa7-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cfaa7-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="cfaa7-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cfaa7-107">Event ID</span></span>|<span data-ttu-id="cfaa7-108">10683</span><span class="sxs-lookup"><span data-stu-id="cfaa7-108">10683</span></span>|  
|<span data-ttu-id="cfaa7-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cfaa7-109">Event Source</span></span>|<span data-ttu-id="cfaa7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cfaa7-110">ENTSSO</span></span>|  
|<span data-ttu-id="cfaa7-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cfaa7-111">Component</span></span>|<span data-ttu-id="cfaa7-112">N\A</span><span class="sxs-lookup"><span data-stu-id="cfaa7-112">N\A</span></span>|  
|<span data-ttu-id="cfaa7-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cfaa7-113">Symbolic Name</span></span>|<span data-ttu-id="cfaa7-114">SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD</span><span class="sxs-lookup"><span data-stu-id="cfaa7-114">SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD</span></span>|  
|<span data-ttu-id="cfaa7-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cfaa7-115">Message Text</span></span>|<span data-ttu-id="cfaa7-116">すぎたために、再生ファイルは削除されました old.%r</span><span class="sxs-lookup"><span data-stu-id="cfaa7-116">A replay file was deleted because it was too old.%r</span></span><br /><span data-ttu-id="cfaa7-117">再生ファイル: %1</span><span class="sxs-lookup"><span data-stu-id="cfaa7-117">Replay File: %1</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cfaa7-118">説明</span><span class="sxs-lookup"><span data-stu-id="cfaa7-118">Explanation</span></span>  
 <span data-ttu-id="cfaa7-119">この警告イベントは、再生ファイルが古すぎたため、削除されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="cfaa7-119">This Warning event indicates that the replay file was deleted because it was too old.</span></span> <span data-ttu-id="cfaa7-120">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfaa7-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="cfaa7-121">この場合、パスワード変更は一時的な暗号化ファイル保存され、再び使用可能になったときに、SSO データベースに対して再生されます。</span><span class="sxs-lookup"><span data-stu-id="cfaa7-121">In this case the password changes are stored in a temporary encrypted file and are replayed back to the SSO database when it again becomes available.</span></span> <span data-ttu-id="cfaa7-122">SSO データベースに対してファイルを再生するときに、古すぎるファイルが検出された場合、そのファイルは破棄されます。</span><span class="sxs-lookup"><span data-stu-id="cfaa7-122">When it is time to replay the files back to the SSO database, if a file is detected that is too old, it is discarded.</span></span> <span data-ttu-id="cfaa7-123">すべての古いパスワード変更は、SSO パスワード同期システムによって破棄されます。`password sync age`パラメーターは、パスワードの最大有効期間の変更要求およびコマンド ライン ツールを使用して制御できるかを決定**ssoconfig-syncage**または SSO 管理 MMC です。</span><span class="sxs-lookup"><span data-stu-id="cfaa7-123">All old password changes are discarded by the SSO password sync system; the `password sync age` parameter determines the maximum age for password change requests and that can be controlled using the command line tools **ssoconfig –syncAge** or the SSO Admin MMC.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cfaa7-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cfaa7-124">User Action</span></span>  
  
-   <span data-ttu-id="cfaa7-125">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cfaa7-125">No user action is necessary.</span></span>  
  
 <span data-ttu-id="cfaa7-126">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="cfaa7-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="cfaa7-127">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="cfaa7-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="cfaa7-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="cfaa7-128">Password Synchronization</span></span>](../core/password-synchronization2.md)