---
title: シングル サインオン:イベント 10589 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fe962bb-e9bb-4107-a5fb-21c180d54e21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160635fe7446a2fbac21edad332b4c87cd86e1b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400167"
---
# <a name="single-sign-on-event-10589"></a><span data-ttu-id="36c5c-102">シングル サインオン:イベント 10589</span><span class="sxs-lookup"><span data-stu-id="36c5c-102">Single Sign-On: Event 10589</span></span>
## <a name="details"></a><span data-ttu-id="36c5c-103">詳細</span><span class="sxs-lookup"><span data-stu-id="36c5c-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="36c5c-104">製品名</span><span class="sxs-lookup"><span data-stu-id="36c5c-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="36c5c-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="36c5c-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="36c5c-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="36c5c-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="36c5c-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="36c5c-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="36c5c-108">10589</span><span class="sxs-lookup"><span data-stu-id="36c5c-108">10589</span></span>                                                                                                                               |
|  <span data-ttu-id="36c5c-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="36c5c-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="36c5c-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="36c5c-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="36c5c-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="36c5c-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="36c5c-112">なし</span><span class="sxs-lookup"><span data-stu-id="36c5c-112">N/A</span></span>                                                                                                                                |
|  <span data-ttu-id="36c5c-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="36c5c-113">Symbolic Name</span></span>  |                                                                                                                 <span data-ttu-id="36c5c-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="36c5c-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span></span>                                                                                                                  |
|  <span data-ttu-id="36c5c-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="36c5c-115">Message Text</span></span>   | <span data-ttu-id="36c5c-116">マスター シークレットがバックアップされていません。</span><span class="sxs-lookup"><span data-stu-id="36c5c-116">The master secret has not been backed up.</span></span> <span data-ttu-id="36c5c-117">マスター シークレットが失われると、SSO システムに保存されたすべての情報が完全に失われます。また、システムが正しく動作しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="36c5c-117">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span> <span data-ttu-id="36c5c-118">SSO 管理ツールを使用して、マスター シークレットをバックアップしてください。</span><span class="sxs-lookup"><span data-stu-id="36c5c-118">Please use the SSO administration tools to back up your master secret.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="36c5c-119">説明</span><span class="sxs-lookup"><span data-stu-id="36c5c-119">Explanation</span></span>  
 <span data-ttu-id="36c5c-120">マスター シークレットがバックアップされていません。</span><span class="sxs-lookup"><span data-stu-id="36c5c-120">The master secret has not been backed up.</span></span> <span data-ttu-id="36c5c-121">マスター シークレットが失われると、SSO システムに保存されたすべての情報が完全に失われます。また、システムが正しく動作しなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="36c5c-121">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="36c5c-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="36c5c-122">User Action</span></span>  
 <span data-ttu-id="36c5c-123">マスター シークレットのバックアップについては、次を参照してください。[マスター シークレットの管理](../core/managing-the-master-secret.md)します。</span><span class="sxs-lookup"><span data-stu-id="36c5c-123">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>