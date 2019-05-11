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
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a>特殊文字をフィールド値の一部として解釈させる方法
位置指定および区切り記号付きの両方のレコードのフィールドは、パッド、ラップ、およびエスケープ文字などのさまざまな種類の特殊文字を含めることができます。 区切られたレコードは、別のレコードから 1 つのレコードおよび内のフィールドを区切るために使用する 1 つまたは複数の異なる区切り記号の文字を含めることもできます。 場合がありますこれらの特殊文字は、データ自体の一部であるし、そのような場合の特別なものとして解釈されるものではありません。  
  
 Microsoft で使用するフラット ファイル スキーマ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]文字フィールドに含まれるデータの一部としてのそれ以外の場合の特別な解釈の 2 つの異なる手法をサポートします。 これら 2 つの手法では、エスケープ文字を使用し、文字をそれぞれラップします。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [エスケープ文字](../core/escape-characters.md)  
  
-   [囲み文字](../core/wrap-characters.md)