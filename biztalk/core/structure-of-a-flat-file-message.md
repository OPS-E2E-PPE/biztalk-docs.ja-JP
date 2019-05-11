---
title: フラット ファイル メッセージの構造 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00f2adf6-a47c-498b-b5ae-c6bd55bafceb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfb2e5f159ad3b792393ad828e0addc7907030c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244122"
---
# <a name="structure-of-a-flat-file-message"></a>フラット ファイル メッセージの構造
Microsoft のコンテキストで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、フラット ファイル インスタンス メッセージを 3 つの論理部分を含むことのできるテキスト ファイルは、: ヘッダー、本文、およびトレーラー、その順序で。 ヘッダーとトレーラーは省略可能です。 次の例では、太字で本文を含むすべての 3 つの部分で構成されるフラット ファイル インスタンス メッセージを示します。  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 ヘッダー、本文、およびフラット ファイル インスタンス メッセージのトレーラーを正しく区別するために フラット ファイル逆アセンブラーを作成する必要があり、別のスキーマをそれぞれの構成します。  
  
 フラット ファイル インスタンス メッセージの特定の部分、内のデータのさまざまな項目がグループ化するのには、レコード、最終的のサブレコードやフィールドと呼ばれるデータの個々 の項目を含めることができます自体。 これらのレコードおよびフィールドは、異なる 2 つの基本的な手法のいずれかを使用して相互から区別されます。 最初の方法では、位置指定と呼ばれるは、その長さの予想値までのデータの短い項目を表示するために使用される埋め込み文字を使って、事前に確立された長さのあるデータの各アイテムを定義します。 区切られたと呼ばれる 2 つ目の方法論では、互いのデータ項目を分割するのに 1 つまたは複数の特殊文字を使用します。 この手法は、それ以外の場合に余分な埋め込み文字の必要性を回避できますが、データ自体には、文字または区切り記号として使用されている文字のシーケンスが含まれている場合、特別な考慮事項が導入されています。  
  
 このセクションの残りの部分が BizTalk Server でのヘッダー、本文、およびフラット ファイル インスタンス メッセージ トレーラーの処理方法の概要を提供および省略可能な部分が存在するかどうかであるの部分を分離する方法を決める方法具体的には、受信フラット ファイル インスタンス メッセージを送信フラット ファイル インスタンス メッセージの部分を結合します。 このセクションには、位置指定レコードおよびフィールドを使用するフラット ファイル インスタンス メッセージと使用には、レコードおよびフィールドが区切られているフラット ファイル インスタンス メッセージの間の違いについて追加の情報も提供します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md)  
  
-   [フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md)  
  
-   [フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md)  
  
-   [位置指定のレコードのあるフラット ファイル メッセージ](../core/flat-file-messages-with-positional-records.md)  
  
-   [区切られたレコードのあるフラット ファイル メッセージ](../core/flat-file-messages-with-delimited-records.md)  
  
-   [フラット ファイル レコードの移行](../core/migrating-flat-file-records.md)