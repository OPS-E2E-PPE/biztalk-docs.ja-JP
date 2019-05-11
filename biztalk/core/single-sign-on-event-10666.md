---
title: シングル サインオン:イベント 10666 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 103947bb-e843-4427-a28a-1cceec90e2ae
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 921f11f422e4707d81a9387cd9606c3dfd3f337d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397545"
---
# <a name="single-sign-on-event-10666"></a><span data-ttu-id="00118-102">シングル サインオン:イベント 10666</span><span class="sxs-lookup"><span data-stu-id="00118-102">Single Sign-On: Event 10666</span></span>
## <a name="details"></a><span data-ttu-id="00118-103">詳細</span><span class="sxs-lookup"><span data-stu-id="00118-103">Details</span></span>  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="00118-104">製品名</span><span class="sxs-lookup"><span data-stu-id="00118-104">Product Name</span></span>   |                                                                         <span data-ttu-id="00118-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="00118-105">Enterprise Single Sign-On</span></span>                                                                          |
| <span data-ttu-id="00118-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="00118-106">Product Version</span></span> |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    <span data-ttu-id="00118-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="00118-107">Event ID</span></span>     |                                                                                   <span data-ttu-id="00118-108">10666</span><span class="sxs-lookup"><span data-stu-id="00118-108">10666</span></span>                                                                                    |
|  <span data-ttu-id="00118-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="00118-109">Event Source</span></span>   |                                                                                   <span data-ttu-id="00118-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="00118-110">ENTSSO</span></span>                                                                                   |
|    <span data-ttu-id="00118-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="00118-111">Component</span></span>    |                                                                                    <span data-ttu-id="00118-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="00118-112">N\A</span></span>                                                                                     |
|  <span data-ttu-id="00118-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="00118-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="00118-114">SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE</span><span class="sxs-lookup"><span data-stu-id="00118-114">SSO_INFO_DAMPED_EXTERNAL_PASSWORD_CHANGE</span></span>                                                                  |
|  <span data-ttu-id="00118-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="00118-115">Message Text</span></span>   | <span data-ttu-id="00118-116">外部パスワード変更は抑制されました (重複および discarded).%r として検出します。</span><span class="sxs-lookup"><span data-stu-id="00118-116">An external password change was damped (detected as a duplicate and discarded).%r</span></span><br /><br /> <span data-ttu-id="00118-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="00118-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="00118-118">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="00118-118">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="00118-119">外部アカウント: %3</span><span class="sxs-lookup"><span data-stu-id="00118-119">External Account: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="00118-120">説明</span><span class="sxs-lookup"><span data-stu-id="00118-120">Explanation</span></span>  
 <span data-ttu-id="00118-121">この情報イベントは、外部パスワード変更が重複するいると判断して、破棄されることを示します。</span><span class="sxs-lookup"><span data-stu-id="00118-121">This Information event indicates that an external password change was determined to be a duplicate and discarded.</span></span>  

## <a name="user-action"></a><span data-ttu-id="00118-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="00118-122">User Action</span></span>  

- <span data-ttu-id="00118-123">ユーザー操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="00118-123">No user action is necessary.</span></span>  

  <span data-ttu-id="00118-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="00118-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="00118-125">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="00118-125">Password Synchronization</span></span>](../core/password-synchronization2.md)
