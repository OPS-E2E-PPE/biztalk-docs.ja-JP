---
title: 'シングル サインオン: イベント 10855 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba244f8e-bc61-475f-913c-475ebf1c69ee
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89bbdb3c004dc7533be9b7f6371ec69b67bde532
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276922"
---
# <a name="single-sign-on-event-10855"></a><span data-ttu-id="3bd26-102">シングル サインオン: イベント 10855</span><span class="sxs-lookup"><span data-stu-id="3bd26-102">Single Sign-On: Event 10855</span></span>
|||  
|-|-|  
|<span data-ttu-id="3bd26-103">製品名</span><span class="sxs-lookup"><span data-stu-id="3bd26-103">Product Name</span></span>|<span data-ttu-id="3bd26-104">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="3bd26-104">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="3bd26-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="3bd26-105">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="3bd26-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="3bd26-106">Event ID</span></span>|<span data-ttu-id="3bd26-107">10855</span><span class="sxs-lookup"><span data-stu-id="3bd26-107">10855</span></span>|  
|<span data-ttu-id="3bd26-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="3bd26-108">Event Source</span></span>|<span data-ttu-id="3bd26-109">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="3bd26-109">ENTSSO</span></span>|  
|<span data-ttu-id="3bd26-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3bd26-110">Component</span></span>|<span data-ttu-id="3bd26-111">なし</span><span class="sxs-lookup"><span data-stu-id="3bd26-111">N/A</span></span>|  
|<span data-ttu-id="3bd26-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="3bd26-112">Symbolic Name</span></span>|<span data-ttu-id="3bd26-113">ENTSSO_E_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="3bd26-113">ENTSSO_E_PASSWORD_FILTER_FAILED</span></span>|  
|<span data-ttu-id="3bd26-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="3bd26-114">Message Text</span></span>|<span data-ttu-id="3bd26-115">パスワード フィルターが失敗したため、資格情報を返すことができません。</span><span class="sxs-lookup"><span data-stu-id="3bd26-115">The credentials cannot be returned because the password filter failed.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="3bd26-116">説明</span><span class="sxs-lookup"><span data-stu-id="3bd26-116">Explanation</span></span>  
 <span data-ttu-id="3bd26-117">パスワード フィルターが有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="3bd26-117">The password filter is not valid.</span></span> <span data-ttu-id="3bd26-118">最も可能性が高い原因は、フィルターを手動で作成したことです。これは推奨されていません。</span><span class="sxs-lookup"><span data-stu-id="3bd26-118">The most likely cause of this is that the filter was created manually, which is not recommended.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="3bd26-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="3bd26-119">User Action</span></span>  
 <span data-ttu-id="3bd26-120">フィルターの作成ウィザードを使用して、もう一度パスワード フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="3bd26-120">Create the password filter again using the Create Filter wizard.</span></span>