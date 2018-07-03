---
title: 'シングル サインオン: イベント 11056 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37e2dd5e-0fa4-4764-8ee1-de2ca2b263d1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 127ff9581779963cc93ff32987cff2549119efe8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010963"
---
# <a name="single-sign-on-event-11056"></a><span data-ttu-id="35b7c-102">シングル サインオン: イベント 11056</span><span class="sxs-lookup"><span data-stu-id="35b7c-102">Single Sign-On: Event 11056</span></span>
## <a name="details"></a><span data-ttu-id="35b7c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="35b7c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="35b7c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="35b7c-104">Product Name</span></span>   |                                                                                                                                                <span data-ttu-id="35b7c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="35b7c-105">Enterprise Single Sign-On</span></span>                                                                                                                                                 |
| <span data-ttu-id="35b7c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="35b7c-106">Product Version</span></span> |                                                                                                                                [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                                |
|    <span data-ttu-id="35b7c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="35b7c-107">Event ID</span></span>     |                                                                                                                                                          <span data-ttu-id="35b7c-108">11056</span><span class="sxs-lookup"><span data-stu-id="35b7c-108">11056</span></span>                                                                                                                                                           |
|  <span data-ttu-id="35b7c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="35b7c-109">Event Source</span></span>   |                                                                                                                                                          <span data-ttu-id="35b7c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="35b7c-110">ENTSSO</span></span>                                                                                                                                                          |
|    <span data-ttu-id="35b7c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="35b7c-111">Component</span></span>    |                                                                                                                                                           <span data-ttu-id="35b7c-112">なし</span><span class="sxs-lookup"><span data-stu-id="35b7c-112">N/A</span></span>                                                                                                                                                            |
|  <span data-ttu-id="35b7c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="35b7c-113">Symbolic Name</span></span>  |                                                                                                                                           <span data-ttu-id="35b7c-114">SSO_WARN_PS_DIRECT_GET_CREDS_FAILED</span><span class="sxs-lookup"><span data-stu-id="35b7c-114">SSO_WARN_PS_DIRECT_GET_CREDS_FAILED</span></span>                                                                                                                                            |
|  <span data-ttu-id="35b7c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="35b7c-115">Message Text</span></span>   | <span data-ttu-id="35b7c-116">既存の外部資格情報を SSO データベースから取得できなかったため、外部アカウントのパスワードを直接変更できませんでした。%r</span><span class="sxs-lookup"><span data-stu-id="35b7c-116">The password was not directly changed for the external account because the existing external credentials could not be obtained from the SSO database.%r</span></span><br /><br /> <span data-ttu-id="35b7c-117">追跡 ID: %1 %r</span><span class="sxs-lookup"><span data-stu-id="35b7c-117">Tracking ID: %1%r</span></span><br /><br /> <span data-ttu-id="35b7c-118">アプリケーション名: % 2 %r</span><span class="sxs-lookup"><span data-stu-id="35b7c-118">Application Name: %2%r</span></span><br /><br /> <span data-ttu-id="35b7c-119">Windows アカウント: % 3 %r</span><span class="sxs-lookup"><span data-stu-id="35b7c-119">Windows Account: %3%r</span></span><br /><br /> <span data-ttu-id="35b7c-120">外部アカウント: % 4 %r</span><span class="sxs-lookup"><span data-stu-id="35b7c-120">External Account: %4%r</span></span><br /><br /> <span data-ttu-id="35b7c-121">エラー コード: %5</span><span class="sxs-lookup"><span data-stu-id="35b7c-121">Error Code: %5</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="35b7c-122">説明</span><span class="sxs-lookup"><span data-stu-id="35b7c-122">Explanation</span></span>  
 <span data-ttu-id="35b7c-123">既存の外部資格情報を SSO データベースから取得できなかったため、外部アカウントのパスワードを直接変更できませんでした。</span><span class="sxs-lookup"><span data-stu-id="35b7c-123">The password was not directly changed for the external account because the existing external credentials could not be obtained from the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="35b7c-124">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="35b7c-124">User Action</span></span>  
 <span data-ttu-id="35b7c-125">表示された情報を使用して、Microsoft 製品サポート サービスに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="35b7c-125">Use the information provided and contact Microsoft Product Support Services.</span></span>