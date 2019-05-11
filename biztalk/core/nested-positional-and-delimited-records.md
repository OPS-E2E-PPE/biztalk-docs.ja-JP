---
title: 位置指定および区切り記号付きレコードを入れ子になった |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d1688f04-d3c7-492c-82f7-a734bec0e409
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf45d62d65f0d24dc711978e3e7d50c141330213
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263506"
---
# <a name="nested-positional-and-delimited-records"></a>入れ子になった位置指定および区切り記号付きレコード
Microsoft でサポートされているフラット ファイル形式で[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、位置指定され、区切られたレコードのいくつかの組み合わせが許可されているし、他のユーザーは許可されません。 次の組み合わせが可能です。  
  
- フラット ファイルとそれらのレコード内のフィールドを区切るため (異なる場合もあります) を区切り記号に使用する区切り記号を使用して、すべてのレコードとその下位レコード、互いの間の境界を決定でします。  
  
- 定義済みのレコードとフィールド長に応じたファイル内の位置に従ってフラット ファイルのすべてのレコード、下位レコード、およびそのフィールド間の境界が決定されます。  
  
- フラット ファイルには少なくとも間の境界を決定する区切り記号を使用する最も外側にある一連のレコード、ファイルと下位レコードの区切り文字および位置指定の組み合わせが使用されます。 下位の区切り文字/位置指定レコード内のフィールド間の境界は、それぞれの区切り記号または固定フィールド長のいずれかを使用して決定されます。 位置指定 (下位) レコードの下位のレコードは位置指定以外にある必要があります。つまり、ファイルの部分は、位置指定に区切られたレコードからスイッチを一度全体、ファイルの下位部分は位置指定である必要があります。  
  
  解析があいまいになりますが、位置指定レコードは、発生した場所には禁止されていますから区切られた下位レコードを格納しています。  
  
## <a name="see-also"></a>参照  
 [フラット ファイル メッセージ スキーマを作成する上での注意点](../core/considerations-when-creating-flat-file-message-schemas.md)