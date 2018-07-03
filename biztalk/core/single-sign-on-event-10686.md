---
title: 'シングル サインオン: イベント 10686 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3e71f2a-e51d-4736-b06a-117142d30dae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 363ec7268ca3088a4d7658bbf4497099c810f92f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987993"
---
# <a name="single-sign-on-event-10686"></a><span data-ttu-id="6dab2-102">シングル サインオン: イベント 10686</span><span class="sxs-lookup"><span data-stu-id="6dab2-102">Single Sign-On: Event 10686</span></span>
## <a name="details"></a><span data-ttu-id="6dab2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6dab2-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="6dab2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6dab2-104">Product Name</span></span>   |                         <span data-ttu-id="6dab2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="6dab2-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="6dab2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6dab2-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="6dab2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6dab2-107">Event ID</span></span>     |                                   <span data-ttu-id="6dab2-108">10686</span><span class="sxs-lookup"><span data-stu-id="6dab2-108">10686</span></span>                                   |
|  <span data-ttu-id="6dab2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6dab2-109">Event Source</span></span>   |                                  <span data-ttu-id="6dab2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="6dab2-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="6dab2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6dab2-111">Component</span></span>    |                                    <span data-ttu-id="6dab2-112">N\A</span><span class="sxs-lookup"><span data-stu-id="6dab2-112">N\A</span></span>                                    |
|  <span data-ttu-id="6dab2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6dab2-113">Symbolic Name</span></span>  |                          <span data-ttu-id="6dab2-114">SSO_INFO_REPLAY_STARTED</span><span class="sxs-lookup"><span data-stu-id="6dab2-114">SSO_INFO_REPLAY_STARTED</span></span>                          |
|  <span data-ttu-id="6dab2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6dab2-115">Message Text</span></span>   | <span data-ttu-id="6dab2-116">保存された外部パスワード変更を再生しています。%r</span><span class="sxs-lookup"><span data-stu-id="6dab2-116">Replaying stored external password changes.%r</span></span><br /><br /> <span data-ttu-id="6dab2-117">再生ファイル: %1</span><span class="sxs-lookup"><span data-stu-id="6dab2-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="6dab2-118">説明</span><span class="sxs-lookup"><span data-stu-id="6dab2-118">Explanation</span></span>  
 <span data-ttu-id="6dab2-119">この情報イベントは、SSO が保存された外部パスワード変更ファイルを再生していることを示します。</span><span class="sxs-lookup"><span data-stu-id="6dab2-119">This Information event indicates that SSO is replaying the stored external password changes file.</span></span> <span data-ttu-id="6dab2-120">ENTSSO サーバーから SSO データベースに接続できない場合、パスワード同期で再生ファイルが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6dab2-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="6dab2-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6dab2-121">User Action</span></span>  

- <span data-ttu-id="6dab2-122">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6dab2-122">No user action is necessary.</span></span>  

  <span data-ttu-id="6dab2-123">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="6dab2-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="6dab2-124">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="6dab2-124">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="6dab2-125">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="6dab2-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
