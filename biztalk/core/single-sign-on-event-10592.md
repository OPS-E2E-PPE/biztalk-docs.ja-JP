---
title: 'シングル サインオン: イベント 10592 |Microsoft ドキュメント'
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
ms.openlocfilehash: 0f03f32a956cabe906c22afe0c89a096a1ad213f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270442"
---
# <a name="single-sign-on-event-10592"></a><span data-ttu-id="fa08f-102">シングル サインオン: イベント 10592</span><span class="sxs-lookup"><span data-stu-id="fa08f-102">Single Sign-On: Event 10592</span></span>
## <a name="details"></a><span data-ttu-id="fa08f-103">詳細</span><span class="sxs-lookup"><span data-stu-id="fa08f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="fa08f-104">製品名</span><span class="sxs-lookup"><span data-stu-id="fa08f-104">Product Name</span></span>|<span data-ttu-id="fa08f-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="fa08f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="fa08f-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="fa08f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="fa08f-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="fa08f-107">Event ID</span></span>|<span data-ttu-id="fa08f-108">10592</span><span class="sxs-lookup"><span data-stu-id="fa08f-108">10592</span></span>|  
|<span data-ttu-id="fa08f-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="fa08f-109">Event Source</span></span>|<span data-ttu-id="fa08f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="fa08f-110">ENTSSO</span></span>|  
|<span data-ttu-id="fa08f-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="fa08f-111">Component</span></span>|<span data-ttu-id="fa08f-112">なし</span><span class="sxs-lookup"><span data-stu-id="fa08f-112">N/A</span></span>|  
|<span data-ttu-id="fa08f-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="fa08f-113">Symbolic Name</span></span>|<span data-ttu-id="fa08f-114">SSO_WARN_TICKET_DECRYPT_FAILED</span><span class="sxs-lookup"><span data-stu-id="fa08f-114">SSO_WARN_TICKET_DECRYPT_FAILED</span></span>|  
|<span data-ttu-id="fa08f-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="fa08f-115">Message Text</span></span>|<span data-ttu-id="fa08f-116">チケットを暗号化解除できませんでした。</span><span class="sxs-lookup"><span data-stu-id="fa08f-116">The ticket could not be decrypted.</span></span> <span data-ttu-id="fa08f-117">チケットが有効ではないか、期限切れの可能性があります。%r</span><span class="sxs-lookup"><span data-stu-id="fa08f-117">The ticket is not valid or it may have expired.%r</span></span><br /><br /> <span data-ttu-id="fa08f-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="fa08f-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="fa08f-119">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="fa08f-119">Error Code: %2</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="fa08f-120">説明</span><span class="sxs-lookup"><span data-stu-id="fa08f-120">Explanation</span></span>  
 <span data-ttu-id="fa08f-121">チケットが有効ではないか、期限切れの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fa08f-121">The ticket is not valid or may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="fa08f-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="fa08f-122">User Action</span></span>  
 <span data-ttu-id="fa08f-123">使用するチケットが有効で、期限が切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="fa08f-123">Confirm that the ticket you want to use is valid and has not expired.</span></span>