---
title: BizTalk スキーマの種類 |Microsoft Docs
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
ms.openlocfilehash: 2a60907b3b8bbecf430984ec3a799bc1f91953be
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010699"
---
# <a name="different-types-of-biztalk-schemas"></a>さまざまな種類の BizTalk スキーマ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、次の 4 種類のスキーマをサポートしています。  
  
- **XML スキーマ**します。 XML スキーマは XML インスタンス メッセージのクラス構造を定義します。 このタイプのスキーマでは、XSD (XML Schema Definition) 言語を使って、XML インスタンス メッセージの構造が定義されます。XSD 本来の目的に沿っているため、このスキーマでは、単純な方法で XSD が使用されます。  
  
- **フラット ファイル スキーマ**します。 フラット ファイル スキーマは、フラット ファイル形式 (区切り文字/位置指定、あるいは、その組み合わせ) を使用したインスタンス メッセージのクラス構造を定義します。 XSD のセマンティック固有の機能がすべてのフラット ファイル インスタンス メッセージの構造を定義するための要件に対応できませんので、-など、さまざまな種類の異なるレコード、フラット ファイル内のフィールドの使用可能性のある区切り記号の。BizTalk Server では、XSD の注釈機能を使用して、XSD スキーマ内でこの追加情報を格納します。 BizTalk Server には、必要な補足情報をすべて格納することのできる注釈タグが豊富に定義されています。  
  
- **エンベロープ スキーマ**します。 エンベロープ スキーマは、特殊な XML スキーマです。 XML ビジネス ドキュメントを単一の XML インスタンス メッセージにラップする XML エンベロープの構造を定義するために使用されます。 エンベロープ スキーマに XML スキーマを定義するときに、いくつかの追加のプロパティの設定が必要なエンベロープ スキーマで定義されている 1 つ以上のルート レコードがあるかどうかなどの要因によって異なります。  
  
- **プロパティ スキーマ**します。 プロパティ スキーマは、BizTalk Server がプロパティの昇格機能として備えている 2 つのメカニズムのいずれかと組み合わせて使用されます。 プロパティの昇格とは、インスタンス メッセージの内部に格納されている特定の値を、メッセージ コンテキストにコピーするプロセスのことです。 各種の BizTalk Server コンポーネントは、メッセージ コンテキストを通じて、これらの値に容易にアクセスできるようになります。 これらのコンポーネントが、メッセージ コンテキスト内の値にアクセスすることで、メッセージのルーティングなどの処理が実行されます。 昇格されたプロパティ値は、インスタンス メッセージを宛先に送る直前に、逆の方向にコピーすることもできます。つまり、プロパティ値をアクセスしやすいメッセージ コンテキストから、インスタンス メッセージの内部に戻すことができます。 プロパティ スキーマは、昇格させたプロパティを、インスタンス メッセージからメッセージ コンテキストへ、あるいは、メッセージ コンテキストからインスタンス メッセージへとコピーするプロセスを実行する、簡易版の BizTalk スキーマといえます。  
  
  以降では、BizTalk Server の 4 種類のスキーマに関する補足情報について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML スキーマ](../core/xml-schemas.md)  
  
-   [フラット ファイル スキーマ](../core/flat-file-schemas.md)  
  
-   [エンベロープ スキーマ](../core/envelope-schemas.md)  
  
-   [プロパティ スキーマ](../core/property-schemas.md)