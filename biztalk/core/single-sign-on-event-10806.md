---
title: シングル サインオン:イベント 10806 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c7aee239e10e96147ff19ee29aa83e7578d8a80
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396124"
---
# <a name="single-sign-on-event-10806"></a><span data-ttu-id="04163-102">シングル サインオン:イベント 10806</span><span class="sxs-lookup"><span data-stu-id="04163-102">Single Sign-On: Event 10806</span></span>
## <a name="details"></a><span data-ttu-id="04163-103">詳細</span><span class="sxs-lookup"><span data-stu-id="04163-103">Details</span></span>  
  
|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  <span data-ttu-id="04163-104">製品名</span><span class="sxs-lookup"><span data-stu-id="04163-104">Product Name</span></span>   |                             <span data-ttu-id="04163-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="04163-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="04163-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="04163-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="04163-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="04163-107">Event ID</span></span>     |                                       <span data-ttu-id="04163-108">10806</span><span class="sxs-lookup"><span data-stu-id="04163-108">10806</span></span>                                       |
|  <span data-ttu-id="04163-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="04163-109">Event Source</span></span>   |                                      <span data-ttu-id="04163-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="04163-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="04163-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="04163-111">Component</span></span>    |                                        <span data-ttu-id="04163-112">なし</span><span class="sxs-lookup"><span data-stu-id="04163-112">N/A</span></span>                                        |
|  <span data-ttu-id="04163-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="04163-113">Symbolic Name</span></span>  |                         <span data-ttu-id="04163-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span><span class="sxs-lookup"><span data-stu-id="04163-114">ENTSSO_E_APP_ASSIGNED_TO_ADAPTER</span></span>                          |
|  <span data-ttu-id="04163-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="04163-115">Message Text</span></span>   | <span data-ttu-id="04163-116">現在アダプターに割り当てられているために、アプリケーションを削除できません。</span><span class="sxs-lookup"><span data-stu-id="04163-116">The application cannot be deleted because it is currently assigned to an adapter.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="04163-117">説明</span><span class="sxs-lookup"><span data-stu-id="04163-117">Explanation</span></span>  
 <span data-ttu-id="04163-118">アダプターに割り当てられたとき、アプリケーションを削除できません。</span><span class="sxs-lookup"><span data-stu-id="04163-118">An application cannot be deleted when it is assigned to an adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04163-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="04163-119">User Action</span></span>  
 <span data-ttu-id="04163-120">アダプターからアプリケーションの割り当てを解除してから削除します。</span><span class="sxs-lookup"><span data-stu-id="04163-120">Unassign the application from the adapter, and then delete it.</span></span>