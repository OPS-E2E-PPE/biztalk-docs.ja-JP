---
title: EDI データ要素の構造体要素 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 775e8b87-b952-46d2-a506-5174d216a9aa
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 600edb30ff157a520ac67eebce58428a62e27c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239474"
---
# <a name="edi-data-element-structural-element"></a><span data-ttu-id="c08fb-102">EDI データ要素の構造体要素</span><span class="sxs-lookup"><span data-stu-id="c08fb-102">EDI Data Element Structural Element</span></span>
<span data-ttu-id="c08fb-103">データ要素は、メッセージのデータの基本単位です。</span><span class="sxs-lookup"><span data-stu-id="c08fb-103">The data element is the primary unit of data in the message.</span></span> <span data-ttu-id="c08fb-104">データ要素は、データ要素区切り記号によって区切られます。データ要素区切り記号は、X12 の場合は既定でアスタリスク、EDIFACT の場合は既定でプラス記号です。</span><span class="sxs-lookup"><span data-stu-id="c08fb-104">Data elements are separated by the data element separator, which is an asterisk by default for X12 and a plus sign by default for EDIFACT.</span></span> <span data-ttu-id="c08fb-105">データ要素の選択肢は、必須、オプション、または条件付きとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="c08fb-105">The optionality of data elements is defined as mandatory, optional, or conditional.</span></span>  
  
 <span data-ttu-id="c08fb-106">データ要素には、単純または複合要素のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="c08fb-106">A data element can be either simple or composite.</span></span> <span data-ttu-id="c08fb-107">単純データ要素は数値で、最も低いレベルのデータです。</span><span class="sxs-lookup"><span data-stu-id="c08fb-107">Simple data elements are numeric and are the lowest level of data.</span></span> <span data-ttu-id="c08fb-108">複合データ要素はサブ要素が連結されたもので、サブ要素はコンポーネント区切り記号で区切られた単純データ要素です。</span><span class="sxs-lookup"><span data-stu-id="c08fb-108">Composite data elements are concatenations of sub element, which are simple data elements separated by a component separator.</span></span> <span data-ttu-id="c08fb-109">既定では、コンポーネント区切り記号は X12 および EDIFACT のどちらでもコロンです。</span><span class="sxs-lookup"><span data-stu-id="c08fb-109">By default, the component separator is the colon for X12 and EDIFACT.</span></span>  
  
 <span data-ttu-id="c08fb-110">EDIFACT でエンコードされたメッセージの場合、EDI 経由で送信するデータで、区切り記号として使用するように定義された文字を送信する必要があるときは、リリース文字を使用して、後続の文字が区切り記号ではなくデータの一部であることを示す必要があります。</span><span class="sxs-lookup"><span data-stu-id="c08fb-110">For EDIFACT-encoded messages, if the data to be sent via EDI needs to send any character defined for use as a separator, you need to use a release character to indicate that the following character is not a separator, but is part of the data.</span></span> <span data-ttu-id="c08fb-111">既定では、リリース文字は疑問符 (?) です。</span><span class="sxs-lookup"><span data-stu-id="c08fb-111">The release character is by default the question mark (?).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c08fb-112">X12 ではリリース文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c08fb-112">A release character is not supported for X12.</span></span> <span data-ttu-id="c08fb-113">受信側または送信側で、X12 エンコード インターチェンジのデータの一部として区切り記号が見つかった場合、インターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="c08fb-113">If a separator is encountered as part of the data of an X12-encoded interchange, on either the receive or send side, the interchange will be suspended.</span></span>