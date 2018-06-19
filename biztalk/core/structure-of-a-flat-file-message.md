---
title: フラット ファイル メッセージの構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: badb8aacf6f2ed8ce9e38f1ea6bbe432a1d3b89e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278938"
---
# <a name="structure-of-a-flat-file-message"></a>フラット ファイル メッセージの構造
Microsoft のコンテキストで[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、フラット ファイル インスタンス メッセージは次の 3 つの論理部分を含めることができるテキスト ファイル: ヘッダー、本文、およびトレーラー、その順序で。 ヘッダーおよびトレーラーはいずれも省略できます。 3 つすべての部分から成るフラット ファイル インスタンス メッセージの例を次に示します。太字で表示されている部分が本文です。  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 フラット ファイル インスタンス メッセージのヘッダー、本文、およびトレーラーをフラット ファイル逆アセンブラーが正しく識別するためには、それぞれについて、個別のスキーマを作成し、構成する必要があります。  
  
 フラット ファイル インスタンス メッセージの特定の部分内では、データの各項目がレコードとしてグループ化されます。レコード自体はサブ レコードを含むことができ、最終的には、個別のデータ項目 (フィールド) を含むことができます。 これらのレコードおよびフィールドは、基本的な 2 種類の方法を用いて相互に区別されます。 1 つ目は、位置指定による方法です。この方法では、各データ項目があらかじめ決められた長さになるように定義されます。長さの短いデータ項目は、埋め込み文字を使って決められた長さになるように調整されます。 2 つ目は、区切り記号を使った方法です。この方法では、データ項目が、1 つまたは複数の特殊文字を使って区切られます。 埋め込み文字は不要ですが、区切り文字 (または区切り文字列) がデータ自体に含まれていた場合を考慮する必要があります。  
  
 以降では、フラット ファイル インスタンス メッセージのヘッダー、本文、およびトレーラーが、BizTalk Server によってどのように処理されるかについて簡単に説明します。特に、省略可能な部分が存在するかどうかの判別方法のほか、受信フラット ファイル インスタンス メッセージの各部分を分割し、送信フラット ファイル インスタンス メッセージの各部分を結合する方法について取り上げます。 また、このセクションでは、位置指定レコード/フィールドが使用されたフラット ファイル インスタンス メッセージと、区切り記号付きレコード/フィールドが使用されたフラット ファイル インスタンス メッセージとの違いについても詳しく説明しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [フラット ファイル メッセージのヘッダー](../core/flat-file-message-headers.md)  
  
-   [フラット ファイル メッセージの本文](../core/flat-file-message-bodies.md)  
  
-   [フラット ファイル メッセージのトレーラー](../core/flat-file-message-trailers.md)  
  
-   [位置指定レコードのあるフラット ファイル メッセージ](../core/flat-file-messages-with-positional-records.md)  
  
-   [区切られたレコードのフラット ファイル メッセージ](../core/flat-file-messages-with-delimited-records.md)  
  
-   [フラット ファイル レコードの移行](../core/migrating-flat-file-records.md)