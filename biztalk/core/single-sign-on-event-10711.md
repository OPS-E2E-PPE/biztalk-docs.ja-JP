---
title: シングル サインオン:イベント 10711 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40722fe1-4be9-40d3-b5c5-a740a4b59f45
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a656e0bc079c2fb11a2cef59e86e914087259cef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397242"
---
# <a name="single-sign-on-event-10711"></a><span data-ttu-id="c3aa7-102">シングル サインオン:イベント 10711</span><span class="sxs-lookup"><span data-stu-id="c3aa7-102">Single Sign-On: Event 10711</span></span>
## <a name="details"></a><span data-ttu-id="c3aa7-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c3aa7-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                   |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="c3aa7-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c3aa7-104">Product Name</span></span>   |                                                                                                             <span data-ttu-id="c3aa7-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c3aa7-105">Enterprise Single Sign-On</span></span>                                                                                                             |
| <span data-ttu-id="c3aa7-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c3aa7-106">Product Version</span></span> |                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                             |
|    <span data-ttu-id="c3aa7-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c3aa7-107">Event ID</span></span>     |                                                                                                                       <span data-ttu-id="c3aa7-108">10711</span><span class="sxs-lookup"><span data-stu-id="c3aa7-108">10711</span></span>                                                                                                                       |
|  <span data-ttu-id="c3aa7-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c3aa7-109">Event Source</span></span>   |                                                                                                                      <span data-ttu-id="c3aa7-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c3aa7-110">ENTSSO</span></span>                                                                                                                       |
|    <span data-ttu-id="c3aa7-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c3aa7-111">Component</span></span>    |                                                                                                                        <span data-ttu-id="c3aa7-112">該当なし</span><span class="sxs-lookup"><span data-stu-id="c3aa7-112">N\A</span></span>                                                                                                                        |
|  <span data-ttu-id="c3aa7-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c3aa7-113">Symbolic Name</span></span>  |                                                                                                         <span data-ttu-id="c3aa7-114">SSO_WARN_PS_MISSING_INITIAL_CREDS</span><span class="sxs-lookup"><span data-stu-id="c3aa7-114">SSO_WARN_PS_MISSING_INITIAL_CREDS</span></span>                                                                                                         |
|  <span data-ttu-id="c3aa7-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c3aa7-115">Message Text</span></span>   | <span data-ttu-id="c3aa7-116">外部パスワード変更。</span><span class="sxs-lookup"><span data-stu-id="c3aa7-116">External password change.</span></span> <span data-ttu-id="c3aa7-117">このマッピングのいくつか不足している外部資格情報フィールドを既定 values.%r に設定されています。</span><span class="sxs-lookup"><span data-stu-id="c3aa7-117">Some missing external credential fields for this mapping have been set to default values.%r</span></span><br /><br /> <span data-ttu-id="c3aa7-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="c3aa7-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="c3aa7-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="c3aa7-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="c3aa7-120">アプリケーション名: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="c3aa7-120">Application Name: %3%r</span></span><br /><br /> <span data-ttu-id="c3aa7-121">外部アカウント: %4</span><span class="sxs-lookup"><span data-stu-id="c3aa7-121">External Account: %4</span></span> |

## <a name="explanation"></a><span data-ttu-id="c3aa7-122">説明</span><span class="sxs-lookup"><span data-stu-id="c3aa7-122">Explanation</span></span>  
 <span data-ttu-id="c3aa7-123">この警告イベントは、資格情報がない外部パスワード変更が受信されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="c3aa7-123">This Warning event indicates that an external password change was received with missing credentials.</span></span> <span data-ttu-id="c3aa7-124">既定値は、これらのフィールドに使用されました。</span><span class="sxs-lookup"><span data-stu-id="c3aa7-124">Default values were used in those fields.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c3aa7-125">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c3aa7-125">User Action</span></span>  
 <span data-ttu-id="c3aa7-126">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3aa7-126">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="c3aa7-127">必要に応じて、一致するように資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="c3aa7-127">If necessary, set the credentials to match.</span></span>  

  <span data-ttu-id="c3aa7-128">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3aa7-128">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="c3aa7-129">SSO 関連アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c3aa7-129">SSO Affiliate Applications</span></span>](../core/sso-affiliate-applications.md)  

- [<span data-ttu-id="c3aa7-130">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="c3aa7-130">Password Synchronization</span></span>](../core/password-synchronization2.md)
