---
title: フィールドの値の一部として特殊文字を解釈する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: b96a3c7502a47541e8e58ec3df3eccf6098e3abc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288386"
---
# <a name="ways-to-interpret-special-characters-as-part-of-a-field-value"></a>フィールドの値の一部として特殊文字を解釈する方法
位置指定レコードおよび区切り記号付きレコードのフィールドには、いずれも、埋め込み文字、囲み文字、エスケープ文字など、さまざまな種類の特殊文字が含まれます。 区切り記号ベースのレコードには、さらに、レコード間の区切りや、レコード内のフィールド間の区切りを表す記号が含まれています。 これらの特殊文字がデータとして含まれている場合もあり、その場合は、特殊な文字として解釈されないようにする必要があります。  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で使用されるフラット ファイル スキーマでは、特殊文字をフィールド データの一部として解釈させるための 2 とおりの方法がサポートされています。 これらの方法には、それぞれエスケープ文字と囲み文字が使用されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [エスケープ文字](../core/escape-characters.md)  
  
-   [囲み文字](../core/wrap-characters.md)