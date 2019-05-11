---
title: シングル サインオン:イベント 10698 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f467934d-fef5-4962-a341-18f272d84108
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd2f52e4cabfac6309e33c3598921dc6001f006c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397300"
---
# <a name="single-sign-on-event-10698"></a><span data-ttu-id="c95ab-102">シングル サインオン:イベント 10698</span><span class="sxs-lookup"><span data-stu-id="c95ab-102">Single Sign-On: Event 10698</span></span>
## <a name="details"></a><span data-ttu-id="c95ab-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c95ab-103">Details</span></span>  

|                 |                                                                      |
|-----------------|----------------------------------------------------------------------|
|  <span data-ttu-id="c95ab-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c95ab-104">Product Name</span></span>   |                      <span data-ttu-id="c95ab-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c95ab-105">Enterprise Single Sign-On</span></span>                       |
| <span data-ttu-id="c95ab-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c95ab-106">Product Version</span></span> |      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="c95ab-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c95ab-107">Event ID</span></span>     |                                <span data-ttu-id="c95ab-108">10698</span><span class="sxs-lookup"><span data-stu-id="c95ab-108">10698</span></span>                                 |
|  <span data-ttu-id="c95ab-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c95ab-109">Event Source</span></span>   |                                <span data-ttu-id="c95ab-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c95ab-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="c95ab-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c95ab-111">Component</span></span>    |                                 <span data-ttu-id="c95ab-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="c95ab-112">N\A</span></span>                                  |
|  <span data-ttu-id="c95ab-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c95ab-113">Symbolic Name</span></span>  |                     <span data-ttu-id="c95ab-114">SSO_INFO_REPLAY_FILE_DELETED</span><span class="sxs-lookup"><span data-stu-id="c95ab-114">SSO_INFO_REPLAY_FILE_DELETED</span></span>                     |
|  <span data-ttu-id="c95ab-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c95ab-115">Message Text</span></span>   | <span data-ttu-id="c95ab-116">再生または進行状況ファイルが deleted.%r</span><span class="sxs-lookup"><span data-stu-id="c95ab-116">The replay or progress file was deleted.%r</span></span><br /><br /> <span data-ttu-id="c95ab-117">ファイル名: %1</span><span class="sxs-lookup"><span data-stu-id="c95ab-117">File Name: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="c95ab-118">説明</span><span class="sxs-lookup"><span data-stu-id="c95ab-118">Explanation</span></span>  
 <span data-ttu-id="c95ab-119">この情報イベントは、SSO が再生または進行ファイルを削除することを示します。</span><span class="sxs-lookup"><span data-stu-id="c95ab-119">This Information event indicates that SSO has deleted a replay and\or progress file.</span></span>  

 <span data-ttu-id="c95ab-120">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="c95ab-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="c95ab-121">進行状況ファイルがどこまで方法を示します SSO が SSO データベースと再生ファイルのケースで連絡先が再度失われたを読めるようにします。</span><span class="sxs-lookup"><span data-stu-id="c95ab-121">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c95ab-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c95ab-122">User Action</span></span>  

- <span data-ttu-id="c95ab-123">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c95ab-123">No user action is necessary.</span></span>  

  <span data-ttu-id="c95ab-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="c95ab-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="c95ab-125">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c95ab-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="c95ab-126">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="c95ab-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
