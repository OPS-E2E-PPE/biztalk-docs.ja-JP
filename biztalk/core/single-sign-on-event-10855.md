---
title: シングル サインオン:イベント 10855 |Microsoft Docs
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
ms.openlocfilehash: 9519453d0209caf46fa75c1bce52d60fe792d0e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306647"
---
# <a name="single-sign-on-event-10855"></a><span data-ttu-id="c23db-102">シングル サインオン:イベント 10855</span><span class="sxs-lookup"><span data-stu-id="c23db-102">Single Sign-On: Event 10855</span></span>

|                 |                                                                        |
|-----------------|------------------------------------------------------------------------|
|  <span data-ttu-id="c23db-103">製品名</span><span class="sxs-lookup"><span data-stu-id="c23db-103">Product Name</span></span>   |                       <span data-ttu-id="c23db-104">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="c23db-104">Enterprise Single Sign-On</span></span>                        |
| <span data-ttu-id="c23db-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c23db-105">Product Version</span></span> |       [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]       |
|    <span data-ttu-id="c23db-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c23db-106">Event ID</span></span>     |                                 <span data-ttu-id="c23db-107">10855</span><span class="sxs-lookup"><span data-stu-id="c23db-107">10855</span></span>                                  |
|  <span data-ttu-id="c23db-108">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c23db-108">Event Source</span></span>   |                                 <span data-ttu-id="c23db-109">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c23db-109">ENTSSO</span></span>                                 |
|    <span data-ttu-id="c23db-110">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c23db-110">Component</span></span>    |                                  <span data-ttu-id="c23db-111">なし</span><span class="sxs-lookup"><span data-stu-id="c23db-111">N/A</span></span>                                   |
|  <span data-ttu-id="c23db-112">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c23db-112">Symbolic Name</span></span>  |                    <span data-ttu-id="c23db-113">ENTSSO_E_PASSWORD_FILTER_FAILED</span><span class="sxs-lookup"><span data-stu-id="c23db-113">ENTSSO_E_PASSWORD_FILTER_FAILED</span></span>                     |
|  <span data-ttu-id="c23db-114">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c23db-114">Message Text</span></span>   | <span data-ttu-id="c23db-115">資格情報は、パスワード フィルターが失敗したため、返されることはできません。</span><span class="sxs-lookup"><span data-stu-id="c23db-115">The credentials cannot be returned because the password filter failed.</span></span> |

## <a name="explanation"></a><span data-ttu-id="c23db-116">説明</span><span class="sxs-lookup"><span data-stu-id="c23db-116">Explanation</span></span>  
 <span data-ttu-id="c23db-117">パスワード フィルターが無効です。</span><span class="sxs-lookup"><span data-stu-id="c23db-117">The password filter is not valid.</span></span> <span data-ttu-id="c23db-118">これの最も可能性の高い原因は、フィルターが作成されたことを手動では推奨されません。</span><span class="sxs-lookup"><span data-stu-id="c23db-118">The most likely cause of this is that the filter was created manually, which is not recommended.</span></span>  

## <a name="user-action"></a><span data-ttu-id="c23db-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c23db-119">User Action</span></span>  
 <span data-ttu-id="c23db-120">フィルターの作成ウィザードを使用してもう一度パスワード フィルターを作成します。</span><span class="sxs-lookup"><span data-stu-id="c23db-120">Create the password filter again using the Create Filter wizard.</span></span>