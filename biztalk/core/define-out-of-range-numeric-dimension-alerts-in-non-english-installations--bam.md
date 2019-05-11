---
title: 英語以外のインストールで範囲外の数値ディメンション警告を定義する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7f1e0373-eadf-4c6d-9a38-a34d847f310f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703c59f83e0a9af01bcddbea1358a56aa825037b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352484"
---
# <a name="how-to-define-out-of-range-numeric-dimension-alerts-in-non-english-installations"></a><span data-ttu-id="23481-102">英語以外のインストールで範囲外の数値ディメンション警告を定義する方法</span><span class="sxs-lookup"><span data-stu-id="23481-102">How to Define Out-of-Range Numeric Dimension Alerts In Non-English Installations</span></span>
<span data-ttu-id="23481-103">英語以外のインストールで定義されている数値範囲ディメンション外の値を条件として含むアラートを設定するときに、文字列のローカライズされたバージョンと、BAM 定義を手動で変更する必要があります**の範囲外**.</span><span class="sxs-lookup"><span data-stu-id="23481-103">When setting alerts that include a condition for a value that is outside the defined numeric range dimension on non-English installations, you must manually modify the BAM definition with the localized version of the string **out of range**.</span></span>  
  
 <span data-ttu-id="23481-104">次の表では、ローカライズされた範囲外の値の例を示します。</span><span class="sxs-lookup"><span data-stu-id="23481-104">The following table lists examples of localized out-of-range values.</span></span>  
  
|<span data-ttu-id="23481-105">言語コード</span><span class="sxs-lookup"><span data-stu-id="23481-105">Language code</span></span>|<span data-ttu-id="23481-106">ローカライズされた文字列</span><span class="sxs-lookup"><span data-stu-id="23481-106">Localized string</span></span>|  
|-------------------|----------------------|  
|<span data-ttu-id="23481-107">CN</span><span class="sxs-lookup"><span data-stu-id="23481-107">CN</span></span>|<span data-ttu-id="23481-108">超出范围</span><span class="sxs-lookup"><span data-stu-id="23481-108">超出范围</span></span>|  
|<span data-ttu-id="23481-109">DE</span><span class="sxs-lookup"><span data-stu-id="23481-109">DE</span></span>|<span data-ttu-id="23481-110">Außerhalb des gültigen Bereichs</span><span class="sxs-lookup"><span data-stu-id="23481-110">Außerhalb des gültigen Bereichs</span></span>|  
|<span data-ttu-id="23481-111">ES</span><span class="sxs-lookup"><span data-stu-id="23481-111">ES</span></span>|<span data-ttu-id="23481-112">Fuera de rango</span><span class="sxs-lookup"><span data-stu-id="23481-112">Fuera de rango</span></span>|  
|<span data-ttu-id="23481-113">FR</span><span class="sxs-lookup"><span data-stu-id="23481-113">FR</span></span>|<span data-ttu-id="23481-114">hors で</span><span class="sxs-lookup"><span data-stu-id="23481-114">hors limites</span></span>|  
|<span data-ttu-id="23481-115">その</span><span class="sxs-lookup"><span data-stu-id="23481-115">IT</span></span>|<span data-ttu-id="23481-116">Fuori intervallo</span><span class="sxs-lookup"><span data-stu-id="23481-116">Fuori intervallo</span></span>|  
|<span data-ttu-id="23481-117">JA</span><span class="sxs-lookup"><span data-stu-id="23481-117">JA</span></span>|<span data-ttu-id="23481-118">範囲外</span><span class="sxs-lookup"><span data-stu-id="23481-118">範囲外</span></span>|  
|<span data-ttu-id="23481-119">KO</span><span class="sxs-lookup"><span data-stu-id="23481-119">KO</span></span>|<span data-ttu-id="23481-120">범위를 벗어남</span><span class="sxs-lookup"><span data-stu-id="23481-120">범위를 벗어남</span></span>|  
|<span data-ttu-id="23481-121">TW</span><span class="sxs-lookup"><span data-stu-id="23481-121">TW</span></span>|<span data-ttu-id="23481-122">超過範圍</span><span class="sxs-lookup"><span data-stu-id="23481-122">超過範圍</span></span>|  
  
### <a name="to-define-out-of-range-alerts-in-non-english-installations"></a><span data-ttu-id="23481-123">英語以外のインストールで範囲外のアラートを定義するには</span><span class="sxs-lookup"><span data-stu-id="23481-123">To define out-of-range alerts in non-English installations</span></span>  
  
1.  <span data-ttu-id="23481-124">BAM 定義 xml ファイルを含むフォルダーに移動します。</span><span class="sxs-lookup"><span data-stu-id="23481-124">Navigate to the folder containing your BAM definition xml file.</span></span>  
  
2.  <span data-ttu-id="23481-125">テキスト エディターまたは XML エディターを使用して、BAM 定義ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="23481-125">Using a text editor or an XML editor, open the BAM definition file.</span></span>  
  
3.  <span data-ttu-id="23481-126">数値のディメンションのスライサー ディメンションを探します。</span><span class="sxs-lookup"><span data-stu-id="23481-126">Locate the slicer dimension for the numeric dimension.</span></span> <span data-ttu-id="23481-127">たとえば、スライサー ディメンションの名前は**Alerts_NumDim**、次のノードを検索する場合します。</span><span class="sxs-lookup"><span data-stu-id="23481-127">For example, if your slicer dimension is named **Alerts_NumDim**, you would locate the following node:</span></span>  
  
    ```  
    <SlicerDimension Name="Alerts_NumDim">  
    <Level Name="(Out of Range)" />  
    </SlicerDimension>  
    ```  
  
4.  <span data-ttu-id="23481-128">変更、 **Out of Range**を適切な文字列値がローカライズされた文字列。</span><span class="sxs-lookup"><span data-stu-id="23481-128">Change the **Out of Range** string value to the appropriate localized string.</span></span>  
  
5.  <span data-ttu-id="23481-129">ファイルを保存し、定義を展開します。</span><span class="sxs-lookup"><span data-stu-id="23481-129">Save the file and deploy the definition.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23481-130">参照</span><span class="sxs-lookup"><span data-stu-id="23481-130">See Also</span></span>  
 <span data-ttu-id="23481-131">[BAM 定義スキーマとは何ですか。](../core/what-is-a-bam-definition-schema.md) </span><span class="sxs-lookup"><span data-stu-id="23481-131">[What Is a BAM Definition Schema?](../core/what-is-a-bam-definition-schema.md) </span></span>  
 [<span data-ttu-id="23481-132">BAM 定義を展開する方法</span><span class="sxs-lookup"><span data-stu-id="23481-132">How to Deploy BAM Definitions</span></span>](../core/how-to-deploy-bam-definitions.md)