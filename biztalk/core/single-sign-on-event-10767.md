---
title: 'シングル サインオン: イベント 10767 |Microsoft Docs'
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
ms.openlocfilehash: a14733abb624207704b304ef9718608c9df1c4bf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977339"
---
# <a name="single-sign-on-event-10767"></a><span data-ttu-id="5e4b3-102">シングル サインオン: イベント 10767</span><span class="sxs-lookup"><span data-stu-id="5e4b3-102">Single Sign-On: Event 10767</span></span>
## <a name="details"></a><span data-ttu-id="5e4b3-103">詳細</span><span class="sxs-lookup"><span data-stu-id="5e4b3-103">Details</span></span>  
  
|                 |                                                                                                                         |
|-----------------|-------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="5e4b3-104">製品名</span><span class="sxs-lookup"><span data-stu-id="5e4b3-104">Product Name</span></span>   |                                                <span data-ttu-id="5e4b3-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="5e4b3-105">Enterprise Single Sign-On</span></span>                                                |
| <span data-ttu-id="5e4b3-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="5e4b3-106">Product Version</span></span> |                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                |
|    <span data-ttu-id="5e4b3-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="5e4b3-107">Event ID</span></span>     |                                                          <span data-ttu-id="5e4b3-108">10767</span><span class="sxs-lookup"><span data-stu-id="5e4b3-108">10767</span></span>                                                          |
|  <span data-ttu-id="5e4b3-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="5e4b3-109">Event Source</span></span>   |                                                         <span data-ttu-id="5e4b3-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5e4b3-110">ENTSSO</span></span>                                                          |
|    <span data-ttu-id="5e4b3-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="5e4b3-111">Component</span></span>    |                                                           <span data-ttu-id="5e4b3-112">なし</span><span class="sxs-lookup"><span data-stu-id="5e4b3-112">N/A</span></span>                                                           |
|  <span data-ttu-id="5e4b3-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="5e4b3-113">Symbolic Name</span></span>  |                                                 <span data-ttu-id="5e4b3-114">ENTSSO_E_NO_SSO_SERVER</span><span class="sxs-lookup"><span data-stu-id="5e4b3-114">ENTSSO_E_NO_SSO_SERVER</span></span>                                                  |
|  <span data-ttu-id="5e4b3-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="5e4b3-115">Message Text</span></span>   | <span data-ttu-id="5e4b3-116">SSO サーバー ‘%1’ に接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="5e4b3-116">Could not contact the SSO server ‘%1’.</span></span> <span data-ttu-id="5e4b3-117">SSO が構成されていること、およびそのサーバーで SSO サービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5e4b3-117">Check that SSO is configured and that the SSO service is running on that server.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="5e4b3-118">説明</span><span class="sxs-lookup"><span data-stu-id="5e4b3-118">Explanation</span></span>  
 <span data-ttu-id="5e4b3-119">ENTSSO クライアントが ENTSSO サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="5e4b3-119">The ENTSSO client is unable to contact the ENTSSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5e4b3-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="5e4b3-120">User Action</span></span>  
 <span data-ttu-id="5e4b3-121">ネットワーク接続を調べ、サーバー名のスペルが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="5e4b3-121">Check network connectivity and make sure you spelled the server name correctly.</span></span>