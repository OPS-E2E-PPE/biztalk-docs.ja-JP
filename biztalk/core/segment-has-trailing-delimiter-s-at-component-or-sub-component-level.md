---
title: セグメントのコンポーネントまたはサブコンポーネント レベルに末尾の区切り記号が |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 517f1cfc-66c1-47e6-be94-2c76c1f89230
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eaf15c3a03933adcfc241cc3f53f50d4f2d8a10a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279747"
---
# <a name="segment-has-trailing-delimiters-at-component-or-sub-component-level"></a><span data-ttu-id="8d984-102">セグメントの末尾の区切り記号がコンポーネントまたはサブコンポーネント レベルにあります</span><span class="sxs-lookup"><span data-stu-id="8d984-102">Segment has trailing delimiter(s) at component or sub-component level</span></span>
## <a name="details"></a><span data-ttu-id="8d984-103">詳細</span><span class="sxs-lookup"><span data-stu-id="8d984-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8d984-104">製品名</span><span class="sxs-lookup"><span data-stu-id="8d984-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8d984-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="8d984-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8d984-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="8d984-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8d984-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="8d984-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8d984-108">EDI</span><span class="sxs-lookup"><span data-stu-id="8d984-108">EDI</span></span> |
|    <span data-ttu-id="8d984-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="8d984-109">Component</span></span>    |                                       <span data-ttu-id="8d984-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="8d984-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="8d984-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="8d984-111">Symbolic Name</span></span>  |                      <span data-ttu-id="8d984-112">X12SeSegmentHasTrailingDelimiterDescription</span><span class="sxs-lookup"><span data-stu-id="8d984-112">X12SeSegmentHasTrailingDelimiterDescription</span></span>                       |
|  <span data-ttu-id="8d984-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="8d984-113">Message Text</span></span>   |         <span data-ttu-id="8d984-114">セグメントの末尾の区切り記号がコンポーネントまたはサブコンポーネント レベルにあります</span><span class="sxs-lookup"><span data-stu-id="8d984-114">Segment has trailing delimiter(s) at component or sub-component level</span></span>          |
  
## <a name="explanation"></a><span data-ttu-id="8d984-115">説明</span><span class="sxs-lookup"><span data-stu-id="8d984-115">Explanation</span></span>  
 <span data-ttu-id="8d984-116">このエラー/警告/情報イベントは、インターチェンジに末尾の区切り記号が含まれており、インターチェンジの受信者としてのパーティに対して末尾の区切り記号が有効化されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="8d984-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the interchange contained trailing delimiters, but trailing delimiters were not enabled for the party as interchange sender.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8d984-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="8d984-117">User Action</span></span>  
 <span data-ttu-id="8d984-118">このエラーを解決するには、次のようにして末尾の区切り記号を有効化します。</span><span class="sxs-lookup"><span data-stu-id="8d984-118">To resolve this error, enable trailing separators as follows:</span></span>  
  
1.  <span data-ttu-id="8d984-119">BizTalk Server 管理コンソールを開き、[パーティ] フォルダーに移動して、パーティの [EDI のプロパティ] を開きます。</span><span class="sxs-lookup"><span data-stu-id="8d984-119">Open the BizTalk Server Administration Console, move to the Parties folder, and open the EDI Properties for the party.</span></span>  
  
2.  <span data-ttu-id="8d984-120">X12 または EDIFACT (該当する方) の検証と確認の生成のページに移動します。</span><span class="sxs-lookup"><span data-stu-id="8d984-120">Move to the Validation and ACK Generation page for X12 or EDIFACT, as appropriate.</span></span>  
  
3.  <span data-ttu-id="8d984-121">[末尾の区切り記号を許可する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d984-121">Click "Allow trailing separators".</span></span>