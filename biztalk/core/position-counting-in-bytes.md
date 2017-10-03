---
title: "位置のカウント (バイト単位) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5cf666ec-d15e-4d2d-9df9-49189f352c65
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3cdb7bbf1f0d6af04f0cc28ed1bdb7477b259de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="position-counting-in-bytes"></a>位置のカウント (バイト単位)

## <a name="overview"></a>概要

使用することができます、**カウント位置 (バイト単位)**のプロパティ、**スキーマ**ノード。 

* 値の入力方法の指定、**位置指定値**と**位置指定オフセット**位置指定レコード内のさまざまなフィールドのプロパティが解釈されます
* 値の入力方法の指定、**タグ オフセット**位置指定レコード自体のプロパティが解釈されます

既定では、これらの値は、文字数として解釈されます。 次の場合、**カウント位置 (バイト単位)**プロパティに設定されている**True**、これらの値はバイト数として解釈されます。  
  
 設定、**カウント位置 (バイト単位)**プロパティを**True**可能性があるマルチバイト文字を扱うときに必要な設定 (MBCS や DBCS) のデータまたは SAP、メインフレームで、フラット ファイル メッセージの発生時に、またはバイト単位で位置のカウントが他のシステムです。  
  
 フィールド長をバイト単位でカウントすると、文字のエンコードに使用されるバイト数が可変である場合に複雑になりやすく、フィールド境界の区切りに関連した問題が生じる場合もあります。 このような場合、フラット ファイル逆アセンブラーは、フラット ファイルを解析するときに、使用されている文字エンコードに基づいて、適切な解析方法を決定します。  
  
 文字エンコードに基づいて解析方法を決定する際、MBCS 文字エンコードの先頭バイト (先行バイトともいう) が考慮されます。 先頭バイトは、マルチバイト文字エンコードの始まりを示す目的で使用され、単独で出現することはありません。 フィールドの長さを文字単位ではなくバイト単位で指定する場合、フィールドの最後のバイトが先頭バイトになってしまう可能性があります。上記のとおり、先頭バイトが単独で文字を形成することはありえません。 このような場合、フラット ファイル逆アセンブラーは、先頭バイトの直前に現れた文字を、前のフィールドの最後の文字として扱い、末尾にある先頭バイトを次のフィールドの解析起点と見なします。  

これらのプロパティの詳細について[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 
  
## <a name="see-also"></a>参照  
 [位置指定レコードに関する注意点](../core/positional-record-considerations.md)   
