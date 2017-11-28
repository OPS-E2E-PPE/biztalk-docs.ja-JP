---
title: "シングル サインオン: イベント 10808 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b4efc1d-f163-4440-a78e-53065c6af36c
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b891a8cb076c332eca8918ece713385c1bbccc3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10808"></a><span data-ttu-id="51d1c-102">シングル サインオン: イベント 10808</span><span class="sxs-lookup"><span data-stu-id="51d1c-102">Single Sign-On: Event 10808</span></span>
## <a name="details"></a><span data-ttu-id="51d1c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="51d1c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="51d1c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="51d1c-104">Product Name</span></span>|<span data-ttu-id="51d1c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="51d1c-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="51d1c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="51d1c-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="51d1c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="51d1c-107">Event ID</span></span>|<span data-ttu-id="51d1c-108">10808</span><span class="sxs-lookup"><span data-stu-id="51d1c-108">10808</span></span>|  
|<span data-ttu-id="51d1c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="51d1c-109">Event Source</span></span>|<span data-ttu-id="51d1c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="51d1c-110">ENTSSO</span></span>|  
|<span data-ttu-id="51d1c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="51d1c-111">Component</span></span>|<span data-ttu-id="51d1c-112">なし</span><span class="sxs-lookup"><span data-stu-id="51d1c-112">N/A</span></span>|  
|<span data-ttu-id="51d1c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="51d1c-113">Symbolic Name</span></span>|<span data-ttu-id="51d1c-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="51d1c-114">ENTSSO_E_HISSO_SYSTEM_NOT_ENABLED</span></span>|  
|<span data-ttu-id="51d1c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="51d1c-115">Message Text</span></span>|<span data-ttu-id="51d1c-116">SSO システムはホスト側開始シングル サインオンに対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="51d1c-116">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="51d1c-117">説明</span><span class="sxs-lookup"><span data-stu-id="51d1c-117">Explanation</span></span>  
 <span data-ttu-id="51d1c-118">SSO システムはホスト側開始シングル サインオンに対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="51d1c-118">The SSO system is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="51d1c-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="51d1c-119">User Action</span></span>  
 <span data-ttu-id="51d1c-120">管理ツールを使用して、ホスト側開始シングル サインオンを構成します。</span><span class="sxs-lookup"><span data-stu-id="51d1c-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="51d1c-121">次の設定を行います</span><span class="sxs-lookup"><span data-stu-id="51d1c-121">This will set the</span></span>  
  
 <span data-ttu-id="51d1c-122">グローバル情報の SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="51d1c-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the global information.</span></span>