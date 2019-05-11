---
title: 区切り記号が一意でない、セグメントとコンポーネント区切り記号が同じ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13c41899-02af-4678-a4ad-f3dc48c1fdfb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cace49910e37381b4fd75660a9584a8fa530f477
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352147"
---
# <a name="delimiters-are-not-unique-segment-and-component-separators-are-the-same"></a><span data-ttu-id="6989e-102">区切り記号が一意ではなく、セグメントとコンポーネントの区切り記号が同じです</span><span class="sxs-lookup"><span data-stu-id="6989e-102">Delimiters are not unique, segment and component separators are the same</span></span>
## <a name="details"></a><span data-ttu-id="6989e-103">詳細</span><span class="sxs-lookup"><span data-stu-id="6989e-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="6989e-104">製品名</span><span class="sxs-lookup"><span data-stu-id="6989e-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="6989e-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="6989e-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="6989e-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6989e-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="6989e-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="6989e-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="6989e-108">EDI</span><span class="sxs-lookup"><span data-stu-id="6989e-108">EDI</span></span> |
|    <span data-ttu-id="6989e-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="6989e-109">Component</span></span>    |                                       <span data-ttu-id="6989e-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="6989e-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="6989e-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="6989e-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="6989e-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="6989e-112">Message Text</span></span>   |        <span data-ttu-id="6989e-113">区切り記号が一意ではなく、セグメントとコンポーネントの区切り記号が同じです</span><span class="sxs-lookup"><span data-stu-id="6989e-113">Delimiters are not unique, segment and component separators are the same</span></span>        |
  
## <a name="explanation"></a><span data-ttu-id="6989e-114">説明</span><span class="sxs-lookup"><span data-stu-id="6989e-114">Explanation</span></span>  
 <span data-ttu-id="6989e-115">このエラー/警告/情報イベントは、セグメント終端記号とコンポーネント区切り記号が同じ値であったため、EDI 送信パイプラインで送信インターチェンジを処理できなかったことを示します。</span><span class="sxs-lookup"><span data-stu-id="6989e-115">This Error/Warning/Information event indicates that the EDI send pipeline could not process an outgoing interchange because the segment terminator or the component separator were the same value.</span></span> <span data-ttu-id="6989e-116">X12 インターチェンジでは、セグメント終端記号は ISA セグメントの最後の文字位置にある文字であり、コンポーネント区切り記号は ISA16 フィールド内の文字です。</span><span class="sxs-lookup"><span data-stu-id="6989e-116">In an X12 interchange, the segment terminator is character in the last character position of the ISA segment and the component separator is the character in the ISA16 field.</span></span> <span data-ttu-id="6989e-117">EDIFACT インターチェンジでは、セグメント終端記号は UNA6 フィールド内の文字であり、コンポーネント区切り記号は UNA1 フィールド内の文字です。</span><span class="sxs-lookup"><span data-stu-id="6989e-117">In an EDIFACT interchange, the segment terminator is the character in the UNA6 field and the component separator is the character in the UNA1 field.</span></span> <span data-ttu-id="6989e-118">保存されたバッチ シナリオでは、同じ値を持つ 2 つの区切り記号が存在する (ただし、エラー状態を引き起こす) 可能性があります。つまり、インターチェンジがパススルー送信を経由して受信され、次にメッセージ ボックス内の XML ファイルとして送信ポートによって取得される場合です。</span><span class="sxs-lookup"><span data-stu-id="6989e-118">Two separators with the same value can occur (but will cause an error condition) in a preserved batch scenario, or if an interchange is received via a passthrough transmit and then picked up by the send port as an XML file in the MessageBox.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6989e-119">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="6989e-119">User Action</span></span>  
 <span data-ttu-id="6989e-120">このエラーを解決するには、インターチェンジのセグメント終端記号またはコンポーネント区切り記号のいずれかの値を変更し、インターチェンジを再送信します。</span><span class="sxs-lookup"><span data-stu-id="6989e-120">To resolve this error, change the value of either the segment terminator or the component separator in the interchange, and then resubmit the interchange.</span></span>