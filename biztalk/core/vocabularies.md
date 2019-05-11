---
title: ボキャブラリ |Microsoft Docs
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
ms.openlocfilehash: 18e513687db2b291462843811d296c15d3509288
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320851"
---
# <a name="vocabularies"></a>ボキャブラリ
ルール条件およびアクションの定義に使用される用語は通常、ドメインまたは業界固有の命名規則によって表されます。 たとえば、電子メール ユーザーに書き込むメッセージとしてルール「から受信した」メッセージ"間、送受信した後、"保険のビジネス アナリストが「危険要素」および「補償範囲額」としてルールを記述  
  
 このドメインに固有の用語を基になると、ルールの条件とルールのアクションを実装するテクノロジ アイテム (オブジェクト、データベース テーブル、および XML ドキュメント)。 Vocabulariesare では、ビジネス セマンティクスと実装の間のギャップを埋めるために設計されています。  
  
 たとえば、承認状態のデータ バインディングは可能性がありますに特定のデータベース、SQL クエリとして表される特定の行で特定の列をポイントします。 ルールでこのような複雑な表現を挿入する代わりに、「状態です」のフレンドリ名をデータ バインドに関連付けられている、ボキャブラリの定義を作成する場合があります代わりに その後、ルールの任意の数の"Status"を含めることができ、ルール エンジンは、テーブルから、対応するデータを取得することができます。  
  
 A*ボキャブラリ*ルール条件およびアクションで使用されるファクトのフレンドリ名で構成される定義のコレクションです。 ボキャブラリの定義するルール読み、理解、および特定のビジネス ドメイン内のユーザーで共有できます。  
  
 ビジネス ルール作成ツールを使用して、共有ルール ストアに配置し、ボキャブラリを定義することができます。 ボキャブラリは、ルールの作成を新規または既存のアプリケーションに統合するツールの開発者でも使用できます。  
  
 ボキャブラリを使用する前にバージョンを設定およびルール ストアに公開する必要があります。 これは、ボキャブラリの定義が変更されないことを保証するためにし、参照整合性を維持します。 これは、ボキャブラリの特定のバージョンを使用するポリシーが、基になるボキャブラリ変更により、予期しない失敗ことを意味します。  
  
## <a name="see-also"></a>参照  
 [ビジネス ルール エンジン](../core/business-rules-engine.md)