---
title: シングル サインオン:イベント 10819 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffa5e977-c8b9-4568-8963-0d4cf44b5637
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f338b78cd9c19b337b83eb829736cb7e81612e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396638"
---
# <a name="single-sign-on-event-10819"></a><span data-ttu-id="d45ce-102">シングル サインオン:イベント 10819</span><span class="sxs-lookup"><span data-stu-id="d45ce-102">Single Sign-On: Event 10819</span></span>
## <a name="details"></a><span data-ttu-id="d45ce-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d45ce-103">Details</span></span>  
  
|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  <span data-ttu-id="d45ce-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d45ce-104">Product Name</span></span>   |                         <span data-ttu-id="d45ce-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="d45ce-105">Enterprise Single Sign-On</span></span>                         |
| <span data-ttu-id="d45ce-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d45ce-106">Product Version</span></span> |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    <span data-ttu-id="d45ce-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d45ce-107">Event ID</span></span>     |                                   <span data-ttu-id="d45ce-108">10819</span><span class="sxs-lookup"><span data-stu-id="d45ce-108">10819</span></span>                                   |
|  <span data-ttu-id="d45ce-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d45ce-109">Event Source</span></span>   |                                  <span data-ttu-id="d45ce-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d45ce-110">ENTSSO</span></span>                                   |
|    <span data-ttu-id="d45ce-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d45ce-111">Component</span></span>    |                                    <span data-ttu-id="d45ce-112">なし</span><span class="sxs-lookup"><span data-stu-id="d45ce-112">N/A</span></span>                                    |
|  <span data-ttu-id="d45ce-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d45ce-113">Symbolic Name</span></span>  |                         <span data-ttu-id="d45ce-114">ENTSSO_E_MAPPING_CONFLICT</span><span class="sxs-lookup"><span data-stu-id="d45ce-114">ENTSSO_E_MAPPING_CONFLICT</span></span>                         |
|  <span data-ttu-id="d45ce-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d45ce-115">Message Text</span></span>   | <span data-ttu-id="d45ce-116">マッピングの競合があるため、外部アカウントは更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="d45ce-116">The external account was not updated because there is a mapping conflict.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d45ce-117">説明</span><span class="sxs-lookup"><span data-stu-id="d45ce-117">Explanation</span></span>  
 <span data-ttu-id="d45ce-118">マッピングの競合があるため、外部アカウントは更新されませんでした。</span><span class="sxs-lookup"><span data-stu-id="d45ce-118">The external account was not updated because there is a mapping conflict.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d45ce-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d45ce-119">User Action</span></span>  
 <span data-ttu-id="d45ce-120">マッピングの競合が予想される動作の場合は、操作は必要ありません。このメッセージは情報のみです。</span><span class="sxs-lookup"><span data-stu-id="d45ce-120">If this is expected behavior then no action is required, this message is informational only.</span></span> <span data-ttu-id="d45ce-121">マッピングの競合を許可する必要がある場合は、アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="d45ce-121">If mapping conflicts should be allowed then configure the application accordingly.</span></span>  
  
 <span data-ttu-id="d45ce-122">マッピングの競合の詳細については、次を参照してください。**パスワード同期アダプターのプロパティ。オプション**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。</span><span class="sxs-lookup"><span data-stu-id="d45ce-122">For more information on mapping conflicts, see **Password Sync Adapter Properties: Options** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>