---
title: シングル サインオン:イベント 10547 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: be25cdc9-d6c1-488d-9ead-877a2454c3d1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8ec8133a6d2456e2cdafca56ae956f6be1d31a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243423"
---
# <a name="single-sign-on-event-10547"></a><span data-ttu-id="81d7d-102">シングル サインオン:イベント 10547</span><span class="sxs-lookup"><span data-stu-id="81d7d-102">Single Sign-On: Event 10547</span></span>
## <a name="details"></a><span data-ttu-id="81d7d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="81d7d-103">Details</span></span>  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="81d7d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="81d7d-104">Product Name</span></span>   |                         <span data-ttu-id="81d7d-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="81d7d-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="81d7d-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="81d7d-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="81d7d-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="81d7d-107">Event ID</span></span>     |                                   <span data-ttu-id="81d7d-108">10547</span><span class="sxs-lookup"><span data-stu-id="81d7d-108">10547</span></span>                                   |
|  <span data-ttu-id="81d7d-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="81d7d-109">Event Source</span></span>   |                                  <span data-ttu-id="81d7d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="81d7d-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="81d7d-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="81d7d-111">Component</span></span>    |                                    <span data-ttu-id="81d7d-112">CO</span><span class="sxs-lookup"><span data-stu-id="81d7d-112">CO</span></span>                                     |
|  <span data-ttu-id="81d7d-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="81d7d-113">Symbolic Name</span></span>  |                          <span data-ttu-id="81d7d-114">SSO_WARN_UPDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="81d7d-114">SSO_WARN_UPDATE_FAILED</span></span>                           |
|  <span data-ttu-id="81d7d-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="81d7d-115">Message Text</span></span>   | <span data-ttu-id="81d7d-116">再暗号化中に、SSO データベース内の資格情報を更新できませんでした。</span><span class="sxs-lookup"><span data-stu-id="81d7d-116">Failed to update the credentials in the SSO database during re-encryption</span></span> |

## <a name="explanation"></a><span data-ttu-id="81d7d-117">説明</span><span class="sxs-lookup"><span data-stu-id="81d7d-117">Explanation</span></span>  
 <span data-ttu-id="81d7d-118">この警告イベントは、新しい暗号化の結果で資格情報を更新することがないことを示します。</span><span class="sxs-lookup"><span data-stu-id="81d7d-118">This Warning event indicates that it was not possible to update the credentials with the result of the new encryption.</span></span> <span data-ttu-id="81d7d-119">新しいシークレットを生成することによって、または古いシークレットを復元することで、マスター シークレットが変更されたときに、再暗号化は、以前のシークレットで暗号化されたすべてのシークレットの暗号化解除し、再暗号化して、新しいシークレットを SSO データベースで実行されます。</span><span class="sxs-lookup"><span data-stu-id="81d7d-119">When the master secret is changed, either by generating a new secret or by restoring an old secret, a re-encryption is performed on the SSO database to decrypt all the secrets encrypted with the old secret, and re-encrypt them with the new secret.</span></span> <span data-ttu-id="81d7d-120">このイベントは、再暗号化の過程で、資格情報が削除された場合に発生することができます。</span><span class="sxs-lookup"><span data-stu-id="81d7d-120">This event can occur if the credentials were deleted as they were in the process of being re-encrypted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="81d7d-121">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="81d7d-121">User Action</span></span>  
 <span data-ttu-id="81d7d-122">この警告を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="81d7d-122">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="81d7d-123">別の再暗号化に若干の遅延の後に発生するまで待ちます自動的を実行しない場合は、1 つが必要な場合に、新しい再暗号化をトリガーする SSO サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="81d7d-123">Wait for another re-encryption to occur after a short delay; if that does not occur automatically, restart the SSO service which will trigger a new re-encryption if one is required.</span></span>  

  <span data-ttu-id="81d7d-124">詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。</span><span class="sxs-lookup"><span data-stu-id="81d7d-124">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="81d7d-125">SSO について</span><span class="sxs-lookup"><span data-stu-id="81d7d-125">Understanding SSO</span></span>](../core/understanding-sso.md)
