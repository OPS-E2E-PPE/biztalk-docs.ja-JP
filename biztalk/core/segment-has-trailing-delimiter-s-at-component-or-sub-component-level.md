---
title: "セグメントにコンポーネントまたはサブコンポーネント レベルで末尾の区切り記号は |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 517f1cfc-66c1-47e6-be94-2c76c1f89230
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3eede2923da1ed206a897b879b7b6be589800e4c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="segment-has-trailing-delimiters-at-component-or-sub-component-level"></a><span data-ttu-id="cf95d-102">セグメントの末尾の区切り記号がコンポーネントまたはサブコンポーネント レベルにあります</span><span class="sxs-lookup"><span data-stu-id="cf95d-102">Segment has trailing delimiter(s) at component or sub-component level</span></span>
## <a name="details"></a><span data-ttu-id="cf95d-103">詳細</span><span class="sxs-lookup"><span data-stu-id="cf95d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="cf95d-104">製品名</span><span class="sxs-lookup"><span data-stu-id="cf95d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="cf95d-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="cf95d-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="cf95d-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="cf95d-106">Event ID</span></span>|-|  
|<span data-ttu-id="cf95d-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="cf95d-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="cf95d-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="cf95d-108"> EDI</span></span>|  
|<span data-ttu-id="cf95d-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="cf95d-109">Component</span></span>|<span data-ttu-id="cf95d-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="cf95d-110">EDI Engine</span></span>|  
|<span data-ttu-id="cf95d-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="cf95d-111">Symbolic Name</span></span>|<span data-ttu-id="cf95d-112">X12SeSegmentHasTrailingDelimiterDescription</span><span class="sxs-lookup"><span data-stu-id="cf95d-112">X12SeSegmentHasTrailingDelimiterDescription</span></span>|  
|<span data-ttu-id="cf95d-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="cf95d-113">Message Text</span></span>|<span data-ttu-id="cf95d-114">セグメントの末尾の区切り記号がコンポーネントまたはサブコンポーネント レベルにあります</span><span class="sxs-lookup"><span data-stu-id="cf95d-114">Segment has trailing delimiter(s) at component or sub-component level</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="cf95d-115">説明</span><span class="sxs-lookup"><span data-stu-id="cf95d-115">Explanation</span></span>  
 <span data-ttu-id="cf95d-116">このエラー/警告/情報イベントは、インターチェンジに末尾の区切り記号が含まれており、インターチェンジの受信者としてのパーティに対して末尾の区切り記号が有効化されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="cf95d-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained trailing delimiters, but trailing delimiters were not enabled for the party as interchange sender.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="cf95d-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="cf95d-117">User Action</span></span>  
 <span data-ttu-id="cf95d-118">このエラーを解決するには、次のようにして末尾の区切り記号を有効化します。</span><span class="sxs-lookup"><span data-stu-id="cf95d-118">To resolve this error, enable trailing separators as follows:</span></span>  
  
1.  <span data-ttu-id="cf95d-119">BizTalk Server 管理コンソールを開き、[パーティ] フォルダーに移動して、パーティの [EDI のプロパティ] を開きます。</span><span class="sxs-lookup"><span data-stu-id="cf95d-119">Open the BizTalk Server Administration Console, move to the Parties folder, and open the EDI Properties for the party.</span></span>  
  
2.  <span data-ttu-id="cf95d-120">X12 または EDIFACT (該当する方) の検証と確認の生成のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="cf95d-120">Move to the Validation and ACK Generation page for X12 or EDIFACT, as appropriate.</span></span>  
  
3.  <span data-ttu-id="cf95d-121">[末尾の区切り記号を許可する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf95d-121">Click "Allow trailing separators".</span></span>