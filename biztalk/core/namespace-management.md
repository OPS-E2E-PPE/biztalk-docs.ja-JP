---
title: Namespace 管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4638c47c-3cdd-43af-aa00-da98e7293503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f313ba2063e2184b4c0fe755c32bc0cbf07e0409
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323545"
---
# <a name="namespace-management"></a>名前空間の管理
BizTalk エディターは名前空間をサポートしています。 XML の名前空間は、XML メッセージにおける要素名または属性名として使用することのできる名前の集合です。 要素名や属性名を名前空間で修飾することにより、同じスキーマ内の別の部分で定義されている同じ要素名や同じ属性名の競合を防ぐことができます。  
  
 名前空間は、URI (Universal Resource Identifier) で識別されます (URI には、URL (Uniform Resource Locator) または URN (Uniform Resource Name) が使用される)。 通常、名前空間には別名が割り当てられます。別名とは、要素名や属性名の前に付加される短いプレフィックスのことで、要素名や属性名との区切りとしてコロン (:) が付きます。 たとえば、一般的に、次の名前空間宣言内では、**スキーマ**要素は、スキーマの XSD 表記でします。  
  
```  
xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
```  
  
 プレフィックスは、xs など、要素として、XSD 全体を通じて表示されることが、**要素**要素 (xs:element) および**属性**要素 (xs:attribute))。  
  
 設定する必要が最初に、メッセージ スキーマと、プロパティ スキーマであるかに関係なく、新しいスキーマを作成するときに、 **Target Namespace**のプロパティ、**スキーマ**ノード適切です。 スキーマは、他のスキーマで、インポート/を含める/redefine メカニズムを使用して、上位変換が定義されている任意のプロパティの前に前に、ターゲットの名前空間を確立する必要があります。  
  
> [!WARNING]
>  大文字と小文字のみが異なる 2 つの名前空間を使用する場合、大文字と小文字を区別する照合順序を指定して BizTalk データベースをインストールする必要があります。 大文字と小文字を区別する照合順序には、たとえば、大文字と小文字の区別を有効にしたバイナリと非バイナリの照合順序などがあります。 XML は大文字と小文字を区別するので、大文字と小文字を区別する照合順序を指定しないと、スキーマ解決が失敗します。  
  
 次の 2 つの名前空間は、スキーマの XSD (XML Schema Definition) 言語表記では、schema 要素に名前空間宣言として自動的に追加されます。  
  
- xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>"  
  
- xmlns:xs="<http://www.w3.org/2001/XMLSchema>"  
  
  作成中のスキーマから他のスキーマを使用する場合は、それに該当する名前空間を宣言する必要があります。 これらの名前空間と、自動的に追加された名前空間を調べることができます、 **Imports**  ダイアログ ボックスを使用してアクセスできる、 **Imports**のプロパティ、 **スキーマ**ノード。 作成して、スキーマ内の他のスキーマで宣言されているその他のデータ型の使用の詳細については、次を参照してください。[使用その他のスキーマを](../core/schemas-that-use-other-schemas.md)と[スキーマを使用して他のスキーマ作成](../core/how-to-create-schemas-that-use-other-schemas.md)です。  
  
  プロパティ スキーマに関連付けられている名前空間で調べることができます、**プロパティの昇格** ダイアログ ボックス。  
  
## <a name="see-also"></a>参照  
 [スキーマを作成する際の考慮事項](../core/considerations-when-creating-schemas.md)