---
title: BizTalk スキーマの種類 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ad8847d3-6f0e-4982-b4a8-92a5f39a4b48
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 051cd8fb9824cece316ea6f56e318490eacf88c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240282"
---
# <a name="different-types-of-biztalk-schemas"></a>さまざまな種類の BizTalk スキーマ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、次の 4 種類のスキーマをサポートしています。  
  
-   **XML スキーマ**です。 XML スキーマは XML インスタンス メッセージのクラス構造を定義します。 このタイプのスキーマでは、XSD (XML Schema Definition) 言語を使って、XML インスタンス メッセージの構造が定義されます。XSD 本来の目的に沿っているため、このスキーマでは、単純な方法で XSD が使用されます。  
  
-   **フラット ファイル スキーマ**です。 フラット ファイル スキーマは、フラット ファイル形式 (区切り文字/位置指定、あるいは、その組み合わせ) を使用したインスタンス メッセージのクラス構造を定義します。 XSD のネイティブのセマンティック機能に対応していませんフラット ファイル インスタンス メッセージの構造を定義するための要件をすべてため — さまざまな種類の異なるレコードと、フラット ファイル内のフィールドを使用する区切り記号のなど。BizTalk Server では、XSD の注釈機能を使用して、XSD スキーマ内でこの追加情報を格納します。 BizTalk Server には、必要な補足情報をすべて格納することのできる注釈タグが豊富に定義されています。  
  
-   **エンベロープ スキーマ**です。 エンベロープ スキーマは、特殊な XML スキーマです。 XML ビジネス ドキュメントを単一の XML インスタンス メッセージにラップする XML エンベロープの構造を定義するために使用されます。 追加のプロパティ設定がいくつかが必要にエンベロープ スキーマに XML スキーマを定義するときは、エンベロープ スキーマで定義されている 1 つ以上のルート レコードがあるかどうかなどの要因によって異なります。  
  
-   **プロパティ スキーマ**です。 プロパティ スキーマは、BizTalk Server がプロパティの昇格機能として備えている 2 つのメカニズムのいずれかと組み合わせて使用されます。 プロパティの昇格とは、インスタンス メッセージの内部に格納されている特定の値を、メッセージ コンテキストにコピーするプロセスのことです。 各種の BizTalk Server コンポーネントは、メッセージ コンテキストを通じて、これらの値に容易にアクセスできるようになります。 これらのコンポーネントが、メッセージ コンテキスト内の値にアクセスすることで、メッセージのルーティングなどの処理が実行されます。 昇格されたプロパティ値は、インスタンス メッセージを宛先に送る直前に、逆の方向にコピーすることもできます。つまり、プロパティ値をアクセスしやすいメッセージ コンテキストから、インスタンス メッセージの内部に戻すことができます。 プロパティ スキーマは、昇格させたプロパティを、インスタンス メッセージからメッセージ コンテキストへ、あるいは、メッセージ コンテキストからインスタンス メッセージへとコピーするプロセスを実行する、簡易版の BizTalk スキーマといえます。  
  
 以降では、BizTalk Server の 4 種類のスキーマに関する補足情報について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML スキーマ](../core/xml-schemas.md)  
  
-   [フラット ファイル スキーマ](../core/flat-file-schemas.md)  
  
-   [エンベロープ スキーマ](../core/envelope-schemas.md)  
  
-   [プロパティ スキーマ](../core/property-schemas.md)