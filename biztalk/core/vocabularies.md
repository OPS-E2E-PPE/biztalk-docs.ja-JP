---
title: ボキャブラリ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, vocabularies
- vocabularies, about vocabularies
- vocabularies
- Business Rules Engine, vocabularies
ms.assetid: 591673a0-2c4d-41ca-9997-b363c086dd66
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9e20dfead51d54822d3316c8819d04a259cfa83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288010"
---
# <a name="vocabularies"></a>ボキャブラリ
ルールの条件やアクションを定義するために使用される用語は、通常、分野固有または業界固有の用語体系に従って表現されます。 たとえば、電子メールを使用するユーザーが "差出人" や "特定日時以降に受信" したメッセージとしてルールを記述したり、保険のビジネス アナリストが "危険要素" および "補償範囲額" としてルールを記述したりします。  
  
 この分野固有の用語の背景には、ルールの条件やルールのアクションを実装するテクノロジ アイテム (オブジェクト、データベース テーブル、および XML ドキュメント) が存在します。 Vocabulariesare では、ビジネス セマンティクスと実装の間のギャップを埋めるために設計されています。  
  
 たとえば、承認状態のデータ バインドは、SQL クエリとして表される特定のデータベースの特定の行の単一の列を示す場合があります。 ルールに直接このような複雑な表現を挿入する代わりに、たとえば、データ バインドに関連付けるボキャブラリ定義をフレンドリ名 "Status" で作成します。 後で任意の数のルールに "Status" を含めることができるので、ルール エンジンは、テーブルから対応するデータを取得できます。  
  
 A*ボキャブラリ*ルール条件およびアクションで使用されるファクトのフレンドリ名で構成される定義のコレクションです。 ボキャブラリを定義すると、特定のビジネス分野のユーザーによるルールの参照、理解、および共有が簡単になります。  
  
 ビジネス ルール作成ツールを使用して、共有されているルール ストアに置くボキャブラリを定義できます。 ルール作成を新しいアプリケーション (または既存のアプリケーション) に統合するツールの開発者も、ボキャブラリを使用できます。  
  
 ボキャブラリを使用する前に、ボキャブラリにバージョンを設定し、使用しているルール ストアにボキャブラリを公開する必要があります。 これにより、ボキャブラリの定義は変更されずに参照整合性が確保されます。 つまり、基になるボキャブラリが変更されても、ボキャブラリの特定のバージョンを使用するポリシーで予期しないエラーが発生することがありません。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジン](../core/business-rules-engine.md)