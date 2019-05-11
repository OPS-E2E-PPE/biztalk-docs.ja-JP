---
title: シングル サインオン:イベント 10683 |Microsoft Docs
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
ms.openlocfilehash: c280011ab792c87d3062ec99954734845eea63f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397445"
---
# <a name="single-sign-on-event-10683"></a><span data-ttu-id="1ad38-102">シングル サインオン:イベント 10683</span><span class="sxs-lookup"><span data-stu-id="1ad38-102">Single Sign-On: Event 10683</span></span>
## <a name="details"></a><span data-ttu-id="1ad38-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1ad38-103">Details</span></span>  

|                 |                                                                          |
|-----------------|--------------------------------------------------------------------------|
|  <span data-ttu-id="1ad38-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1ad38-104">Product Name</span></span>   |                        <span data-ttu-id="1ad38-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1ad38-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="1ad38-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1ad38-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]        |
|    <span data-ttu-id="1ad38-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1ad38-107">Event ID</span></span>     |                                  <span data-ttu-id="1ad38-108">10683</span><span class="sxs-lookup"><span data-stu-id="1ad38-108">10683</span></span>                                   |
|  <span data-ttu-id="1ad38-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1ad38-109">Event Source</span></span>   |                                  <span data-ttu-id="1ad38-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1ad38-110">ENTSSO</span></span>                                  |
|    <span data-ttu-id="1ad38-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1ad38-111">Component</span></span>    |                                   <span data-ttu-id="1ad38-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="1ad38-112">N\A</span></span>                                    |
|  <span data-ttu-id="1ad38-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1ad38-113">Symbolic Name</span></span>  |                   <span data-ttu-id="1ad38-114">SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD</span><span class="sxs-lookup"><span data-stu-id="1ad38-114">SSO_WARN_REPLAY_FILE_DELETED_TOO_OLD</span></span>                   |
|  <span data-ttu-id="1ad38-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1ad38-115">Message Text</span></span>   | <span data-ttu-id="1ad38-116">すぎたため、再生ファイルが削除された old.%r</span><span class="sxs-lookup"><span data-stu-id="1ad38-116">A replay file was deleted because it was too old.%r</span></span><br /><span data-ttu-id="1ad38-117">再生ファイル: %1</span><span class="sxs-lookup"><span data-stu-id="1ad38-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="1ad38-118">説明</span><span class="sxs-lookup"><span data-stu-id="1ad38-118">Explanation</span></span>  
 <span data-ttu-id="1ad38-119">この警告イベントは、再生ファイルが古すぎるため、削除されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="1ad38-119">This Warning event indicates that the replay file was deleted because it was too old.</span></span> <span data-ttu-id="1ad38-120">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ad38-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="1ad38-121">ここで、パスワードの変更は一時的な暗号化ファイルに格納され、再び使用可能になったときに、SSO データベースに再生されます。</span><span class="sxs-lookup"><span data-stu-id="1ad38-121">In this case the password changes are stored in a temporary encrypted file and are replayed back to the SSO database when it again becomes available.</span></span> <span data-ttu-id="1ad38-122">ですが古すぎるファイルが検出された場合、SSO データベースにファイルを再生するときに、破棄されます。</span><span class="sxs-lookup"><span data-stu-id="1ad38-122">When it is time to replay the files back to the SSO database, if a file is detected that is too old, it is discarded.</span></span> <span data-ttu-id="1ad38-123">すべての古いパスワードの変更は、SSO パスワード同期システムによって破棄されます。`password sync age`パスワードの最大有効期間の変更要求およびコマンド ライン ツールを使用して制御できるパラメーターを決定します**ssoconfig-syncage**または SSO 管理 MMC。</span><span class="sxs-lookup"><span data-stu-id="1ad38-123">All old password changes are discarded by the SSO password sync system; the `password sync age` parameter determines the maximum age for password change requests and that can be controlled using the command line tools **ssoconfig –syncAge** or the SSO Admin MMC.</span></span>  

## <a name="user-action"></a><span data-ttu-id="1ad38-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1ad38-124">User Action</span></span>  

- <span data-ttu-id="1ad38-125">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="1ad38-125">No user action is necessary.</span></span>  

  <span data-ttu-id="1ad38-126">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="1ad38-126">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="1ad38-127">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="1ad38-127">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="1ad38-128">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="1ad38-128">Password Synchronization</span></span>](../core/password-synchronization2.md)
