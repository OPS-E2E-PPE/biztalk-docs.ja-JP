---
title: 'シングル サインオン: イベント 11063 |Microsoft Docs'
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
ms.openlocfilehash: 5a653b8c5cf27925c65d8922a5a561855fdb6a4c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975571"
---
# <a name="single-sign-on-event-11063"></a><span data-ttu-id="9a8fa-102">シングル サインオン: イベント 11063</span><span class="sxs-lookup"><span data-stu-id="9a8fa-102">Single Sign-On: Event 11063</span></span>
## <a name="details"></a><span data-ttu-id="9a8fa-103">詳細</span><span class="sxs-lookup"><span data-stu-id="9a8fa-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="9a8fa-104">製品名</span><span class="sxs-lookup"><span data-stu-id="9a8fa-104">Product Name</span></span>   |                 <span data-ttu-id="9a8fa-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="9a8fa-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="9a8fa-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="9a8fa-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="9a8fa-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="9a8fa-107">Event ID</span></span>     |                           <span data-ttu-id="9a8fa-108">11063</span><span class="sxs-lookup"><span data-stu-id="9a8fa-108">11063</span></span>                            |
|  <span data-ttu-id="9a8fa-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="9a8fa-109">Event Source</span></span>   |                           <span data-ttu-id="9a8fa-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9a8fa-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="9a8fa-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="9a8fa-111">Component</span></span>    |                            <span data-ttu-id="9a8fa-112">なし</span><span class="sxs-lookup"><span data-stu-id="9a8fa-112">N/A</span></span>                             |
|  <span data-ttu-id="9a8fa-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="9a8fa-113">Symbolic Name</span></span>  |          <span data-ttu-id="9a8fa-114">SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="9a8fa-114">SSO_ERROR_PS_MIIS_CALLBACK_ACCESS_DENIED</span></span>          |
|  <span data-ttu-id="9a8fa-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="9a8fa-115">Message Text</span></span>   |      <span data-ttu-id="9a8fa-116">(MIIS に対する) パスワード同期サーバーのアクセスが拒否されました。%r</span><span class="sxs-lookup"><span data-stu-id="9a8fa-116">Password sync server (for MIIS) access denied.%r</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="9a8fa-117">説明</span><span class="sxs-lookup"><span data-stu-id="9a8fa-117">Explanation</span></span>  
 <span data-ttu-id="9a8fa-118">MIIS コールバックのアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="9a8fa-118">MIIS Callback access has been denied.</span></span> <span data-ttu-id="9a8fa-119">このエラーの原因として最も可能性が高いのは、ENTSSO システムと MIIS の間での Kerberos 認証の使用の失敗です。</span><span class="sxs-lookup"><span data-stu-id="9a8fa-119">The most likely cause of this error is failure to use the Kerberos authentication between the ENTSSO system and MIIS.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9a8fa-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="9a8fa-120">User Action</span></span>  
 <span data-ttu-id="9a8fa-121">ENTSSO システムが Kerberos 認証を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9a8fa-121">Confirm that your ENTSSO system is using Kerberos authentication.</span></span> <span data-ttu-id="9a8fa-122">詳細については、次を参照してください。 [SSO のセキュリティに関する推奨事項](../core/sso-security-recommendations.md)します。</span><span class="sxs-lookup"><span data-stu-id="9a8fa-122">For more information, see [SSO Security Recommendations](../core/sso-security-recommendations.md).</span></span>