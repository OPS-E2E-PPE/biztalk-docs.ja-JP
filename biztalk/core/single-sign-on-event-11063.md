---
title: シングル サインオン:イベント 11063 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c84f91de-221d-43c4-8d23-3d1b7fd29cf7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5971a2ace4307128d094a6b88c4928616173694
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65258681"
---
# <a name="single-sign-on-event-11063"></a><span data-ttu-id="1f6f2-102">シングル サインオン:イベント 11063</span><span class="sxs-lookup"><span data-stu-id="1f6f2-102">Single Sign-On: Event 11063</span></span>
## <a name="details"></a><span data-ttu-id="1f6f2-103">詳細</span><span class="sxs-lookup"><span data-stu-id="1f6f2-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="1f6f2-104">製品名</span><span class="sxs-lookup"><span data-stu-id="1f6f2-104">Product Name</span></span>   |                 <span data-ttu-id="1f6f2-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="1f6f2-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="1f6f2-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="1f6f2-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="1f6f2-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="1f6f2-107">Event ID</span></span>     |                           <span data-ttu-id="1f6f2-108">11063</span><span class="sxs-lookup"><span data-stu-id="1f6f2-108">11063</span></span>                            |
|  <span data-ttu-id="1f6f2-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="1f6f2-109">Event Source</span></span>   |                           <span data-ttu-id="1f6f2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="1f6f2-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="1f6f2-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="1f6f2-111">Component</span></span>    |                            <span data-ttu-id="1f6f2-112">なし</span><span class="sxs-lookup"><span data-stu-id="1f6f2-112">N/A</span></span>                             |
|  <span data-ttu-id="1f6f2-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="1f6f2-113">Symbolic Name</span></span>  |          <span data-ttu-id="1f6f2-114">SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="1f6f2-114">SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED</span></span>          |
|  <span data-ttu-id="1f6f2-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="1f6f2-115">Message Text</span></span>   |      <span data-ttu-id="1f6f2-116">(MIIS に対する) パスワード同期サーバーのアクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="1f6f2-116">Password sync server (for MIIS) access denied.%r</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="1f6f2-117">説明</span><span class="sxs-lookup"><span data-stu-id="1f6f2-117">Explanation</span></span>  
 <span data-ttu-id="1f6f2-118">MIIS コールバックのアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="1f6f2-118">MIIS Callback access has been denied.</span></span> <span data-ttu-id="1f6f2-119">このエラーの原因として最も可能性が高いのは、ENTSSO システムと MIIS の間での Kerberos 認証の使用の失敗です。</span><span class="sxs-lookup"><span data-stu-id="1f6f2-119">The most likely cause of this error is failure to use the Kerberos authentication between the ENTSSO system and MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1f6f2-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="1f6f2-120">User Action</span></span>  
 <span data-ttu-id="1f6f2-121">ENTSSO システムが Kerberos 認証を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1f6f2-121">Confirm that your ENTSSO system is using Kerberos authentication.</span></span> <span data-ttu-id="1f6f2-122">詳細については、次を参照してください。 [SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)します。</span><span class="sxs-lookup"><span data-stu-id="1f6f2-122">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>