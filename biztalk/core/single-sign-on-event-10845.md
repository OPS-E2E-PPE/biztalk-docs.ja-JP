---
title: 'シングル サインオン: イベント 10845 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 37b8b3c2-ae61-49a1-b171-ca51664f00dd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 237942063a665d7114def55c4ef765a08a1f667b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984363"
---
# <a name="single-sign-on-event-10845"></a><span data-ttu-id="07fd4-102">シングル サインオン: イベント 10845</span><span class="sxs-lookup"><span data-stu-id="07fd4-102">Single Sign-On: Event 10845</span></span>
## <a name="details"></a><span data-ttu-id="07fd4-103">詳細</span><span class="sxs-lookup"><span data-stu-id="07fd4-103">Details</span></span>  
  
|                 |                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="07fd4-104">製品名</span><span class="sxs-lookup"><span data-stu-id="07fd4-104">Product Name</span></span>   |                                               <span data-ttu-id="07fd4-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="07fd4-105">Enterprise Single Sign-On</span></span>                                               |
| <span data-ttu-id="07fd4-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="07fd4-106">Product Version</span></span> |                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                               |
|    <span data-ttu-id="07fd4-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="07fd4-107">Event ID</span></span>     |                                                         <span data-ttu-id="07fd4-108">10845</span><span class="sxs-lookup"><span data-stu-id="07fd4-108">10845</span></span>                                                         |
|  <span data-ttu-id="07fd4-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="07fd4-109">Event Source</span></span>   |                                                        <span data-ttu-id="07fd4-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="07fd4-110">ENTSSO</span></span>                                                         |
|    <span data-ttu-id="07fd4-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="07fd4-111">Component</span></span>    |                                                          <span data-ttu-id="07fd4-112">なし</span><span class="sxs-lookup"><span data-stu-id="07fd4-112">N/A</span></span>                                                          |
|  <span data-ttu-id="07fd4-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="07fd4-113">Symbolic Name</span></span>  |                                                  <span data-ttu-id="07fd4-114">ENTSSO_E_DB_ACCESS2</span><span class="sxs-lookup"><span data-stu-id="07fd4-114">ENTSSO_E_DB_ACCESS2</span></span>                                                  |
|  <span data-ttu-id="07fd4-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="07fd4-115">Message Text</span></span>   | <span data-ttu-id="07fd4-116">SSO データベースへのアクセスを試みているときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="07fd4-116">An error occurred while attempting to access the SSO database.</span></span> <span data-ttu-id="07fd4-117">詳細については、イベント ログ (コンピューター "%1" 上) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="07fd4-117">See the event log (on computer ‘%1’) for more details.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="07fd4-118">説明</span><span class="sxs-lookup"><span data-stu-id="07fd4-118">Explanation</span></span>  
 <span data-ttu-id="07fd4-119">SSO データベースへのアクセスを試みているときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="07fd4-119">An error occurred while attempting to access the SSO database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07fd4-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="07fd4-120">User Action</span></span>  
 <span data-ttu-id="07fd4-121">指定したコンピューターのイベント ログで、SQL Server からの追加情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="07fd4-121">See the event log on the specified computer for additional information from the SQL Server.</span></span>