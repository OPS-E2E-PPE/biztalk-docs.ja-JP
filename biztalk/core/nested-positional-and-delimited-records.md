---
title: "位置指定され、区切られたレコードを入れ子になった |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1688f04-d3c7-492c-82f7-a734bec0e409
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccc3d994a3561f26df1bdffa7b547b1f647936a6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="nested-positional-and-delimited-records"></a>入れ子になった位置指定レコードおよび区切り記号付きレコード
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でサポートされているフラット ファイル形式では、位置指定レコードと区切り記号付きレコードを組み合わせて使用できます (使用できない場合もあります)。 次の組み合わせが可能です。  
  
-   区切り記号を使用してすべてのレコードとその下位レコードの相互の境界を設定しており、区切り記号 (境界の区切り記号とは異なる場合もある) を使用してそれらのレコード内のフィールドを分割しているフラット ファイル。  
  
-   あらかじめ定義されたレコード長およびフィールド長に応じたファイル内の位置に基づいて、すべてのレコード、下位レコード、およびフィールドの境界が決定されるフラット ファイル。  
  
-   区切り記号を使用してファイルの最も外側のレコードセットの境界が設定されていて、下位の区切り記号付きレコードと下位の位置指定レコードが組み合わされているフラット ファイル。 下位の区切り記号付き (または位置指定) レコード内にあるフィールド間の境界では、区切り記号 (区切り記号付きレコード) またはフィールドの固定長 (位置指定レコード) が使用されます。 位置指定レコードの下に属しているレコードについては、位置の指定も行う必要があります。つまり、ファイルの一部が区切り記号付きレコードから位置指定レコードに切り替わると、そのファイルの下位部分の位置をすべて指定する必要があります。  
  
 解析があいまいになると、位置指定レコードは、どのような場合であっても、下位の区切り記号付きレコードを格納できなくなります。  
  
## <a name="see-also"></a>参照  
 [ファイル メッセージ スキーマをフラットを作成する際の考慮事項](../core/considerations-when-creating-flat-file-message-schemas.md)