---
title: マップについての詳細 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- file types, maps
- BizTalk Mapper
- maps, file type
- maps, about maps
- BizTalk Mapper, about BizTalk Mapper
- maps
ms.assetid: 512ef2b7-3d01-4fcf-bb38-de68ec608b07
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b7a2e7f89e927b4759ea814f341684195273e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65362336"
---
# <a name="about-maps"></a>マップについて
BizTalk マッパーでは、リンクと Functoid を使って入力スキーマと出力スキーマの関係を定義できます。 リンクは、レコードまたはフィールドのデータを直接コピーするような関係を定義するときに使用します。 スキーマに含まれる項目どうしを直接接続したり、Functoid との接続を定義する場合にリンクが使用されます。 Functoid は、次のように複雑なデータ操作を実行するときに使用します。  
  
- 送信元スキーマに含まれる 2 つのフィールドの値を加算し、その結果を送信先スキーマにコピーする。  
  
- 文字を ASCII 形式に変換する。  
  
- 繰り返しレコードのフィールドの平均を取得し、その結果を送信先スキーマのフィールドにコピーする。  
  
  BizTalk マッパーでは、.btm という拡張子のファイルにマップが保存されます。 ファイルは、マップに関するデザイン情報を保存します: functoid、スキーマ項目と functoid 間のリンクを表すアイコンの場所と、マップに関するその他の情報。 マップをビルドまたはコンパイルすると、こうしたマップに関する情報が、BizTalk マッパーによって対応する XSLT (Extensible Language Stylesheet Transformations) スタイルシートに変換されます。  
  
> [!NOTE]
>  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コンパイラには、単一のプロジェクトにおけるすべての文字列の合計サイズについて 16 MB の制限があります。 BizTalk プロジェクトをコンパイルしている間、コンパイラはアセンブリ作成のスキーマ、マップ、およびオーケストレーションをシリアル化し、これによってすべての文字列の合計サイズが増加し、制限を超える可能性があります。 この問題を解決するには、各プロジェクト内のすべての文字列の合計サイズが 16 MB より小さくなるようにスキームまたはマップを別の BizTalk プロジェクト (通常は、同じソリューションの下) に入れることで、プロジェクトを再編成します。  
  
 作成したマップを使用することで、データをさまざまな形式に変換できます。たとえば、単一の取引先固有の形式に変換したり、複数の取引先とやり取りするための形式に変換することもできます。 このセクションの各トピックでは、スキーマのマッピングに関する概要について説明します。 マップの背景については、次を参照してください。[マップ](../core/maps.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [マップのリンク](../core/links-in-maps.md)  
  
-   [マップの Functoid](../core/functoids-in-maps.md)  
  
-   [マップのコンパイルとテスト](../core/map-compilation-and-testing.md)