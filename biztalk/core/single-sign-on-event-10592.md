---
title: シングル サインオン:イベント 10592 |Microsoft Docs
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
ms.openlocfilehash: 0bfd622db90bbafcb4d2af1b45ae2b2286e3345c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270949"
---
# <a name="single-sign-on-event-10592"></a><span data-ttu-id="4331b-102">シングル サインオン:イベント 10592</span><span class="sxs-lookup"><span data-stu-id="4331b-102">Single Sign-On: Event 10592</span></span>
## <a name="details"></a><span data-ttu-id="4331b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="4331b-103">Details</span></span>  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="4331b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="4331b-104">Product Name</span></span>   |                                                             <span data-ttu-id="4331b-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="4331b-105">Enterprise Single Sign-On</span></span>                                                              |
| <span data-ttu-id="4331b-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="4331b-106">Product Version</span></span> |                                             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                             |
|    <span data-ttu-id="4331b-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="4331b-107">Event ID</span></span>     |                                                                       <span data-ttu-id="4331b-108">10592</span><span class="sxs-lookup"><span data-stu-id="4331b-108">10592</span></span>                                                                        |
|  <span data-ttu-id="4331b-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="4331b-109">Event Source</span></span>   |                                                                       <span data-ttu-id="4331b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="4331b-110">ENTSSO</span></span>                                                                       |
|    <span data-ttu-id="4331b-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="4331b-111">Component</span></span>    |                                                                        <span data-ttu-id="4331b-112">なし</span><span class="sxs-lookup"><span data-stu-id="4331b-112">N/A</span></span>                                                                         |
|  <span data-ttu-id="4331b-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="4331b-113">Symbolic Name</span></span>  |                                                           <span data-ttu-id="4331b-114">SSO_WARN_TICKET_DECRYPT_FAILED</span><span class="sxs-lookup"><span data-stu-id="4331b-114">SSO_WARN_TICKET_DECRYPT_FAILED</span></span>                                                           |
|  <span data-ttu-id="4331b-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="4331b-115">Message Text</span></span>   | <span data-ttu-id="4331b-116">チケットの暗号化を解除できませんでした。</span><span class="sxs-lookup"><span data-stu-id="4331b-116">The ticket could not be decrypted.</span></span> <span data-ttu-id="4331b-117">チケットが無効か expired.%r する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4331b-117">The ticket is not valid or it may have expired.%r</span></span><br /><br /> <span data-ttu-id="4331b-118">アプリケーション名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="4331b-118">Application Name: %1%r</span></span><br /><br /> <span data-ttu-id="4331b-119">エラー コード: %2</span><span class="sxs-lookup"><span data-stu-id="4331b-119">Error Code: %2</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="4331b-120">説明</span><span class="sxs-lookup"><span data-stu-id="4331b-120">Explanation</span></span>  
 <span data-ttu-id="4331b-121">チケットが無効であるか、期限が切れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="4331b-121">The ticket is not valid or may have expired.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="4331b-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="4331b-122">User Action</span></span>  
 <span data-ttu-id="4331b-123">使用するチケットが有効でありが切れていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="4331b-123">Confirm that the ticket you want to use is valid and has not expired.</span></span>