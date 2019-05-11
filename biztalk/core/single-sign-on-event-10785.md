---
title: シングル サインオン:イベント 10785 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4f4a2ad-a378-4806-ba16-d2872c4773f1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fed42624f0efc2c4ae2d13c35d48ca47a87e35cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65278020"
---
# <a name="single-sign-on-event-10785"></a><span data-ttu-id="74eb6-102">シングル サインオン:イベント 10785</span><span class="sxs-lookup"><span data-stu-id="74eb6-102">Single Sign-On: Event 10785</span></span>
## <a name="details"></a><span data-ttu-id="74eb6-103">詳細</span><span class="sxs-lookup"><span data-stu-id="74eb6-103">Details</span></span>  
  
|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  <span data-ttu-id="74eb6-104">製品名</span><span class="sxs-lookup"><span data-stu-id="74eb6-104">Product Name</span></span>   |                   <span data-ttu-id="74eb6-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="74eb6-105">Enterprise Single Sign-On</span></span>                    |
| <span data-ttu-id="74eb6-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="74eb6-106">Product Version</span></span> |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    <span data-ttu-id="74eb6-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="74eb6-107">Event ID</span></span>     |                             <span data-ttu-id="74eb6-108">10785</span><span class="sxs-lookup"><span data-stu-id="74eb6-108">10785</span></span>                              |
|  <span data-ttu-id="74eb6-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="74eb6-109">Event Source</span></span>   |                             <span data-ttu-id="74eb6-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="74eb6-110">ENTSSO</span></span>                             |
|    <span data-ttu-id="74eb6-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="74eb6-111">Component</span></span>    |                              <span data-ttu-id="74eb6-112">なし</span><span class="sxs-lookup"><span data-stu-id="74eb6-112">N/A</span></span>                               |
|  <span data-ttu-id="74eb6-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="74eb6-113">Symbolic Name</span></span>  |                       <span data-ttu-id="74eb6-114">ENTSSO_E_DB_ACCESS</span><span class="sxs-lookup"><span data-stu-id="74eb6-114">ENTSSO_E_DB_ACCESS</span></span>                       |
|  <span data-ttu-id="74eb6-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="74eb6-115">Message Text</span></span>   | <span data-ttu-id="74eb6-116">SSO データベースへのアクセスを試みているときにエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="74eb6-116">An error occurred while attempting to access the SSO database.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="74eb6-117">説明</span><span class="sxs-lookup"><span data-stu-id="74eb6-117">Explanation</span></span>  
 <span data-ttu-id="74eb6-118">ENTSSO データベースはオフラインの可能性があります。</span><span class="sxs-lookup"><span data-stu-id="74eb6-118">The ENTSSO database may be offline.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="74eb6-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="74eb6-119">User Action</span></span>  
 <span data-ttu-id="74eb6-120">ENTSSO サーバーのイベント ログを確認、システム管理者に依頼します。</span><span class="sxs-lookup"><span data-stu-id="74eb6-120">Have your system administrator check the Event Log on the ENTSSO server.</span></span>