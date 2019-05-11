---
title: シングル サインオン:イベント 10767 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef5efc04-a0b5-4fc7-9d0e-f7aa9a9c413d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f225e6e80467aa269e579846c6c8ece05963cdb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394294"
---
# <a name="single-sign-on-event-10767"></a><span data-ttu-id="0e6ed-102">シングル サインオン:イベント 10767</span><span class="sxs-lookup"><span data-stu-id="0e6ed-102">Single Sign-On: Event 10767</span></span>
## <a name="details"></a><span data-ttu-id="0e6ed-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0e6ed-103">Details</span></span>  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e6ed-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0e6ed-104">Product Name</span></span>   |                                                <span data-ttu-id="0e6ed-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0e6ed-105">Enterprise Single Sign-On</span></span>                                                |
| <span data-ttu-id="0e6ed-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0e6ed-106">Product Version</span></span> |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                |
|    <span data-ttu-id="0e6ed-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0e6ed-107">Event ID</span></span>     |                                                          <span data-ttu-id="0e6ed-108">10767</span><span class="sxs-lookup"><span data-stu-id="0e6ed-108">10767</span></span>                                                          |
|  <span data-ttu-id="0e6ed-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0e6ed-109">Event Source</span></span>   |                                                         <span data-ttu-id="0e6ed-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0e6ed-110">ENTSSO</span></span>                                                          |
|    <span data-ttu-id="0e6ed-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0e6ed-111">Component</span></span>    |                                                           <span data-ttu-id="0e6ed-112">なし</span><span class="sxs-lookup"><span data-stu-id="0e6ed-112">N/A</span></span>                                                           |
|  <span data-ttu-id="0e6ed-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0e6ed-113">Symbolic Name</span></span>  |                                                 <span data-ttu-id="0e6ed-114">ENTSSO_E_NO_SSO_SERVER</span><span class="sxs-lookup"><span data-stu-id="0e6ed-114">ENTSSO_E_NO_SSO_SERVER</span></span>                                                  |
|  <span data-ttu-id="0e6ed-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0e6ed-115">Message Text</span></span>   | <span data-ttu-id="0e6ed-116">SSO サーバー '%1' に接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="0e6ed-116">Could not contact the SSO server ‘%1’.</span></span> <span data-ttu-id="0e6ed-117">SSO が構成されていることと、そのサーバーで SSO サービスが実行されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e6ed-117">Check that SSO is configured and that the SSO service is running on that server.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="0e6ed-118">説明</span><span class="sxs-lookup"><span data-stu-id="0e6ed-118">Explanation</span></span>  
 <span data-ttu-id="0e6ed-119">ENTSSO クライアントは、ENTSSO サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="0e6ed-119">The ENTSSO client is unable to contact the ENTSSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e6ed-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0e6ed-120">User Action</span></span>  
 <span data-ttu-id="0e6ed-121">ネットワーク接続を確認し、サーバー名のスペルが正しいかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0e6ed-121">Check network connectivity and make sure you spelled the server name correctly.</span></span>