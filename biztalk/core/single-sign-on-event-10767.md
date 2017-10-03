---
title: "シングル サインオン: イベント 10767 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef5efc04-a0b5-4fc7-9d0e-f7aa9a9c413d
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67eb30238071cbac6dd50fe8edeec9ae581f9a57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10767"></a><span data-ttu-id="02c08-102">シングル サインオン: イベント 10767</span><span class="sxs-lookup"><span data-stu-id="02c08-102">Single Sign-On: Event 10767</span></span>
## <a name="details"></a><span data-ttu-id="02c08-103">詳細</span><span class="sxs-lookup"><span data-stu-id="02c08-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="02c08-104">製品名</span><span class="sxs-lookup"><span data-stu-id="02c08-104">Product Name</span></span>|<span data-ttu-id="02c08-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="02c08-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="02c08-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="02c08-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="02c08-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="02c08-107">Event ID</span></span>|<span data-ttu-id="02c08-108">10767</span><span class="sxs-lookup"><span data-stu-id="02c08-108">10767</span></span>|  
|<span data-ttu-id="02c08-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="02c08-109">Event Source</span></span>|<span data-ttu-id="02c08-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="02c08-110">ENTSSO</span></span>|  
|<span data-ttu-id="02c08-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="02c08-111">Component</span></span>|<span data-ttu-id="02c08-112">なし</span><span class="sxs-lookup"><span data-stu-id="02c08-112">N/A</span></span>|  
|<span data-ttu-id="02c08-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="02c08-113">Symbolic Name</span></span>|<span data-ttu-id="02c08-114">ENTSSO_E_NO_SSO_SERVER</span><span class="sxs-lookup"><span data-stu-id="02c08-114">ENTSSO_E_NO_SSO_SERVER</span></span>|  
|<span data-ttu-id="02c08-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="02c08-115">Message Text</span></span>|<span data-ttu-id="02c08-116">SSO サーバー ‘%1’ に接続できませんでした。</span><span class="sxs-lookup"><span data-stu-id="02c08-116">Could not contact the SSO server ‘%1’.</span></span> <span data-ttu-id="02c08-117">SSO が構成されていること、およびそのサーバーで SSO サービスが実行されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="02c08-117">Check that SSO is configured and that the SSO service is running on that server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="02c08-118">説明</span><span class="sxs-lookup"><span data-stu-id="02c08-118">Explanation</span></span>  
 <span data-ttu-id="02c08-119">ENTSSO クライアントが ENTSSO サーバーに接続できません。</span><span class="sxs-lookup"><span data-stu-id="02c08-119">The ENTSSO client is unable to contact the ENTSSO server.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="02c08-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="02c08-120">User Action</span></span>  
 <span data-ttu-id="02c08-121">ネットワーク接続を調べ、サーバー名のスペルが正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="02c08-121">Check network connectivity and make sure you spelled the server name correctly.</span></span>