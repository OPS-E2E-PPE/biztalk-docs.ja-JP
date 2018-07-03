---
title: 'シングル サインオン: イベント 10592 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e044f9bd-c384-4f08-81f0-699e0c774c45
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9fdf7259de2217c2e6cd616f58b3b1118bf991c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017258"
---
# <a name="single-sign-on-event-10592"></a><span data-ttu-id="28c11-102">シングル サインオン: イベント 10592</span><span class="sxs-lookup"><span data-stu-id="28c11-102">Single Sign-On: Event 10592</span></span>
## <a name="details"></a><span data-ttu-id="28c11-103">詳細</span><span class="sxs-lookup"><span data-stu-id="28c11-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="28c11-104">製品名</span><span class="sxs-lookup"><span data-stu-id="28c11-104">Product Name</span></span>   |                                                             <span data-ttu-id="28c11-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="28c11-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="28c11-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="28c11-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="28c11-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="28c11-107">Event ID</span></span>     |                                                                       <span data-ttu-id="28c11-108">10592</span><span class="sxs-lookup"><span data-stu-id="28c11-108">10592</span></span>                                                                        |
|  <span data-ttu-id="28c11-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="28c11-109">Event Source</span></span>   |                                                                       <span data-ttu-id="28c11-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="28c11-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="28c11-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="28c11-111">Component</span></span>    |                                                                        <span data-ttu-id="28c11-112">なし</span><span class="sxs-lookup"><span data-stu-id="28c11-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="28c11-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="28c11-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="28c11-114">SSO_WARN_TICKET_DECRYPT_FAILED</span><span class="sxs-lookup"><span data-stu-id="28c11-114">SSO_WARN_TICKET_DECRYPT_FAILED</span></span>                                                           |
|  <span data-ttu-id="28c11-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="28c11-115">Message Text</span></span>   | <span data-ttu-id="28c11-116">チケットを暗号化解除できませんでした。</span><span class="sxs-lookup"><span data-stu-id="28c11-116">The ticket could not be decrypted.</span></span> <span data-ttu-id="28c11-117">チケットが有効ではないか、期限切れの可能性があります。%r</span><span class="sxs-lookup"><span data-stu-id="28c11-117">The ticket is not valid or it may have expired.%r</span></span><br /><br /> <span data-ttu-id="28c11-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="28c11-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="28c11-119">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="28c11-119">Error Code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="28c11-120">説明</span><span class="sxs-lookup"><span data-stu-id="28c11-120">Explanation</span></span>  
 <span data-ttu-id="28c11-121">チケットが有効ではないか、期限切れの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="28c11-121">The ticket is not valid or may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28c11-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="28c11-122">User Action</span></span>  
 <span data-ttu-id="28c11-123">使用するチケットが有効で、期限が切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="28c11-123">Confirm that the ticket you want to use is valid and has not expired.</span></span>