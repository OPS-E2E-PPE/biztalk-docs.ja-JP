---
title: シングル サインオン:イベント 10699 |Microsoft Docs
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
ms.openlocfilehash: f2cd62c4d952b9375b5d9255efc2f46add36dbb5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397297"
---
# <a name="single-sign-on-event-10699"></a><span data-ttu-id="f3e59-102">シングル サインオン:イベント 10699</span><span class="sxs-lookup"><span data-stu-id="f3e59-102">Single Sign-On: Event 10699</span></span>
## <a name="details"></a><span data-ttu-id="f3e59-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f3e59-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f3e59-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f3e59-104">Product Name</span></span>   |                                                                                                       <span data-ttu-id="f3e59-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f3e59-105">Enterprise Single Sign-On</span></span>                                                                                                       |
| <span data-ttu-id="f3e59-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f3e59-106">Product Version</span></span> |                                                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                       |
|    <span data-ttu-id="f3e59-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f3e59-107">Event ID</span></span>     |                                                                                                                 <span data-ttu-id="f3e59-108">10699</span><span class="sxs-lookup"><span data-stu-id="f3e59-108">10699</span></span>                                                                                                                 |
|  <span data-ttu-id="f3e59-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f3e59-109">Event Source</span></span>   |                                                                                                                <span data-ttu-id="f3e59-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f3e59-110">ENTSSO</span></span>                                                                                                                 |
|    <span data-ttu-id="f3e59-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f3e59-111">Component</span></span>    |                                                                                                                  <span data-ttu-id="f3e59-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="f3e59-112">N\A</span></span>                                                                                                                  |
|  <span data-ttu-id="f3e59-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f3e59-113">Symbolic Name</span></span>  |                                                                                           <span data-ttu-id="f3e59-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span><span class="sxs-lookup"><span data-stu-id="f3e59-114">SSO_INFO_EXTERNAL_PASSWORD_CHANGE_RECEIVED_REPLAY</span></span>                                                                                           |
|  <span data-ttu-id="f3e59-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f3e59-115">Message Text</span></span>   | <span data-ttu-id="f3e59-116">(再生 file).%r からアダプターから外部パスワード変更を受け取りました</span><span class="sxs-lookup"><span data-stu-id="f3e59-116">An external password change was received from an adapter (from replay file).%r</span></span><br /><br /> <span data-ttu-id="f3e59-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f3e59-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="f3e59-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="f3e59-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="f3e59-119">外部アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="f3e59-119">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="f3e59-120">クライアント ユーザー: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="f3e59-120">Client User: %4%r</span></span><br /><br /> <span data-ttu-id="f3e59-121">レコード数: %5</span><span class="sxs-lookup"><span data-stu-id="f3e59-121">Record Number: %5</span></span> |

## <a name="explanation"></a><span data-ttu-id="f3e59-122">説明</span><span class="sxs-lookup"><span data-stu-id="f3e59-122">Explanation</span></span>  
 <span data-ttu-id="f3e59-123">この情報イベントは、再生ファイルに記録されたアダプターから外部パスワード変更を受け取ったことを示します。</span><span class="sxs-lookup"><span data-stu-id="f3e59-123">This Information event indicates that an external password change was received from an adapter that was recorded to a replay file.</span></span> <span data-ttu-id="f3e59-124">SSO が再生ファイルから保存された外部パスワード変更を再生しています。</span><span class="sxs-lookup"><span data-stu-id="f3e59-124">SSO is replaying the stored external password changes from the replay file.</span></span>  

 <span data-ttu-id="f3e59-125">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f3e59-125">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="f3e59-126">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="f3e59-126">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f3e59-127">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f3e59-127">User Action</span></span>  

- <span data-ttu-id="f3e59-128">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f3e59-128">No user action is necessary.</span></span>  

  <span data-ttu-id="f3e59-129">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f3e59-129">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="f3e59-130">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f3e59-130">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="f3e59-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="f3e59-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
