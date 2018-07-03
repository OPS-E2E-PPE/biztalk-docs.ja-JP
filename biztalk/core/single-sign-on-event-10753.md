---
title: 'シングル サインオン: イベント 10753 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6b538083-180b-4a15-bedf-aac4fc351c30
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10fb7980b8c039c6ef02e52952564c581e88054b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969083"
---
# <a name="single-sign-on-event-10753"></a><span data-ttu-id="74097-102">シングル サインオン: イベント 10753</span><span class="sxs-lookup"><span data-stu-id="74097-102">Single Sign-On: Event 10753</span></span>
## <a name="details"></a><span data-ttu-id="74097-103">詳細</span><span class="sxs-lookup"><span data-stu-id="74097-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="74097-104">製品名</span><span class="sxs-lookup"><span data-stu-id="74097-104">Product Name</span></span>   |                 <span data-ttu-id="74097-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="74097-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="74097-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="74097-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="74097-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="74097-107">Event ID</span></span>     |                           <span data-ttu-id="74097-108">10753</span><span class="sxs-lookup"><span data-stu-id="74097-108">10753</span></span>                            |
|  <span data-ttu-id="74097-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="74097-109">Event Source</span></span>   |                           <span data-ttu-id="74097-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="74097-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="74097-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="74097-111">Component</span></span>    |                            <span data-ttu-id="74097-112">なし</span><span class="sxs-lookup"><span data-stu-id="74097-112">N/A</span></span>                             |
|  <span data-ttu-id="74097-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="74097-113">Symbolic Name</span></span>  |                  <span data-ttu-id="74097-114">ENTSSO_E_MAPPING_EXISTS</span><span class="sxs-lookup"><span data-stu-id="74097-114">ENTSSO_E_MAPPING_EXISTS</span></span>                   |
|  <span data-ttu-id="74097-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="74097-115">Message Text</span></span>   |                <span data-ttu-id="74097-116">マッピングは既に存在します。</span><span class="sxs-lookup"><span data-stu-id="74097-116">The mapping already exists.</span></span>                 |
  
## <a name="explanation"></a><span data-ttu-id="74097-117">説明</span><span class="sxs-lookup"><span data-stu-id="74097-117">Explanation</span></span>  
 <span data-ttu-id="74097-118">このマッピングは、使用中の Windows アカウントまたは外部アカウントに既に存在しています。</span><span class="sxs-lookup"><span data-stu-id="74097-118">This mapping already exists, either on the Windows account already in use or the external account.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74097-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="74097-119">User Action</span></span>  
 <span data-ttu-id="74097-120">既存のマッピングおよび作成しようとしているマッピングを確認します。</span><span class="sxs-lookup"><span data-stu-id="74097-120">Check the existing mappings and the mapping you are trying to create.</span></span> <span data-ttu-id="74097-121">必要なマッピングが既に存在している場合は、そのマッピングを使用し、新しいマッピングを削除します。</span><span class="sxs-lookup"><span data-stu-id="74097-121">If the mapping you want already exists, use it and delete your new one.</span></span> <span data-ttu-id="74097-122">マッピングが存在しない場合は、新しいマッピングを削除して作成し直します。</span><span class="sxs-lookup"><span data-stu-id="74097-122">If not, delete your new one and recreate it.</span></span>