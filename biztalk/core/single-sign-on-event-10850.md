---
title: シングル サインオン:イベント 10850 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04e2af52-d35b-491a-a983-d80442dd6aef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5bd240e9176465c431ca13a5069c3d510f7c2d1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65306666"
---
# <a name="single-sign-on-event-10850"></a><span data-ttu-id="41408-102">シングル サインオン:イベント 10850</span><span class="sxs-lookup"><span data-stu-id="41408-102">Single Sign-On: Event 10850</span></span>
## <a name="details"></a><span data-ttu-id="41408-103">詳細</span><span class="sxs-lookup"><span data-stu-id="41408-103">Details</span></span>  
  
|                 |                                                                     |
|-----------------|---------------------------------------------------------------------|
|  <span data-ttu-id="41408-104">製品名</span><span class="sxs-lookup"><span data-stu-id="41408-104">Product Name</span></span>   |                      <span data-ttu-id="41408-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="41408-105">Enterprise Single Sign-On</span></span>                      |
| <span data-ttu-id="41408-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="41408-106">Product Version</span></span> |     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]      |
|    <span data-ttu-id="41408-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="41408-107">Event ID</span></span>     |                                <span data-ttu-id="41408-108">10850</span><span class="sxs-lookup"><span data-stu-id="41408-108">10850</span></span>                                |
|  <span data-ttu-id="41408-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="41408-109">Event Source</span></span>   |                               <span data-ttu-id="41408-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="41408-110">ENTSSO</span></span>                                |
|    <span data-ttu-id="41408-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="41408-111">Component</span></span>    |                                 <span data-ttu-id="41408-112">なし</span><span class="sxs-lookup"><span data-stu-id="41408-112">N/A</span></span>                                 |
|  <span data-ttu-id="41408-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="41408-113">Symbolic Name</span></span>  |                 <span data-ttu-id="41408-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span><span class="sxs-lookup"><span data-stu-id="41408-114">ENTSSO_E_ENABLED_NOT_ALLOWED_CREATE</span></span>                 |
|  <span data-ttu-id="41408-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="41408-115">Message Text</span></span>   | <span data-ttu-id="41408-116">'Enabled' フラグを指定には、アプリケーションを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="41408-116">An application cannot be created with the 'enabled' flag specified.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="41408-117">説明</span><span class="sxs-lookup"><span data-stu-id="41408-117">Explanation</span></span>  
 <span data-ttu-id="41408-118">アプリケーションを有効にする前にアプリケーションを作成しての各フィールド (UserID および Password) のフィールド情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41408-118">Before enabling an application, it is necessary to both create the application and enter the field information for each of its fields (i.e. UserID and Password).</span></span> <span data-ttu-id="41408-119">"Enabled"フィールドで、アプリケーションを作成することは既に設定されています。</span><span class="sxs-lookup"><span data-stu-id="41408-119">It is not possible to create an application with the “enabled” field already set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="41408-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="41408-120">User Action</span></span>  
 <span data-ttu-id="41408-121">もう一度アプリケーションを作成する (を使用してアプリケーションの作成 API または新しい関連アプリケーション作成ウィザードのいずれか)。</span><span class="sxs-lookup"><span data-stu-id="41408-121">Create the application again (using either the Create Application API or the Create New Affiliate Application Wizard).</span></span> <span data-ttu-id="41408-122">アプリケーションが完了して、フィールドに入力すると、アプリケーションを有効にされます。</span><span class="sxs-lookup"><span data-stu-id="41408-122">When the application is complete and the fields populated, enable the application.</span></span>