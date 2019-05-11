---
title: シングル サインオン:イベント 10533 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 31abd828-5f10-43f7-b99e-f3195250130c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ce83b8d2c7ff6973900088dcb0c0028e31f0e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262318"
---
# <a name="single-sign-on-event-10533"></a><span data-ttu-id="bc6da-102">シングル サインオン:イベント 10533</span><span class="sxs-lookup"><span data-stu-id="bc6da-102">Single Sign-On: Event 10533</span></span>
## <a name="details"></a><span data-ttu-id="bc6da-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bc6da-103">Details</span></span>  

|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bc6da-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bc6da-104">Product Name</span></span>   |                                             <span data-ttu-id="bc6da-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bc6da-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="bc6da-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bc6da-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="bc6da-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bc6da-107">Event ID</span></span>     |                                                       <span data-ttu-id="bc6da-108">10533</span><span class="sxs-lookup"><span data-stu-id="bc6da-108">10533</span></span>                                                       |
|  <span data-ttu-id="bc6da-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bc6da-109">Event Source</span></span>   |                                                      <span data-ttu-id="bc6da-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bc6da-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="bc6da-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bc6da-111">Component</span></span>    |                                                        <span data-ttu-id="bc6da-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="bc6da-112">N\A</span></span>                                                        |
|  <span data-ttu-id="bc6da-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bc6da-113">Symbolic Name</span></span>  |                                            <span data-ttu-id="bc6da-114">SSO_INFO_GOT_CURRENT_SECRET</span><span class="sxs-lookup"><span data-stu-id="bc6da-114">SSO_INFO_GOT_CURRENT_SECRET</span></span>                                            |
|  <span data-ttu-id="bc6da-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bc6da-115">Message Text</span></span>   | <span data-ttu-id="bc6da-116">マスター シークレット server.%r から現在のシークレットを取得しました</span><span class="sxs-lookup"><span data-stu-id="bc6da-116">Got the current secret from the master secret server.%r</span></span><br /><br /> <span data-ttu-id="bc6da-117">シークレット サーバー名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="bc6da-117">Secret Server Name: %1%r</span></span><br /><br /> <span data-ttu-id="bc6da-118">MSID: %2</span><span class="sxs-lookup"><span data-stu-id="bc6da-118">MSID: %2</span></span> |

## <a name="explanation"></a><span data-ttu-id="bc6da-119">説明</span><span class="sxs-lookup"><span data-stu-id="bc6da-119">Explanation</span></span>  
 <span data-ttu-id="bc6da-120">この情報イベントは、SSO に現在のマスター シークレットことを示します。</span><span class="sxs-lookup"><span data-stu-id="bc6da-120">This Information event indicates that SSO has the current master secret.</span></span>  

## <a name="user-action"></a><span data-ttu-id="bc6da-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bc6da-121">User Action</span></span>  

- <span data-ttu-id="bc6da-122">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="bc6da-122">No user action is necessary.</span></span>  

  <span data-ttu-id="bc6da-123">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="bc6da-123">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="bc6da-124">マスター シークレットを生成する方法</span><span class="sxs-lookup"><span data-stu-id="bc6da-124">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  

- [<span data-ttu-id="bc6da-125">マスター シークレットの管理</span><span class="sxs-lookup"><span data-stu-id="bc6da-125">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)
