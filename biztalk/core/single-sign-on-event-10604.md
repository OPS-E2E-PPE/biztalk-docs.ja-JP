---
title: 'シングル サインオン: イベント 10604 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eea14ab1-5a89-4a62-b414-1bcb36ea339e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0d9d6858fb13542ca642c9c48a8a187b66ba6526
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270546"
---
# <a name="single-sign-on-event-10604"></a><span data-ttu-id="13330-102">シングル サインオン: イベント 10604</span><span class="sxs-lookup"><span data-stu-id="13330-102">Single Sign-On: Event 10604</span></span>
## <a name="details"></a><span data-ttu-id="13330-103">詳細</span><span class="sxs-lookup"><span data-stu-id="13330-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="13330-104">製品名</span><span class="sxs-lookup"><span data-stu-id="13330-104">Product Name</span></span>|<span data-ttu-id="13330-105">エンタープライズ シングル サインオン</span><span class="sxs-lookup"><span data-stu-id="13330-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="13330-106">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="13330-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="13330-107">イベント ID</span><span class="sxs-lookup"><span data-stu-id="13330-107">Event ID</span></span>|<span data-ttu-id="13330-108">10604</span><span class="sxs-lookup"><span data-stu-id="13330-108">10604</span></span>|  
|<span data-ttu-id="13330-109">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="13330-109">Event Source</span></span>|<span data-ttu-id="13330-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="13330-110">ENTSSO</span></span>|  
|<span data-ttu-id="13330-111">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="13330-111">Component</span></span>|<span data-ttu-id="13330-112">なし</span><span class="sxs-lookup"><span data-stu-id="13330-112">N/A</span></span>|  
|<span data-ttu-id="13330-113">シンボル名</span><span class="sxs-lookup"><span data-stu-id="13330-113">Symbolic Name</span></span>|<span data-ttu-id="13330-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span><span class="sxs-lookup"><span data-stu-id="13330-114">SSO_ERROR_SSOCSTX_OUT_OF_PROC</span></span>|  
|<span data-ttu-id="13330-115">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="13330-115">Message Text</span></span>|<span data-ttu-id="13330-116">"ENTSSO Server" COM+ アプリケーションが正しく構成されていません。</span><span class="sxs-lookup"><span data-stu-id="13330-116">The 'ENTSSO Server' COM+ application is not configured correctly.</span></span> <span data-ttu-id="13330-117">COM+ ライブラリ アプリケーションである必要があります。</span><span class="sxs-lookup"><span data-stu-id="13330-117">It must be a COM+ library application.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="13330-118">説明</span><span class="sxs-lookup"><span data-stu-id="13330-118">Explanation</span></span>  
 <span data-ttu-id="13330-119">COM+ アプリケーションは、COM+ ライブラリ アプリケーションとして構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="13330-119">The COM+ application must be configured as a COM+ library application.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="13330-120">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="13330-120">User Action</span></span>  
 <span data-ttu-id="13330-121">ENTSSO MMC スナップインで、COM+ フォルダーを展開し、ENTSSO サーバーを探します。</span><span class="sxs-lookup"><span data-stu-id="13330-121">In the ENTSSO MMC Snap-In, expand the COM+ folder and locate your ENTSSO Server.</span></span> <span data-ttu-id="13330-122">サーバーを右クリックし、[プロパティ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13330-122">Right-click the server, and then click Properties.</span></span> <span data-ttu-id="13330-123">[サーバー アプリケーション] ではなく [ライブラリ アプリケーション] を選択し、[OK] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="13330-123">Select Library Application instead of Server Application, and click OK.</span></span>