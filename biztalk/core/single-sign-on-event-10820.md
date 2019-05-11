---
title: シングル サインオン:イベント 10820 |Microsoft Docs
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
ms.openlocfilehash: 59b0795514529e4e4236ebab96ceb5730171884f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395474"
---
# <a name="single-sign-on-event-10820"></a><span data-ttu-id="2745a-102">シングル サインオン:イベント 10820</span><span class="sxs-lookup"><span data-stu-id="2745a-102">Single Sign-On: Event 10820</span></span>
## <a name="details"></a><span data-ttu-id="2745a-103">詳細</span><span class="sxs-lookup"><span data-stu-id="2745a-103">Details</span></span>  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="2745a-104">製品名</span><span class="sxs-lookup"><span data-stu-id="2745a-104">Product Name</span></span>   |                                  <span data-ttu-id="2745a-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="2745a-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="2745a-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="2745a-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    <span data-ttu-id="2745a-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="2745a-107">Event ID</span></span>     |                                            <span data-ttu-id="2745a-108">10820</span><span class="sxs-lookup"><span data-stu-id="2745a-108">10820</span></span>                                             |
|  <span data-ttu-id="2745a-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="2745a-109">Event Source</span></span>   |                                            <span data-ttu-id="2745a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="2745a-110">ENTSSO</span></span>                                            |
|    <span data-ttu-id="2745a-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="2745a-111">Component</span></span>    |                                             <span data-ttu-id="2745a-112">なし</span><span class="sxs-lookup"><span data-stu-id="2745a-112">N/A</span></span>                                              |
|  <span data-ttu-id="2745a-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="2745a-113">Symbolic Name</span></span>  |                                <span data-ttu-id="2745a-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="2745a-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span></span>                                 |
|  <span data-ttu-id="2745a-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="2745a-115">Message Text</span></span>   | <span data-ttu-id="2745a-116">外部アカウントのパスワードを変更するときに、アダプターは、古いパスワードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2745a-116">When changing the password for an external account the adapter must supply the old password.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="2745a-117">説明</span><span class="sxs-lookup"><span data-stu-id="2745a-117">Explanation</span></span>  
 <span data-ttu-id="2745a-118">このアプリケーションは、パスワード同期アダプターに古いパスワードを指定する必要があるような方法で構成されます。</span><span class="sxs-lookup"><span data-stu-id="2745a-118">This application is configured in such a way that the password sync adapter is required to supply the old password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2745a-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="2745a-119">User Action</span></span>  
 <span data-ttu-id="2745a-120">パスワード同期アダプターの構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="2745a-120">Check the configuration of your password sync adapter.</span></span>