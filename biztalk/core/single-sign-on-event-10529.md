---
title: シングル サインオン:イベント 10529 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75ed70e0-8458-4736-883f-a4536f094dc0
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 204e5d2ff2093b5980176d1696fd9bd45b892023
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262428"
---
# <a name="single-sign-on-event-10529"></a><span data-ttu-id="653d9-102">シングル サインオン:イベント 10529</span><span class="sxs-lookup"><span data-stu-id="653d9-102">Single Sign-On: Event 10529</span></span>
## <a name="details"></a><span data-ttu-id="653d9-103">詳細</span><span class="sxs-lookup"><span data-stu-id="653d9-103">Details</span></span>  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="653d9-104">製品名</span><span class="sxs-lookup"><span data-stu-id="653d9-104">Product Name</span></span>   |                                             <span data-ttu-id="653d9-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="653d9-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="653d9-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="653d9-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="653d9-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="653d9-107">Event ID</span></span>     |                                                       <span data-ttu-id="653d9-108">10529</span><span class="sxs-lookup"><span data-stu-id="653d9-108">10529</span></span>                                                       |
|  <span data-ttu-id="653d9-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="653d9-109">Event Source</span></span>   |                                                      <span data-ttu-id="653d9-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="653d9-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="653d9-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="653d9-111">Component</span></span>    |                                                        <span data-ttu-id="653d9-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="653d9-112">N\A</span></span>                                                        |
|  <span data-ttu-id="653d9-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="653d9-113">Symbolic Name</span></span>  |                                            <span data-ttu-id="653d9-114">SSO_INFO_GOT_CURRENT_SECRET</span><span class="sxs-lookup"><span data-stu-id="653d9-114">SSO_INFO_GOT_CURRENT_SECRET</span></span>                                            |
|  <span data-ttu-id="653d9-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="653d9-115">Message Text</span></span>   | <span data-ttu-id="653d9-116">マスター シークレット server.%r から現在のシークレットを取得しました</span><span class="sxs-lookup"><span data-stu-id="653d9-116">Got the current secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="653d9-117">シークレット サーバー名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="653d9-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="653d9-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="653d9-118">MSID: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="653d9-119">説明</span><span class="sxs-lookup"><span data-stu-id="653d9-119">Explanation</span></span>  
 <span data-ttu-id="653d9-120">この情報イベントは、SSO がマスター シークレット サーバーから要求されたマスター シークレットを示します。</span><span class="sxs-lookup"><span data-stu-id="653d9-120">This Information event indicates that SSO has the requested master secret from the master secret server.</span></span>  

## <a name="user-action"></a><span data-ttu-id="653d9-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="653d9-121">User Action</span></span>  

- <span data-ttu-id="653d9-122">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="653d9-122">No user action is necessary.</span></span>  

  <span data-ttu-id="653d9-123">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="653d9-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="653d9-124">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="653d9-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="653d9-125">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="653d9-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
