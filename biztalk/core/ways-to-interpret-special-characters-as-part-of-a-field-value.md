---
title: 特殊文字をフィールド値の一部として解釈させる方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e19a202-4e4d-42e0-ba1e-fddc52792b21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f802eca93622a893787ebc06f3cf6cebf4004918
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393631"
---
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a><span data-ttu-id="021b8-102">特殊文字をフィールド値の一部として解釈させる方法</span><span class="sxs-lookup"><span data-stu-id="021b8-102">Ways to Interpret Special Characters as Part of a Field Value</span></span>
<span data-ttu-id="021b8-103">位置指定および区切り記号付きの両方のレコードのフィールドは、パッド、ラップ、およびエスケープ文字などのさまざまな種類の特殊文字を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="021b8-103">Fields in both positional and delimited records can contain special characters of different types, such as pad, wrap, and escape characters.</span></span> <span data-ttu-id="021b8-104">区切られたレコードは、別のレコードから 1 つのレコードおよび内のフィールドを区切るために使用する 1 つまたは複数の異なる区切り記号の文字を含めることもできます。</span><span class="sxs-lookup"><span data-stu-id="021b8-104">Delimited records can also contain one or more different delimiter characters that are used to separate the fields within a record and one record from another record.</span></span> <span data-ttu-id="021b8-105">場合がありますこれらの特殊文字は、データ自体の一部であるし、そのような場合の特別なものとして解釈されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="021b8-105">Sometimes these special characters are part of the data itself, and are not meant to be interpreted as special in those cases.</span></span>  
  
 <span data-ttu-id="021b8-106">Microsoft で使用するフラット ファイル スキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文字フィールドに含まれるデータの一部としてのそれ以外の場合の特別な解釈の 2 つの異なる手法をサポートします。</span><span class="sxs-lookup"><span data-stu-id="021b8-106">The flat file schemas used by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] support two different techniques for flagging occurrences of otherwise special characters as simply part of the data contained by a field.</span></span> <span data-ttu-id="021b8-107">これら 2 つの手法では、エスケープ文字を使用し、文字をそれぞれラップします。</span><span class="sxs-lookup"><span data-stu-id="021b8-107">These two techniques employ escape characters and wrap characters, respectively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="021b8-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="021b8-108">In This Section</span></span>  
  
-   [<span data-ttu-id="021b8-109">エスケープ文字</span><span class="sxs-lookup"><span data-stu-id="021b8-109">Escape Characters</span></span>](../core/escape-characters.md)  
  
-   [<span data-ttu-id="021b8-110">囲み文字</span><span class="sxs-lookup"><span data-stu-id="021b8-110">Wrap Characters</span></span>](../core/wrap-characters.md)