---
title: 'シングル サインオン: イベント 10809 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e010c6ee391e72ec270ddbdc767bed861836cb8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277018"
---
# <a name="single-sign-on-event-10809"></a><span data-ttu-id="3091a-102">シングル サインオン: イベント 10809</span><span class="sxs-lookup"><span data-stu-id="3091a-102">Single Sign-On: Event 10809</span></span>
## <a name="details"></a><span data-ttu-id="3091a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3091a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="3091a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3091a-104">Product Name</span></span>|<span data-ttu-id="3091a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3091a-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3091a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3091a-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3091a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3091a-107">Event ID</span></span>|<span data-ttu-id="3091a-108">10809</span><span class="sxs-lookup"><span data-stu-id="3091a-108">10809</span></span>|  
|<span data-ttu-id="3091a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3091a-109">Event Source</span></span>|<span data-ttu-id="3091a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3091a-110">ENTSSO</span></span>|  
|<span data-ttu-id="3091a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3091a-111">Component</span></span>|<span data-ttu-id="3091a-112">なし</span><span class="sxs-lookup"><span data-stu-id="3091a-112">N/A</span></span>|  
|<span data-ttu-id="3091a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3091a-113">Symbolic Name</span></span>|<span data-ttu-id="3091a-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="3091a-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span></span>|  
|<span data-ttu-id="3091a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3091a-115">Message Text</span></span>|<span data-ttu-id="3091a-116">アプリケーションはホスト側開始シングル サインオンに対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="3091a-116">The application is not enabled for Host Initiated Single Sign-On.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3091a-117">説明</span><span class="sxs-lookup"><span data-stu-id="3091a-117">Explanation</span></span>  
 <span data-ttu-id="3091a-118">アプリケーションはホスト側開始シングル サインオンに対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="3091a-118">The application is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3091a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3091a-119">User Action</span></span>  
 <span data-ttu-id="3091a-120">管理ツールを使用して、ホスト側開始シングル サインオンを構成します。</span><span class="sxs-lookup"><span data-stu-id="3091a-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="3091a-121">次の設定を行います</span><span class="sxs-lookup"><span data-stu-id="3091a-121">This will set the</span></span>  
  
 <span data-ttu-id="3091a-122">アプリケーションの SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS フラグが設定されます。</span><span class="sxs-lookup"><span data-stu-id="3091a-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the application.</span></span>