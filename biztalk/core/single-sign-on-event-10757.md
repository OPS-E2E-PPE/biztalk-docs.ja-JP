---
title: シングル サインオン:イベント 10757 |Microsoft Docs
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
ms.openlocfilehash: 8f62cdb2cbf0e5c3ba3477fdfc79376d1c22d3d2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65307711"
---
# <a name="single-sign-on-event-10757"></a><span data-ttu-id="bfb91-102">シングル サインオン:イベント 10757</span><span class="sxs-lookup"><span data-stu-id="bfb91-102">Single Sign-On: Event 10757</span></span>
## <a name="details"></a><span data-ttu-id="bfb91-103">詳細</span><span class="sxs-lookup"><span data-stu-id="bfb91-103">Details</span></span>  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="bfb91-104">製品名</span><span class="sxs-lookup"><span data-stu-id="bfb91-104">Product Name</span></span>   |                                  <span data-ttu-id="bfb91-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="bfb91-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="bfb91-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="bfb91-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    <span data-ttu-id="bfb91-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="bfb91-107">Event ID</span></span>     |                                            <span data-ttu-id="bfb91-108">10757</span><span class="sxs-lookup"><span data-stu-id="bfb91-108">10757</span></span>                                             |
|  <span data-ttu-id="bfb91-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="bfb91-109">Event Source</span></span>   |                                            <span data-ttu-id="bfb91-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="bfb91-110">ENTSSO</span></span>                                            |
|    <span data-ttu-id="bfb91-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="bfb91-111">Component</span></span>    |                                             <span data-ttu-id="bfb91-112">なし</span><span class="sxs-lookup"><span data-stu-id="bfb91-112">N/A</span></span>                                              |
|  <span data-ttu-id="bfb91-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="bfb91-113">Symbolic Name</span></span>  |                                     <span data-ttu-id="bfb91-114">ENTSSO_E_NO_MAPPING</span><span class="sxs-lookup"><span data-stu-id="bfb91-114">ENTSSO_E_NO_MAPPING</span></span>                                      |
|  <span data-ttu-id="bfb91-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="bfb91-115">Message Text</span></span>   | <span data-ttu-id="bfb91-116">マッピングが存在しません。</span><span class="sxs-lookup"><span data-stu-id="bfb91-116">The mapping does not exist.</span></span> <span data-ttu-id="bfb91-117">構成ストア アプリケーションの場合は、構成情報が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="bfb91-117">For Config Store applications, the config info has not been set.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="bfb91-118">説明</span><span class="sxs-lookup"><span data-stu-id="bfb91-118">Explanation</span></span>  
 <span data-ttu-id="bfb91-119">これが単独アプリケーションまたはグループ アプリケーションである場合は、マッピングは存在しません。</span><span class="sxs-lookup"><span data-stu-id="bfb91-119">If this is an Individual or Group type application, then the mapping does not exist.</span></span>  
  
 <span data-ttu-id="bfb91-120">これが構成ストア アプリケーションである場合は、構成データが設定されていません。</span><span class="sxs-lookup"><span data-stu-id="bfb91-120">If this is a Config Store application, then the configuration data has not been set.</span></span> <span data-ttu-id="bfb91-121">このような状況は、SSO データベースが再初期化されているが、BizTalk 管理データベースは再初期化されていない場合、またはその逆の場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="bfb91-121">This can occur when the SSO database has been reinitialized but the BizTalk Management database has not, or vice versa.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="bfb91-122">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="bfb91-122">User Action</span></span>  
 <span data-ttu-id="bfb91-123">これが単独アプリケーションまたはグループ アプリケーションである場合は、目的のマッピングを作成します。</span><span class="sxs-lookup"><span data-stu-id="bfb91-123">If this is an Individual or Group type application, create the desired mapping.</span></span> <span data-ttu-id="bfb91-124">詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)します。</span><span class="sxs-lookup"><span data-stu-id="bfb91-124">For more information, see [How to Create User Mappings](../core/how-to-create-user-mappings.md).</span></span>