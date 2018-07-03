---
title: 'シングル サインオン: イベント 10750 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2a0fdaf2-d429-40b9-adc3-eb134687fb1a
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28526c6695cbf8f9c29e99621d6cb2f852fa7021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984371"
---
# <a name="single-sign-on-event-10750"></a><span data-ttu-id="68e35-102">シングル サインオン: イベント 10750</span><span class="sxs-lookup"><span data-stu-id="68e35-102">Single Sign-On: Event 10750</span></span>
## <a name="details"></a><span data-ttu-id="68e35-103">詳細</span><span class="sxs-lookup"><span data-stu-id="68e35-103">Details</span></span>  

|                 |                                                                                                                                                                                                                                                                  |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="68e35-104">製品名</span><span class="sxs-lookup"><span data-stu-id="68e35-104">Product Name</span></span>   |                                                                                                                    <span data-ttu-id="68e35-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="68e35-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="68e35-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="68e35-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                    |
|    <span data-ttu-id="68e35-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="68e35-107">Event ID</span></span>     |                                                                                                                              <span data-ttu-id="68e35-108">10750</span><span class="sxs-lookup"><span data-stu-id="68e35-108">10750</span></span>                                                                                                                               |
|  <span data-ttu-id="68e35-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="68e35-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="68e35-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="68e35-110">ENTSSO</span></span>                                                                                                                              |
|    <span data-ttu-id="68e35-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="68e35-111">Component</span></span>    |                                                                                                                               <span data-ttu-id="68e35-112">N\A</span><span class="sxs-lookup"><span data-stu-id="68e35-112">N\A</span></span>                                                                                                                                |
|  <span data-ttu-id="68e35-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="68e35-113">Symbolic Name</span></span>  |                                                                                                                <span data-ttu-id="68e35-114">SSO_ERROR_PS_WRONG_USER_NAME_TYPE</span><span class="sxs-lookup"><span data-stu-id="68e35-114">SSO_ERROR_PS_WRONG_USER_NAME_TYPE</span></span>                                                                                                                 |
|  <span data-ttu-id="68e35-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="68e35-115">Message Text</span></span>   | <span data-ttu-id="68e35-116">PasswordChangeNotify: 正しくないユーザー名の種類。</span><span class="sxs-lookup"><span data-stu-id="68e35-116">PasswordChangeNotify: Incorrect User Name Type.</span></span> <span data-ttu-id="68e35-117">指定できる値は USER_NAME_TYPE_NT4 のみです。</span><span class="sxs-lookup"><span data-stu-id="68e35-117">The only accepted value is USER_NAME_TYPE_NT4.</span></span><br /><br /> <span data-ttu-id="68e35-118">ターゲットが Active Directory で正しく構成されていません。%r</span><span class="sxs-lookup"><span data-stu-id="68e35-118">The target is incorrectly configured in Active Directory.%r</span></span><br /><br /> <span data-ttu-id="68e35-119">ユーザー名の種類: %r</span><span class="sxs-lookup"><span data-stu-id="68e35-119">User Name Type: %1%r</span></span><br /><br /> <span data-ttu-id="68e35-120">クライアント ユーザー: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="68e35-120">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="68e35-121">エラー コード: %3</span><span class="sxs-lookup"><span data-stu-id="68e35-121">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="68e35-122">説明</span><span class="sxs-lookup"><span data-stu-id="68e35-122">Explanation</span></span>  
 <span data-ttu-id="68e35-123">このエラー イベントは、パスワード同期が、パスワード変更通知サービス (PCNS) からパスワード変更を受け取ったが、パスワード変更の形式が正しくなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="68e35-123">This Error event indicates that Password Sync received a password change from the Password Change Notification Service (PCNS), but the password change was in the wrong format.</span></span>  

## <a name="user-action"></a><span data-ttu-id="68e35-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="68e35-124">User Action</span></span>  
 <span data-ttu-id="68e35-125">このエラーを解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="68e35-125">To resolve this error, do the following:</span></span>  

- <span data-ttu-id="68e35-126">PCNS の構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="68e35-126">Check the PCNS configuration.</span></span> <span data-ttu-id="68e35-127">PCNS はドメイン コントローラーでのみ実行できます。</span><span class="sxs-lookup"><span data-stu-id="68e35-127">PCNS can run only on a domain controller.</span></span>  

- <span data-ttu-id="68e35-128">Active Directory で、ユーザー名の種類を USER_NAME_TYPE_NT4 に構成します。</span><span class="sxs-lookup"><span data-stu-id="68e35-128">Configure User Name Type to USER_NAME_TYPE_NT4 in Active Directory.</span></span>  

  <span data-ttu-id="68e35-129">詳細については、次のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68e35-129">For more information, see the following resources:</span></span>  

- <span data-ttu-id="68e35-130">ユーザー名の種類を指定する方法については、Active Directory のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="68e35-130">Refer to Active Directory documentation for information on how to specify User Name Type.</span></span>  

- [<span data-ttu-id="68e35-131">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="68e35-131">Password Synchronization</span></span>](../core/password-synchronization2.md)
