---
title: 'シングル サインオン: イベント 11043 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 128d68fb-1905-49b3-9b67-30a9442569cc
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99faeaefdd029995944033cdb77c6636e716ed5a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024544"
---
# <a name="single-sign-on-event-11043"></a><span data-ttu-id="abcb4-102">シングル サインオン: イベント 11043</span><span class="sxs-lookup"><span data-stu-id="abcb4-102">Single Sign-On: Event 11043</span></span>
## <a name="details"></a><span data-ttu-id="abcb4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="abcb4-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="abcb4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="abcb4-104">Product Name</span></span>   |                                                                                                                                             <span data-ttu-id="abcb4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="abcb4-105">Enterprise Single Sign-On</span></span>                                                                                                                                             |
| <span data-ttu-id="abcb4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="abcb4-106">Product Version</span></span> |                                                                                                                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                             |
|    <span data-ttu-id="abcb4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="abcb4-107">Event ID</span></span>     |                                                                                                                                                       <span data-ttu-id="abcb4-108">11043</span><span class="sxs-lookup"><span data-stu-id="abcb4-108">11043</span></span>                                                                                                                                                       |
|  <span data-ttu-id="abcb4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="abcb4-109">Event Source</span></span>   |                                                                                                                                                      <span data-ttu-id="abcb4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="abcb4-110">ENTSSO</span></span>                                                                                                                                                       |
|    <span data-ttu-id="abcb4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="abcb4-111">Component</span></span>    |                                                                                                                                                        <span data-ttu-id="abcb4-112">なし</span><span class="sxs-lookup"><span data-stu-id="abcb4-112">N/A</span></span>                                                                                                                                                        |
|  <span data-ttu-id="abcb4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="abcb4-113">Symbolic Name</span></span>  |                                                                                                                                       <span data-ttu-id="abcb4-114">SSO_WARN_PS_ADAPTER_REPORTED_FAILURE</span><span class="sxs-lookup"><span data-stu-id="abcb4-114">SSO_WARN_PS_ADAPTER_REPORTED_FAILURE</span></span>                                                                                                                                        |
|  <span data-ttu-id="abcb4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="abcb4-115">Message Text</span></span>   | <span data-ttu-id="abcb4-116">外部パスワードを変更しようとしたときに、パスワード同期アダプターでエラーが報告されました。</span><span class="sxs-lookup"><span data-stu-id="abcb4-116">The password sync adapter reported a failure while attempting to change the external password.</span></span> <span data-ttu-id="abcb4-117">SSO データベース内の外部パスワードは更新されませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="abcb4-117">The external password was not updated in the SSO database.%r</span></span><br /><br /> <span data-ttu-id="abcb4-118">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="abcb4-118">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="abcb4-119">アダプター: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="abcb4-119">Adapter: %2%r</span></span><br /><br /> <span data-ttu-id="abcb4-120">外部アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="abcb4-120">External Account: %3%r</span></span><br /><br /> <span data-ttu-id="abcb4-121">エラー メッセージ: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="abcb4-121">Error Message: %4%r</span></span><br /><br /> <span data-ttu-id="abcb4-122">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="abcb4-122">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="abcb4-123">説明</span><span class="sxs-lookup"><span data-stu-id="abcb4-123">Explanation</span></span>  
 <span data-ttu-id="abcb4-124">ENTSSO がパスワード変更をパスワード同期アダプターに送信する場合、ENTSSO で SSO データベース内に外部パスワードが作成される前に、外部パスワードを正しく変更しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="abcb4-124">When ENTSSO sends a password change to a password sync adapter, the external password must be successfully changed before ENTSSO makes it in the SSO database.</span></span> <span data-ttu-id="abcb4-125">この場合、その作業が行われていませんでした。</span><span class="sxs-lookup"><span data-stu-id="abcb4-125">In this case, that did not occur.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="abcb4-126">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="abcb4-126">User Action</span></span>  
 <span data-ttu-id="abcb4-127">警告メッセージの情報をメモし、システム管理者に問い合わせます。</span><span class="sxs-lookup"><span data-stu-id="abcb4-127">Note the information in the warning message and consult your system administrator.</span></span>