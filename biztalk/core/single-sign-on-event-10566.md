---
title: シングル サインオン:イベント 10566 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7bd140b-5503-40f8-bf5d-604fa763989e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27530a47a1262cbc5baf9edede91dcee385fa91e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398786"
---
# <a name="single-sign-on-event-10566"></a><span data-ttu-id="06600-102">シングル サインオン:イベント 10566</span><span class="sxs-lookup"><span data-stu-id="06600-102">Single Sign-On: Event 10566</span></span>
## <a name="details"></a><span data-ttu-id="06600-103">詳細</span><span class="sxs-lookup"><span data-stu-id="06600-103">Details</span></span>  
  
|                 |                                                                                                                                                                    |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="06600-104">製品名</span><span class="sxs-lookup"><span data-stu-id="06600-104">Product Name</span></span>   |                                                                     <span data-ttu-id="06600-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="06600-105">Enterprise Single Sign-On</span></span>                                                                      |
| <span data-ttu-id="06600-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="06600-106">Product Version</span></span> |                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    <span data-ttu-id="06600-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="06600-107">Event ID</span></span>     |                                                                               <span data-ttu-id="06600-108">10566</span><span class="sxs-lookup"><span data-stu-id="06600-108">10566</span></span>                                                                                |
|  <span data-ttu-id="06600-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="06600-109">Event Source</span></span>   |                                                                               <span data-ttu-id="06600-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="06600-110">ENTSSO</span></span>                                                                               |
|    <span data-ttu-id="06600-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="06600-111">Component</span></span>    |                                                                                <span data-ttu-id="06600-112">なし</span><span class="sxs-lookup"><span data-stu-id="06600-112">N/A</span></span>                                                                                 |
|  <span data-ttu-id="06600-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="06600-113">Symbolic Name</span></span>  |                                                                  <span data-ttu-id="06600-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span><span class="sxs-lookup"><span data-stu-id="06600-114">SSO_WARN_CANNOT_UPDATE_APP_FLAGS</span></span>                                                                  |
|  <span data-ttu-id="06600-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="06600-115">Message Text</span></span>   | <span data-ttu-id="06600-116">このアプリケーションの指定したフラグの一部を更新することはできません。</span><span class="sxs-lookup"><span data-stu-id="06600-116">You cannot update some of the specified flags for this application.</span></span> <span data-ttu-id="06600-117">Ignored.%r されます。</span><span class="sxs-lookup"><span data-stu-id="06600-117">They will be ignored.%r</span></span><br /><br /> <span data-ttu-id="06600-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="06600-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="06600-119">指定フラグ マスク: %2</span><span class="sxs-lookup"><span data-stu-id="06600-119">Specified Flag Mask: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="06600-120">説明</span><span class="sxs-lookup"><span data-stu-id="06600-120">Explanation</span></span>  
 <span data-ttu-id="06600-121">アプリケーションの特定のフラグを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="06600-121">Certain flags in an application cannot be changed.</span></span> <span data-ttu-id="06600-122">(たとえば、ことはできませんをグループに個々 のアプリケーションの種類を変更する。)このアプリケーションのフラグは、警告テキストで指定されます。</span><span class="sxs-lookup"><span data-stu-id="06600-122">(For example, it is not allowed to change an application type from Individual to Group.) The flags for this application are specified in the warning text.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="06600-123">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="06600-123">User Action</span></span>  
 <span data-ttu-id="06600-124">ユーザーによる操作は不要です。</span><span class="sxs-lookup"><span data-stu-id="06600-124">No user action is required.</span></span>