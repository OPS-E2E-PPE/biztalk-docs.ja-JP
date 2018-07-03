---
title: 'シングル サインオン: イベント 10528 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d96c1645-70f4-4d15-a0d7-0ae37669ad2a
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2e91944de7399f8bee3e03f3facdb91263d2761
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974827"
---
# <a name="single-sign-on-event-10528"></a><span data-ttu-id="cdb74-102">シングル サインオン: イベント 10528</span><span class="sxs-lookup"><span data-stu-id="cdb74-102">Single Sign-On: Event 10528</span></span>
## <a name="details"></a><span data-ttu-id="cdb74-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cdb74-103">Details</span></span>  

|                 |                                                                                                                                                                            |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="cdb74-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cdb74-104">Product Name</span></span>   |                                                                         <span data-ttu-id="cdb74-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="cdb74-105">Enterprise Single Sign-On</span></span>                                                                          |
| <span data-ttu-id="cdb74-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cdb74-106">Product Version</span></span> |                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                         |
|    <span data-ttu-id="cdb74-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cdb74-107">Event ID</span></span>     |                                                                                   <span data-ttu-id="cdb74-108">10528</span><span class="sxs-lookup"><span data-stu-id="cdb74-108">10528</span></span>                                                                                    |
|  <span data-ttu-id="cdb74-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cdb74-109">Event Source</span></span>   |                                                                                   <span data-ttu-id="cdb74-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="cdb74-110">ENTSSO</span></span>                                                                                   |
|    <span data-ttu-id="cdb74-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cdb74-111">Component</span></span>    |                                                                                    <span data-ttu-id="cdb74-112">N\A</span><span class="sxs-lookup"><span data-stu-id="cdb74-112">N\A</span></span>                                                                                     |
|  <span data-ttu-id="cdb74-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cdb74-113">Symbolic Name</span></span>  |                                                                           <span data-ttu-id="cdb74-114">SSO_INFO_REENCRYPT_OK</span><span class="sxs-lookup"><span data-stu-id="cdb74-114">SSO_INFO_REENCRYPT_OK</span></span>                                                                            |
|  <span data-ttu-id="cdb74-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cdb74-115">Message Text</span></span>   | <span data-ttu-id="cdb74-116">SSO データベースの再暗号化が正常に完了しました。%r</span><span class="sxs-lookup"><span data-stu-id="cdb74-116">SSO database re-encryption has completed successfully.%r</span></span><br /><br /> <span data-ttu-id="cdb74-117">再暗号化された資格情報の数: 1 %r</span><span class="sxs-lookup"><span data-stu-id="cdb74-117">Number of Credentials re-encrypted: %1%r</span></span><br /><br /> <span data-ttu-id="cdb74-118">現在の MSID: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="cdb74-118">Current MSID: %2%r</span></span><br /><br /> <span data-ttu-id="cdb74-119">以前の MSID: %3</span><span class="sxs-lookup"><span data-stu-id="cdb74-119">Previous MSID: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="cdb74-120">説明</span><span class="sxs-lookup"><span data-stu-id="cdb74-120">Explanation</span></span>  
 <span data-ttu-id="cdb74-121">この情報イベントは、SSO データベースの再暗号化が正常に完了したことを示します。</span><span class="sxs-lookup"><span data-stu-id="cdb74-121">This Information event indicates that re-encryption of the SSO database has completed successfully.</span></span>  

## <a name="user-action"></a><span data-ttu-id="cdb74-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cdb74-122">User Action</span></span>  

- <span data-ttu-id="cdb74-123">ユーザーの操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cdb74-123">No user action is necessary.</span></span>  

  <span data-ttu-id="cdb74-124">詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください: </span><span class="sxs-lookup"><span data-stu-id="cdb74-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="cdb74-125">SSO データベースを更新する方法</span><span class="sxs-lookup"><span data-stu-id="cdb74-125">How to Update the SSO Database</span></span>](../core/how-to-update-the-sso-database.md)  

- [<span data-ttu-id="cdb74-126">SSO データベース情報を表示する方法</span><span class="sxs-lookup"><span data-stu-id="cdb74-126">How to Display the SSO Database Information</span></span>](../core/how-to-display-the-sso-database-information.md)
