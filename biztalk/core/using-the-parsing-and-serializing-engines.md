---
title: "文字列の解析を使用して、エンジンをシリアル化 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- parsing engine
- pipeline components [custom], engines
- serialization engine
- pipeline components [custom], assembling
- pipeline components [custom], parsing
ms.assetid: a9d19703-b074-402a-971a-b2a6cd5d0724
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e820b2dce1257ec948aa214c9fdf1d43a6a7152
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-the-parsing-and-serializing-engines"></a>解析およびシリアル化エンジンを使用します。
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] には、フラット ファイル ドキュメントの解析とシリアル化の処理を容易にする解析エンジンとシリアル化エンジンが組み込まれています。  
  
 解析エンジンは、スキーマ主導のフレームワークで、さまざまな種類のドキュメント形式を XML として解析できます。 また、カスタム形式の解析を容易にするための厳密に定義された機能拡張モデルも備えています。  
  
 複雑な解析の場合は、逆アセンブラーを使用できます。 逆アセンブラーは、ネイティブ形式を XML に変換するだけでなく、単一ドキュメントから複数ドキュメントへの分割も行うことができます。  
  
 シリアル化エンジンは解析エンジンと似ていますが、処理の方向が逆です。 解析エンジンがネイティブ形式を XML に変換するのに対し、シリアル化エンジンは XML をネイティブ形式に変換します。 また、解析エンジンが逆アセンブラーを使用するのと同様に、シリアル化エンジンはアセンブラーを使用します。  
  
 このセクションでは、文字エンコードの実行方法、XSD (XML スキーマ定義) 言語スキーマに基づく解析とシリアル化の方法、および解析エンジンとシリアル化エンジンの API を使用するその他一般的なタスクの実行方法について説明します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パイプライン コンポーネントの文字エンコーディングを実装します。](../core/implementing-character-encoding-in-a-pipeline-component.md)  
  
-   [スキーマの使用](../core/using-schemas.md)  
  
-   [フラット ファイル解析エンジンの使用](../core/using-the-flat-file-parsing-engine.md)  
  
-   [フラット ファイルのシリアル化エンジンを使用します。](../core/using-the-flat-file-serializing-engine.md)