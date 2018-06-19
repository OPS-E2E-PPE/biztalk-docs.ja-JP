---
title: 'シングル サインオン: イベント 10820 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46a3ae1be84ca0b936fe38463e51e6385071f7a9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276690"
---
# <a name="single-sign-on-event-10820"></a><span data-ttu-id="0bfd0-102">シングル サインオン: イベント 10820</span><span class="sxs-lookup"><span data-stu-id="0bfd0-102">Single Sign-On: Event 10820</span></span>
## <a name="details"></a><span data-ttu-id="0bfd0-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0bfd0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0bfd0-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0bfd0-104">Product Name</span></span>|<span data-ttu-id="0bfd0-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0bfd0-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0bfd0-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0bfd0-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0bfd0-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0bfd0-107">Event ID</span></span>|<span data-ttu-id="0bfd0-108">10820</span><span class="sxs-lookup"><span data-stu-id="0bfd0-108">10820</span></span>|  
|<span data-ttu-id="0bfd0-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0bfd0-109">Event Source</span></span>|<span data-ttu-id="0bfd0-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0bfd0-110">ENTSSO</span></span>|  
|<span data-ttu-id="0bfd0-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0bfd0-111">Component</span></span>|<span data-ttu-id="0bfd0-112">なし</span><span class="sxs-lookup"><span data-stu-id="0bfd0-112">N/A</span></span>|  
|<span data-ttu-id="0bfd0-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0bfd0-113">Symbolic Name</span></span>|<span data-ttu-id="0bfd0-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="0bfd0-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span></span>|  
|<span data-ttu-id="0bfd0-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0bfd0-115">Message Text</span></span>|<span data-ttu-id="0bfd0-116">外部アカウントのパスワードを変更するときに、アダプターで古いパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bfd0-116">When changing the password for an external account the adapter must supply the old password.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0bfd0-117">説明</span><span class="sxs-lookup"><span data-stu-id="0bfd0-117">Explanation</span></span>  
 <span data-ttu-id="0bfd0-118">このアプリケーションは、パスワード同期アダプターに古いパスワードの指定を求めるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="0bfd0-118">This application is configured in such a way that the password sync adapter is required to supply the old password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0bfd0-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0bfd0-119">User Action</span></span>  
 <span data-ttu-id="0bfd0-120">パスワード同期アダプターの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="0bfd0-120">Check the configuration of your password sync adapter.</span></span>