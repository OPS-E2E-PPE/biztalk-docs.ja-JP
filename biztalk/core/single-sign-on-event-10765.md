---
title: "シングル サインオン: イベント 10765 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e28fe42e-aa2b-4be4-b757-bc9c5c37526b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0fbc04f4c8fc98a87de87a4cd48529a3ca7e2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10765"></a><span data-ttu-id="0a7f8-102">シングル サインオン: イベント 10765</span><span class="sxs-lookup"><span data-stu-id="0a7f8-102">Single Sign-On: Event 10765</span></span>
## <a name="details"></a><span data-ttu-id="0a7f8-103">詳細</span><span class="sxs-lookup"><span data-stu-id="0a7f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="0a7f8-104">製品名</span><span class="sxs-lookup"><span data-stu-id="0a7f8-104">Product Name</span></span>|<span data-ttu-id="0a7f8-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="0a7f8-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="0a7f8-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="0a7f8-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="0a7f8-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="0a7f8-107">Event ID</span></span>|<span data-ttu-id="0a7f8-108">10765</span><span class="sxs-lookup"><span data-stu-id="0a7f8-108">10765</span></span>|  
|<span data-ttu-id="0a7f8-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="0a7f8-109">Event Source</span></span>|<span data-ttu-id="0a7f8-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="0a7f8-110">ENTSSO</span></span>|  
|<span data-ttu-id="0a7f8-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="0a7f8-111">Component</span></span>|<span data-ttu-id="0a7f8-112">なし</span><span class="sxs-lookup"><span data-stu-id="0a7f8-112">N/A</span></span>|  
|<span data-ttu-id="0a7f8-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="0a7f8-113">Symbolic Name</span></span>|<span data-ttu-id="0a7f8-114">ENTSSO_E_NO_CREDENTIALS</span><span class="sxs-lookup"><span data-stu-id="0a7f8-114">ENTSSO_E_NO_CREDENTIALS</span></span>|  
|<span data-ttu-id="0a7f8-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="0a7f8-115">Message Text</span></span>|<span data-ttu-id="0a7f8-116">マッピングに対して資格情報が設定されていません。</span><span class="sxs-lookup"><span data-stu-id="0a7f8-116">No credentials have been set for the mapping.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="0a7f8-117">説明</span><span class="sxs-lookup"><span data-stu-id="0a7f8-117">Explanation</span></span>  
 <span data-ttu-id="0a7f8-118">マッピングに対して GetCredentials が要求されましたが、指定されたマッピングには資格情報がありません。</span><span class="sxs-lookup"><span data-stu-id="0a7f8-118">You have requested a GetCredentials on a mapping, and the mapping specified has no credentials.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0a7f8-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="0a7f8-119">User Action</span></span>  
 <span data-ttu-id="0a7f8-120">コマンド ラインまたは MMC スナップインを使用して、マッピングに資格情報を設定します。</span><span class="sxs-lookup"><span data-stu-id="0a7f8-120">Use the command line or the MMC Snap-in to set credentials for the mapping.</span></span>