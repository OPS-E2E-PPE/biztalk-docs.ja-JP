---
title: 無効なコンポーネント要素区切り記号 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 738a1107-86e6-4475-a61d-ed1d9ab7e5d2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa8896a68f0621437bba07429ce87bdbbbc03a9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381420"
---
# <a name="invalid-component-element-separator"></a><span data-ttu-id="c404e-102">コンポーネント要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="c404e-102">Invalid Component Element Separator</span></span>
## <a name="details"></a><span data-ttu-id="c404e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="c404e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c404e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="c404e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c404e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="c404e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c404e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="c404e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c404e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="c404e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c404e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="c404e-108">EDI</span></span> |
|    <span data-ttu-id="c404e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="c404e-109">Component</span></span>    |                                       <span data-ttu-id="c404e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="c404e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c404e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="c404e-111">Symbolic Name</span></span>  |                   <span data-ttu-id="c404e-112">X12Ta1InvalidComponentElementSeparatorDescription\\</span><span class="sxs-lookup"><span data-stu-id="c404e-112">X12Ta1InvalidComponentElementSeparatorDescription\\</span></span>                   |
|  <span data-ttu-id="c404e-113">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="c404e-113">Message Text</span></span>   |                          <span data-ttu-id="c404e-114">コンポーネント要素区切り記号が無効です。</span><span class="sxs-lookup"><span data-stu-id="c404e-114">Invalid Component Element Separator</span></span>                           |
  
## <a name="explanation"></a><span data-ttu-id="c404e-115">説明</span><span class="sxs-lookup"><span data-stu-id="c404e-115">Explanation</span></span>  
 <span data-ttu-id="c404e-116">このエラー/警告/情報イベントは、インターチェンジ内のコンポーネントの区切り記号の値が ASCII 文字セット内の文字に制限されていなかったため、受信パイプラインで受信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="c404e-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because the value of the component separator in the interchange was not limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="c404e-117">X12 では、セグメント終端記号は ISA16 フィールドです。</span><span class="sxs-lookup"><span data-stu-id="c404e-117">In X12, the segment terminator is the ISA16 field.</span></span> <span data-ttu-id="c404e-118">EDIFACT では、セグメント終端記号は UNA1 フィールドです。</span><span class="sxs-lookup"><span data-stu-id="c404e-118">In EDIFACT, the segment terminator is the UNA1 field.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c404e-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="c404e-119">User Action</span></span>  
 <span data-ttu-id="c404e-120">このエラーを解決するには、セグメントの区切り記号 (X12 インターチェンジの ISA16 フィールド、または EDIFACT インターチェンジの UNA1 フィールド) が、ASCII 文字セットの文字に制限されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c404e-120">To resolve this error, make sure that the segment terminator (the ISA16 field in an X12 interchange or the UNA1 field in an EDIFACT interchange) is limited to the characters in the ASCII character set.</span></span> <span data-ttu-id="c404e-121">インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="c404e-121">Have the interchange resent.</span></span>