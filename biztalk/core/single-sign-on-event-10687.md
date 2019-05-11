---
title: シングル サインオン:イベント 10687 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b3fe2c-a7ba-47e1-a753-4eaa64b01a60
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77412a149c79e508c03b245cba04a76c87542936
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397390"
---
# <a name="single-sign-on-event-10687"></a><span data-ttu-id="f7378-102">シングル サインオン:イベント 10687</span><span class="sxs-lookup"><span data-stu-id="f7378-102">Single Sign-On: Event 10687</span></span>
## <a name="details"></a><span data-ttu-id="f7378-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f7378-103">Details</span></span>  

|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f7378-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f7378-104">Product Name</span></span>   |                                               <span data-ttu-id="f7378-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f7378-105">Enterprise Single Sign-On</span></span>                                               |
| <span data-ttu-id="f7378-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f7378-106">Product Version</span></span> |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    <span data-ttu-id="f7378-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f7378-107">Event ID</span></span>     |                                                         <span data-ttu-id="f7378-108">10687</span><span class="sxs-lookup"><span data-stu-id="f7378-108">10687</span></span>                                                         |
|  <span data-ttu-id="f7378-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f7378-109">Event Source</span></span>   |                                                        <span data-ttu-id="f7378-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f7378-110">ENTSSO</span></span>                                                         |
|    <span data-ttu-id="f7378-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f7378-111">Component</span></span>    |                                                          <span data-ttu-id="f7378-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="f7378-112">N\A</span></span>                                                          |
|  <span data-ttu-id="f7378-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f7378-113">Symbolic Name</span></span>  |                                               <span data-ttu-id="f7378-114">SSO_INFO_REPLAY_COMPLETE</span><span class="sxs-lookup"><span data-stu-id="f7378-114">SSO_INFO_REPLAY_COMPLETE</span></span>                                                |
|  <span data-ttu-id="f7378-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f7378-115">Message Text</span></span>   | <span data-ttu-id="f7378-116">再生の保存された外部パスワード変更 completed.%r</span><span class="sxs-lookup"><span data-stu-id="f7378-116">Replay of stored external password changes completed.%r</span></span><br /><br /> <span data-ttu-id="f7378-117">再生ファイル: % 1 %r</span><span class="sxs-lookup"><span data-stu-id="f7378-117">Replay File: %1%r</span></span><br /><br /> <span data-ttu-id="f7378-118">追加データ: %2</span><span class="sxs-lookup"><span data-stu-id="f7378-118">Additional Data: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="f7378-119">説明</span><span class="sxs-lookup"><span data-stu-id="f7378-119">Explanation</span></span>  
 <span data-ttu-id="f7378-120">この情報イベントは、SSO の保存された外部パスワード変更ファイルの再生が完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="f7378-120">This Information event indicates that SSO has completed replaying the stored external password changes file.</span></span> <span data-ttu-id="f7378-121">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f7378-121">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f7378-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f7378-122">User Action</span></span>  

- <span data-ttu-id="f7378-123">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f7378-123">No user action is necessary.</span></span>  

  <span data-ttu-id="f7378-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f7378-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="f7378-125">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f7378-125">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="f7378-126">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="f7378-126">Password Synchronization</span></span>](../core/password-synchronization2.md)
