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
ms.openlocfilehash: cabbfc889b4a07616012dc85c6763e1444ed8f43
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351081"
---
# <a name="different-types-of-biztalk-schemas"></a>さまざまな種類の BizTalk スキーマ
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 次の 4 種類のスキーマをサポートしています。  
  
- **XML スキーマ**します。 XML スキーマでは、XML インスタンス メッセージのクラスの構造を定義します。 このタイプのスキーマは、XML インスタンス メッセージの構造を定義する XML スキーマ定義 (XSD) 言語を使用して、XSD の使用目的は、このため、このようなスキーマは、簡単な方法で XSD を使用します。  
  
- **フラット ファイル スキーマ**します。 フラット ファイル スキーマは、いくつかの組み合わせまたは区切り文字/位置指定フラット ファイル形式を使用するインスタンス メッセージのクラスの構造を定義します。 XSD のセマンティック固有の機能がすべてのフラット ファイル インスタンス メッセージの構造を定義するための要件に対応できませんので、-など、さまざまな種類の異なるレコード、フラット ファイル内のフィールドの使用可能性のある区切り記号の。BizTalk Server では、XSD の注釈機能を使用して、XSD スキーマ内でこの追加情報を格納します。 BizTalk Server では、すべての必要な追加情報を格納するために使用できる注釈タグの豊富なセットを定義します。  
  
- **エンベロープ スキーマ**します。 エンベロープ スキーマは、特殊な種類の XML スキーマです。 エンベロープ スキーマは、1 つまたは複数の XML ビジネス ドキュメントを 1 つの XML インスタンス メッセージにラップするために使用する XML エンベロープの構造の定義に使用されます。 エンベロープ スキーマに XML スキーマを定義するときに、いくつかの追加のプロパティの設定が必要なエンベロープ スキーマで定義されている 1 つ以上のルート レコードがあるかどうかなどの要因によって異なります。  
  
- **プロパティ スキーマ**します。 プロパティ スキーマは、プロパティの昇格と呼ばれるものの BizTalk Server 内に存在する 2 つのメカニズムのいずれかで使用されます。 プロパティの昇格は、メッセージ コンテキストに、インスタンス メッセージの内部から特定の値をコピーするプロセスです。 メッセージ コンテキストからこれらの値は、さまざまな BizTalk Server コンポーネントでより簡単にアクセスします。 これらのコンポーネントでは、値を使用して、メッセージのルーティングなどの操作を実行します。 昇格されたプロパティが、インスタンス メッセージが送信先に送信される直前に、値をインスタンス メッセージの深さに簡単にアクセスできるメッセージ コンテキストから、他の方向にコピーこともできます。 プロパティ スキーマは、インスタンス メッセージとメッセージ コンテキストの間を行き来昇格させたプロパティをコピーするプロセスで再生する BizTalk スキーマの簡易バージョンです。  
  
  セクションの残りの部分は、これらの 4 種類の BizTalk Server でのスキーマに関する追加情報を提供します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [XML スキーマ](../core/xml-schemas.md)  
  
-   [フラット ファイル スキーマ](../core/flat-file-schemas.md)  
  
-   [エンベロープ スキーマ](../core/envelope-schemas.md)  
  
-   [プロパティ スキーマ](../core/property-schemas.md)