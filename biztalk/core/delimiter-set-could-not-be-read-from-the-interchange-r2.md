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
ms.openlocfilehash: 778bfa7c417776e5baa78a6103e1075c7ccac27b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996275"
---
# <a name="delimiter-set-could-not-be-read-from-the-interchange-r2"></a><span data-ttu-id="d040b-102">インターチェンジから区切り記号セットを読み込めませんでした (R2)</span><span class="sxs-lookup"><span data-stu-id="d040b-102">Delimiter set could not be read from the interchange (R2)</span></span>
## <a name="details"></a><span data-ttu-id="d040b-103">詳細</span><span class="sxs-lookup"><span data-stu-id="d040b-103">Details</span></span>  

|                 |                                                                                                                           |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="d040b-104">製品名</span><span class="sxs-lookup"><span data-stu-id="d040b-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| <span data-ttu-id="d040b-105">製品バージョン</span><span class="sxs-lookup"><span data-stu-id="d040b-105">Product Version</span></span> |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                 |
|    <span data-ttu-id="d040b-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="d040b-106">Event ID</span></span>     |                                                             -                                                             |
|  <span data-ttu-id="d040b-107">イベント ソース</span><span class="sxs-lookup"><span data-stu-id="d040b-107">Event Source</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d040b-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d040b-108"> EDI</span></span>                   |
|    <span data-ttu-id="d040b-109">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="d040b-109">Component</span></span>    |                                                        <span data-ttu-id="d040b-110">EDI エンジン</span><span class="sxs-lookup"><span data-stu-id="d040b-110">EDI Engine</span></span>                                                         |
|  <span data-ttu-id="d040b-111">シンボル名</span><span class="sxs-lookup"><span data-stu-id="d040b-111">Symbolic Name</span></span>  |                                                             -                                                             |
|  <span data-ttu-id="d040b-112">メッセージ テキスト</span><span class="sxs-lookup"><span data-stu-id="d040b-112">Message Text</span></span>   | <span data-ttu-id="d040b-113">インターチェンジから区切り記号セットを読み込めませんでした。</span><span class="sxs-lookup"><span data-stu-id="d040b-113">Delimiter set could not be read from the interchange.</span></span> <span data-ttu-id="d040b-114">ルート ノードに属性 DelimiterSetSerializedData が見つかりません。</span><span class="sxs-lookup"><span data-stu-id="d040b-114">The attribute DelimiterSetSerializedData is missing from root node.</span></span> |

## <a name="explanation"></a><span data-ttu-id="d040b-115">説明</span><span class="sxs-lookup"><span data-stu-id="d040b-115">Explanation</span></span>  
 <span data-ttu-id="d040b-116">このエラーは、インターチェンジに区切り記号セットの値が含まれていないことを示します。</span><span class="sxs-lookup"><span data-stu-id="d040b-116">This error indicates the interchange does not contain the delimiter set values.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d040b-117">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="d040b-117">User Action</span></span>  
 <span data-ttu-id="d040b-118">このエラーを解決するには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="d040b-118">To resolve this error, do one of the following:</span></span>  

- <span data-ttu-id="d040b-119">次のようにしてインターチェンジに区切り記号セットの値を追加します。</span><span class="sxs-lookup"><span data-stu-id="d040b-119">Add delimiter set values to the interchange, as follows:</span></span>  

  1.  <span data-ttu-id="d040b-120">メッセージを開きます。</span><span class="sxs-lookup"><span data-stu-id="d040b-120">Open up the message.</span></span>  

  2.  <span data-ttu-id="d040b-121">インターチェンジに UNA セグメントが含まれているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d040b-121">Determine whether there is a UNA segment in the interchange.</span></span> <span data-ttu-id="d040b-122">UNA セグメントがない場合は、インターチェンジへの UNA セグメントの追加をパートナーに依頼します。</span><span class="sxs-lookup"><span data-stu-id="d040b-122">If there is not a UNA segment, ask the partner to add the UNA segment to the interchange.</span></span>  

- <span data-ttu-id="d040b-123">次のようにして EfactDelimiters パイプライン プロパティに区切り記号の値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d040b-123">Enter the delimiter values to the EfactDelimiters pipeline property, as follows:</span></span>  

  1. <span data-ttu-id="d040b-124">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールで、プロパティを設定するパイプラインを使用している受信場所または送信ポートを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="d040b-124">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the receive location or send port using the pipeline that you want to set properties for.</span></span> <span data-ttu-id="d040b-125">**[プロパティ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d040b-125">Click **Properties**.</span></span>  

  2. <span data-ttu-id="d040b-126">プロパティを設定する対象のパイプラインの横にある省略記号ボタン ([…]) をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d040b-126">Click the ellipsis button (…) next to the pipeline that you want to set properties for.</span></span>  

  3. <span data-ttu-id="d040b-127">コンマで区切ったリストとして UNA 区切り記号の値を入力し (UNA1、UNA2、UNA3、UNA4、UNA5、および UNA6 用)、必要に応じて既定値を変更します。</span><span class="sxs-lookup"><span data-stu-id="d040b-127">Enter values for the UNA delimiters as a comma-delimited list (for UNA1, UNA2, UNA3, UNA4, UNA5, and UNA6), changing the defaults as required.</span></span> <span data-ttu-id="d040b-128">既定値は、次のとおり: 0x3A、0x2B、0x2C、0x3F、0x20、0x27 します。</span><span class="sxs-lookup"><span data-stu-id="d040b-128">The defaults are as follows: 0x3A, 0x2B, 0x2C, 0x3F, 0x20, 0x27.</span></span>  

  4. <span data-ttu-id="d040b-129">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d040b-129">Click **OK**.</span></span>
