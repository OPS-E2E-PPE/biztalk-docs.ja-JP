---
title: シングル サインオン:イベント 10686 |Microsoft Docs
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
ms.openlocfilehash: 90306488cb77f40458cf0fccacae9050807a2e3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397385"
---
# <a name="single-sign-on-event-10686"></a><span data-ttu-id="f693a-102">シングル サインオン:イベント 10686</span><span class="sxs-lookup"><span data-stu-id="f693a-102">Single Sign-On: Event 10686</span></span>
## <a name="details"></a><span data-ttu-id="f693a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="f693a-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="f693a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="f693a-104">Product Name</span></span>   |                         <span data-ttu-id="f693a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="f693a-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="f693a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="f693a-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="f693a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="f693a-107">Event ID</span></span>     |                                   <span data-ttu-id="f693a-108">10686</span><span class="sxs-lookup"><span data-stu-id="f693a-108">10686</span></span>                                   |
|  <span data-ttu-id="f693a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="f693a-109">Event Source</span></span>   |                                  <span data-ttu-id="f693a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f693a-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="f693a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f693a-111">Component</span></span>    |                                    <span data-ttu-id="f693a-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="f693a-112">N\A</span></span>                                    |
|  <span data-ttu-id="f693a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="f693a-113">Symbolic Name</span></span>  |                          <span data-ttu-id="f693a-114">SSO_INFO_REPLAY_STARTED</span><span class="sxs-lookup"><span data-stu-id="f693a-114">SSO_INFO_REPLAY_STARTED</span></span>                          |
|  <span data-ttu-id="f693a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="f693a-115">Message Text</span></span>   | <span data-ttu-id="f693a-116">格納されている外部パスワード changes.%r を再生します。</span><span class="sxs-lookup"><span data-stu-id="f693a-116">Replaying stored external password changes.%r</span></span><br /><br /> <span data-ttu-id="f693a-117">再生ファイル: %1</span><span class="sxs-lookup"><span data-stu-id="f693a-117">Replay File: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="f693a-118">説明</span><span class="sxs-lookup"><span data-stu-id="f693a-118">Explanation</span></span>  
 <span data-ttu-id="f693a-119">この情報イベントは、SSO が保存された外部パスワード変更ファイルを再生することを示します。</span><span class="sxs-lookup"><span data-stu-id="f693a-119">This Information event indicates that SSO is replaying the stored external password changes file.</span></span> <span data-ttu-id="f693a-120">再生ファイルは、ENTSSO サーバーが SSO データベースに接続できない場合、パスワード同期で使用されます。</span><span class="sxs-lookup"><span data-stu-id="f693a-120">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f693a-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="f693a-121">User Action</span></span>  

- <span data-ttu-id="f693a-122">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f693a-122">No user action is necessary.</span></span>  

  <span data-ttu-id="f693a-123">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="f693a-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="f693a-124">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="f693a-124">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="f693a-125">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="f693a-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
