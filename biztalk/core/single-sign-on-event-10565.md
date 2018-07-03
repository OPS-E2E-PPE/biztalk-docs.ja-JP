---
title: 'シングル サインオン: イベント 10565 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d279491-dc0d-44c4-a77e-a67498a3481d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d31b639853b845169c3360ec6367aee120a266d1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008003"
---
# <a name="single-sign-on-event-10565"></a><span data-ttu-id="3a3eb-102">シングル サインオン: イベント 10565</span><span class="sxs-lookup"><span data-stu-id="3a3eb-102">Single Sign-On: Event 10565</span></span>
## <a name="details"></a><span data-ttu-id="3a3eb-103">詳細</span><span class="sxs-lookup"><span data-stu-id="3a3eb-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3a3eb-104">製品名</span><span class="sxs-lookup"><span data-stu-id="3a3eb-104">Product Name</span></span>   |                                                                                           <span data-ttu-id="3a3eb-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3a3eb-105">Enterprise Single Sign-On</span></span>                                                                                           |
| <span data-ttu-id="3a3eb-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3a3eb-106">Product Version</span></span> |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                           |
|    <span data-ttu-id="3a3eb-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3a3eb-107">Event ID</span></span>     |                                                                                                     <span data-ttu-id="3a3eb-108">10565</span><span class="sxs-lookup"><span data-stu-id="3a3eb-108">10565</span></span>                                                                                                     |
|  <span data-ttu-id="3a3eb-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3a3eb-109">Event Source</span></span>   |                                                                                                    <span data-ttu-id="3a3eb-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3a3eb-110">ENTSSO</span></span>                                                                                                     |
|    <span data-ttu-id="3a3eb-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3a3eb-111">Component</span></span>    |                                                                                                      <span data-ttu-id="3a3eb-112">なし</span><span class="sxs-lookup"><span data-stu-id="3a3eb-112">N/A</span></span>                                                                                                      |
|  <span data-ttu-id="3a3eb-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3a3eb-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="3a3eb-114">SSO_ERROR_SECRET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="3a3eb-114">SSO_ERROR_SECRET_VALIDATE_FAILED</span></span>                                                                                        |
|  <span data-ttu-id="3a3eb-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3a3eb-115">Message Text</span></span>   | <span data-ttu-id="3a3eb-116">シークレットをレジストリから読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="3a3eb-116">The secret could not be loaded from the registry.</span></span> <span data-ttu-id="3a3eb-117">SSO サービスのサービス アカウントが変更されたか、シークレットが壊れている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a3eb-117">The service account for the SSO service may have been changed or the secret may be corrupted.</span></span> <span data-ttu-id="3a3eb-118">バックアップ ファイルからシークレットを復元してください。%r</span><span class="sxs-lookup"><span data-stu-id="3a3eb-118">Restore the secret from a backup file.%r</span></span><br /><br /> <span data-ttu-id="3a3eb-119">MSID: %1</span><span class="sxs-lookup"><span data-stu-id="3a3eb-119">MSID: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="3a3eb-120">説明</span><span class="sxs-lookup"><span data-stu-id="3a3eb-120">Explanation</span></span>  
 <span data-ttu-id="3a3eb-121">システムの管理者が、SSO サービス アカウントを変更し、暗号化を解除できないようにしている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3a3eb-121">It is likely that an administrator in the system has changed the SSO Service account, making decryption impossible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3a3eb-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3a3eb-122">User Action</span></span>  
 <span data-ttu-id="3a3eb-123">SSO サービス アカウントを変更した管理者を見つけて、バックアップ ファイルからシークレットを復元します。</span><span class="sxs-lookup"><span data-stu-id="3a3eb-123">Find the person who changed the SSO Service account, and then restore the secret from a backup file.</span></span> <span data-ttu-id="3a3eb-124">シークレットを復元する方法の詳細については、次を参照してください。[マスター シークレットの管理](../core/managing-the-master-secret.md)します。</span><span class="sxs-lookup"><span data-stu-id="3a3eb-124">For more information on restoring the secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>