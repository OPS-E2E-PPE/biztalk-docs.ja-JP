---
title: EDI データ要素の構造体要素 |Microsoft Docs
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
ms.openlocfilehash: b36433f3cf4cf4a8f14ac70467d870a727db7dd9
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530830"
---
# <a name="edi-data-element-structural-element"></a><span data-ttu-id="21e88-102">EDI データ要素の構造体要素</span><span class="sxs-lookup"><span data-stu-id="21e88-102">EDI Data Element Structural Element</span></span>
<span data-ttu-id="21e88-103">データ要素は、メッセージ内のデータの主要な単位です。</span><span class="sxs-lookup"><span data-stu-id="21e88-103">The data element is the primary unit of data in the message.</span></span> <span data-ttu-id="21e88-104">データ要素は、既定では X12 の場合は、アスタリスク、EDIFACT の場合、既定でプラス記号であるデータ要素区切り記号で区切られます。</span><span class="sxs-lookup"><span data-stu-id="21e88-104">Data elements are separated by the data element separator, which is an asterisk by default for X12 and a plus sign by default for EDIFACT.</span></span> <span data-ttu-id="21e88-105">データ要素の選択肢は、必須、オプション、または条件付きとして定義されます。</span><span class="sxs-lookup"><span data-stu-id="21e88-105">The optionality of data elements is defined as mandatory, optional, or conditional.</span></span>  
  
 <span data-ttu-id="21e88-106">データ要素には、単純または複合のいずれかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="21e88-106">A data element can be either simple or composite.</span></span> <span data-ttu-id="21e88-107">単純データ要素は数値でデータの最下位レベル。</span><span class="sxs-lookup"><span data-stu-id="21e88-107">Simple data elements are numeric and are the lowest level of data.</span></span> <span data-ttu-id="21e88-108">複合データ要素は、コンポーネントの区切り記号で区切られた単純データ要素には、サブ要素の連結です。</span><span class="sxs-lookup"><span data-stu-id="21e88-108">Composite data elements are concatenations of sub element, which are simple data elements separated by a component separator.</span></span> <span data-ttu-id="21e88-109">既定では、コンポーネントの区切り記号は X12 と EDIFACT のコロンです。</span><span class="sxs-lookup"><span data-stu-id="21e88-109">By default, the component separator is the colon for X12 and EDIFACT.</span></span>  
  
 <span data-ttu-id="21e88-110">EDIFACT でエンコードされたメッセージでは、EDI 経由で送信されるデータは、区切り記号として使用するために定義された文字を送信する必要がある場合たいリリース文字を使用して、次の文字が区切り記号でないが、データの一部であることを示します。</span><span class="sxs-lookup"><span data-stu-id="21e88-110">For EDIFACT-encoded messages, if the data to be sent via EDI needs to send any character defined for use as a separator, you need to use a release character to indicate that the following character is not a separator, but is part of the data.</span></span> <span data-ttu-id="21e88-111">リリース文字は、疑問符 (?) で、既定です。</span><span class="sxs-lookup"><span data-stu-id="21e88-111">The release character is by default the question mark (?).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="21e88-112">X12 では、リリース文字はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="21e88-112">A release character is not supported for X12.</span></span> <span data-ttu-id="21e88-113">区切り記号が、受信または送信のいずれかの側で、X12 エンコード インターチェンジのデータの一部として発生した場合、インターチェンジは中断されます。</span><span class="sxs-lookup"><span data-stu-id="21e88-113">If a separator is encountered as part of the data of an X12-encoded interchange, on either the receive or send side, the interchange will be suspended.</span></span>