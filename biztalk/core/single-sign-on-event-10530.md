---
title: シングル サインオン:イベント 10530 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4bb37305-26fe-46a7-958d-3ed7f6876a7b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccdea8c120bba407f22f24f28afd425768ff24b3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262396"
---
# <a name="single-sign-on-event-10530"></a><span data-ttu-id="cfd2b-102">シングル サインオン:イベント 10530</span><span class="sxs-lookup"><span data-stu-id="cfd2b-102">Single Sign-On: Event 10530</span></span>
## <a name="details"></a><span data-ttu-id="cfd2b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cfd2b-103">Details</span></span>  

|                 |                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cfd2b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cfd2b-104">Product Name</span></span>   |                                             <span data-ttu-id="cfd2b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cfd2b-105">Enterprise Single Sign-On</span></span>                                              |
| <span data-ttu-id="cfd2b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cfd2b-106">Product Version</span></span> |                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="cfd2b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cfd2b-107">Event ID</span></span>     |                                                       <span data-ttu-id="cfd2b-108">10530</span><span class="sxs-lookup"><span data-stu-id="cfd2b-108">10530</span></span>                                                        |
|  <span data-ttu-id="cfd2b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cfd2b-109">Event Source</span></span>   |                                                       <span data-ttu-id="cfd2b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cfd2b-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="cfd2b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cfd2b-111">Component</span></span>    |                                                        <span data-ttu-id="cfd2b-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="cfd2b-112">N\A</span></span>                                                         |
|  <span data-ttu-id="cfd2b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cfd2b-113">Symbolic Name</span></span>  |                                            <span data-ttu-id="cfd2b-114">SSO_INFO_GOT_PREVIOUS_SECRET</span><span class="sxs-lookup"><span data-stu-id="cfd2b-114">SSO_INFO_GOT_PREVIOUS_SECRET</span></span>                                            |
|  <span data-ttu-id="cfd2b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cfd2b-115">Message Text</span></span>   | <span data-ttu-id="cfd2b-116">マスター シークレット server.%r から以前のシークレットを取得しました</span><span class="sxs-lookup"><span data-stu-id="cfd2b-116">Got the previous secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="cfd2b-117">シークレット サーバー名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="cfd2b-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="cfd2b-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="cfd2b-118">MSID: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="cfd2b-119">説明</span><span class="sxs-lookup"><span data-stu-id="cfd2b-119">Explanation</span></span>  
 <span data-ttu-id="cfd2b-120">この情報イベントは、SSO が以前のマスター シークレットを持つことを示します。</span><span class="sxs-lookup"><span data-stu-id="cfd2b-120">This Information event indicates that SSO has the previous master secret.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cfd2b-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cfd2b-121">User Action</span></span>  

- <span data-ttu-id="cfd2b-122">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cfd2b-122">No user action is necessary.</span></span>  

  <span data-ttu-id="cfd2b-123">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="cfd2b-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="cfd2b-124">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="cfd2b-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="cfd2b-125">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="cfd2b-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
