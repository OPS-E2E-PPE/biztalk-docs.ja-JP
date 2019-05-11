---
title: (R2) のインターチェンジから区切り記号セットを読み取ることができませんでした。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17bdd32e-d43f-4f59-af27-5d3054fd5432
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7208e9be2d8c5f28420151af060720f72eaa1913
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390222"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a><span data-ttu-id="63935-102">(R2) のインターチェンジから区切り記号セットを読み取ることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="63935-102">Delimiter set could not be read from the interchange (R2)</span></span>
## <a name="details"></a><span data-ttu-id="63935-103">詳細</span><span class="sxs-lookup"><span data-stu-id="63935-103">Details</span></span>  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="63935-104">製品名</span><span class="sxs-lookup"><span data-stu-id="63935-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="63935-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="63935-105">Product Version</span></span> |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                 |
|    <span data-ttu-id="63935-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="63935-106">Event ID</span></span>     |                                                             -                                                             |
|  <span data-ttu-id="63935-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="63935-107">Event Source</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="63935-108">EDI</span><span class="sxs-lookup"><span data-stu-id="63935-108">EDI</span></span>                   |
|    <span data-ttu-id="63935-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="63935-109">Component</span></span>    |                                                        <span data-ttu-id="63935-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="63935-110">EDI Engine</span></span>                                                         |
|  <span data-ttu-id="63935-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="63935-111">Symbolic Name</span></span>  |                                                             -                                                             |
|  <span data-ttu-id="63935-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="63935-112">Message Text</span></span>   | <span data-ttu-id="63935-113">インターチェンジから区切り記号セットを読み取ることができませんでした。</span><span class="sxs-lookup"><span data-stu-id="63935-113">Delimiter set could not be read from the interchange.</span></span> <span data-ttu-id="63935-114">属性 DelimiterSetSerializedData がルート ノードにありません。</span><span class="sxs-lookup"><span data-stu-id="63935-114">The attribute DelimiterSetSerializedData is missing from root node.</span></span> |

## <a name="explanation"></a><span data-ttu-id="63935-115">説明</span><span class="sxs-lookup"><span data-stu-id="63935-115">Explanation</span></span>  
 <span data-ttu-id="63935-116">このエラーは、インターチェンジに区切り記号セットの値が含まれていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="63935-116">This error indicates the interchange does not contain the delimiter set values.</span></span>  

## <a name="user-action"></a><span data-ttu-id="63935-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="63935-117">User Action</span></span>  
 <span data-ttu-id="63935-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="63935-118">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="63935-119">次のように、インターチェンジに区切り記号セットの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="63935-119">Add delimiter set values to the interchange, as follows:</span></span>  

  1.  <span data-ttu-id="63935-120">メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="63935-120">Open up the message.</span></span>  

  2.  <span data-ttu-id="63935-121">インターチェンジの UNA セグメントがあるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="63935-121">Determine whether there is a UNA segment in the interchange.</span></span> <span data-ttu-id="63935-122">UNA セグメントがない場合は、インターチェンジに UNA セグメントを追加するパートナーに問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="63935-122">If there is not a UNA segment, ask the partner to add the UNA segment to the interchange.</span></span>  

- <span data-ttu-id="63935-123">よう、EfactDelimiters パイプライン プロパティの区切り記号の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="63935-123">Enter the delimiter values to the EfactDelimiters pipeline property, as follows:</span></span>  

  1. <span data-ttu-id="63935-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、受信場所を右クリックするか送信ポートのプロパティを設定するパイプラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="63935-124">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="63935-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63935-125">Click **Properties**.</span></span>  

  2. <span data-ttu-id="63935-126">プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63935-126">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  

  3. <span data-ttu-id="63935-127">(UNA1、UNA2、UNA3、UNA4、UNA5、および UNA6) のコンマ区切りのリストとして UNA 区切り記号の値を入力として必要な既定値を変更します。</span><span class="sxs-lookup"><span data-stu-id="63935-127">Enter values for the UNA delimiters as a comma-delimited list (for UNA1, UNA2, UNA3, UNA4, UNA5, and UNA6), changing the defaults as required.</span></span> <span data-ttu-id="63935-128">既定値は次のとおりです。0x3A、0x2B、0x2C、0x3F、0x20、0x27 します。</span><span class="sxs-lookup"><span data-stu-id="63935-128">The defaults are as follows: 0x3A, 0x2B, 0x2C, 0x3F, 0x20, 0x27.</span></span>  

  4. <span data-ttu-id="63935-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="63935-129">Click **OK**.</span></span>
