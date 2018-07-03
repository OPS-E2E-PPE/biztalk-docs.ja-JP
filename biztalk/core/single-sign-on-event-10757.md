---
title: 'シングル サインオン: イベント 10757 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 08a75a95a3804ee429baaf24c6b89bbb68a0ce6a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008147"
---
# <a name="single-sign-on-event-10757"></a><span data-ttu-id="7a5e1-102">シングル サインオン: イベント 10757</span><span class="sxs-lookup"><span data-stu-id="7a5e1-102">Single Sign-On: Event 10757</span></span>
## <a name="details"></a><span data-ttu-id="7a5e1-103">詳細</span><span class="sxs-lookup"><span data-stu-id="7a5e1-103">Details</span></span>  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="7a5e1-104">製品名</span><span class="sxs-lookup"><span data-stu-id="7a5e1-104">Product Name</span></span>   |                                  <span data-ttu-id="7a5e1-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="7a5e1-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="7a5e1-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="7a5e1-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    <span data-ttu-id="7a5e1-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="7a5e1-107">Event ID</span></span>     |                                            <span data-ttu-id="7a5e1-108">10757</span><span class="sxs-lookup"><span data-stu-id="7a5e1-108">10757</span></span>                                             |
|  <span data-ttu-id="7a5e1-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="7a5e1-109">Event Source</span></span>   |                                            <span data-ttu-id="7a5e1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="7a5e1-110">ENTSSO</span></span>                                            |
|    <span data-ttu-id="7a5e1-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7a5e1-111">Component</span></span>    |                                             <span data-ttu-id="7a5e1-112">なし</span><span class="sxs-lookup"><span data-stu-id="7a5e1-112">N/A</span></span>                                              |
|  <span data-ttu-id="7a5e1-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="7a5e1-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="7a5e1-114">ENTSSO_E_NO_MAPPING</span><span class="sxs-lookup"><span data-stu-id="7a5e1-114">ENTSSO_E_NO_MAPPING</span></span>                                      |
|  <span data-ttu-id="7a5e1-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="7a5e1-115">Message Text</span></span>   | <span data-ttu-id="7a5e1-116">マッピングが存在しません。</span><span class="sxs-lookup"><span data-stu-id="7a5e1-116">The mapping does not exist.</span></span> <span data-ttu-id="7a5e1-117">構成ストア アプリケーションの場合は、構成情報が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="7a5e1-117">For Config Store applications, the config info has not been set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="7a5e1-118">説明</span><span class="sxs-lookup"><span data-stu-id="7a5e1-118">Explanation</span></span>  
 <span data-ttu-id="7a5e1-119">これが単独アプリケーションまたはグループ アプリケーションである場合は、マッピングは存在しません。</span><span class="sxs-lookup"><span data-stu-id="7a5e1-119">If this is an Individual or Group type application, then the mapping does not exist.</span></span>  
  
 <span data-ttu-id="7a5e1-120">これが構成ストア アプリケーションである場合は、構成データが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="7a5e1-120">If this is a Config Store application, then the configuration data has not been set.</span></span> <span data-ttu-id="7a5e1-121">このような状況は、SSO データベースが再初期化されているが、BizTalk 管理データベースは再初期化されていない場合、またはその逆の場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="7a5e1-121">This can occur when the SSO database has been reinitialized but the BizTalk Management database has not, or vice versa.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7a5e1-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="7a5e1-122">User Action</span></span>  
 <span data-ttu-id="7a5e1-123">これが単独アプリケーションまたはグループ アプリケーションである場合は、目的のマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="7a5e1-123">If this is an Individual or Group type application, create the desired mapping.</span></span> <span data-ttu-id="7a5e1-124">詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)します。</span><span class="sxs-lookup"><span data-stu-id="7a5e1-124">For more information, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>