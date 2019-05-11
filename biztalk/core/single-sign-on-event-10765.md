---
title: シングル サインオン:イベント 10765 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f509bb4a00bc4f1e77b09fa0b93ccaf7d50ad0ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394303"
---
# <a name="single-sign-on-event-10765"></a><span data-ttu-id="77fcd-102">シングル サインオン:イベント 10765</span><span class="sxs-lookup"><span data-stu-id="77fcd-102">Single Sign-On: Event 10765</span></span>
## <a name="details"></a><span data-ttu-id="77fcd-103">詳細</span><span class="sxs-lookup"><span data-stu-id="77fcd-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="77fcd-104">製品名</span><span class="sxs-lookup"><span data-stu-id="77fcd-104">Product Name</span></span>   |                 <span data-ttu-id="77fcd-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="77fcd-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="77fcd-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="77fcd-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="77fcd-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="77fcd-107">Event ID</span></span>     |                           <span data-ttu-id="77fcd-108">10765</span><span class="sxs-lookup"><span data-stu-id="77fcd-108">10765</span></span>                            |
|  <span data-ttu-id="77fcd-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="77fcd-109">Event Source</span></span>   |                           <span data-ttu-id="77fcd-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="77fcd-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="77fcd-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="77fcd-111">Component</span></span>    |                            <span data-ttu-id="77fcd-112">なし</span><span class="sxs-lookup"><span data-stu-id="77fcd-112">N/A</span></span>                             |
|  <span data-ttu-id="77fcd-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="77fcd-113">Symbolic Name</span></span>  |                  <span data-ttu-id="77fcd-114">ENTSSO_E_NO_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="77fcd-114">ENTSSO_E_NO_CREDENTIALS</span></span>                   |
|  <span data-ttu-id="77fcd-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="77fcd-115">Message Text</span></span>   |       <span data-ttu-id="77fcd-116">マッピングの資格情報が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="77fcd-116">No credentials have been set for the mapping.</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="77fcd-117">説明</span><span class="sxs-lookup"><span data-stu-id="77fcd-117">Explanation</span></span>  
 <span data-ttu-id="77fcd-118">マッピングに対して getcredentials が要求したされ、指定されたマッピングには、資格情報はありません。</span><span class="sxs-lookup"><span data-stu-id="77fcd-118">You have requested a GetCredentials on a mapping, and the mapping specified has no credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77fcd-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="77fcd-119">User Action</span></span>  
 <span data-ttu-id="77fcd-120">コマンドラインまたは MMC スナップインを使用して、マッピングの資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="77fcd-120">Use the command line or the MMC Snap-in to set credentials for the mapping.</span></span>