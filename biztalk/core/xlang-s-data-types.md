---
title: "XLANG のデータ タイプ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- Orchestration Designer, managing data
- Orchestration Designer, variables
- orchestrations, variables
- Orchestration Designer, expressions
ms.assetid: 5b08aaa6-1533-4bac-a76d-f9162e39bf4f
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c21ed77c5fdd56485514d17ed75e921c63a56212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="xlang-s-data-types"></a>XLANG のデータ型
XLANG/s は、C# の対応する型のリフレクションである、値の標準型を定義します。 これらが含まれます**ブール**、**バイト**、 **Char**、 **Decimal**、**二重**、 **Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、 **UInt16**、 **UInt32**、および**UInt64**です。 XLANG/s は 1 次元配列をサポートしますが、配列リテラルをサポートしません。  
  
 XLANG/s では、メッセージ処理に対するさまざまなサポートも提供されます。 メッセージは、スキーマ、.NET クラス、Web メッセージの種類 (WSDL)、または複雑なメッセージの種類に基づいて作成できます。 XLANG/s は、次の複合データ型をサポートします。  
  
-   **messagetype です。** このデータ型は、データ要素および XSD ベース メッセージの組み合わせとして定義されるマルチパート メッセージの種類と、メソッド メッセージの種類 (クラスまたはインターフェイスのメソッドの署名形式に一致するメッセージ) を定義します。  
  
-   **porttype。** このデータ型は、その型のポート インスタンスが動作できるポートの操作のコレクションを定義します。  
  
-   **correlationsettype です。** このデータ型は、関連付けセット変数のインスタンスで使用されるデータを定義します。 関連付けセットのデータは、システム内を移動するメッセージがビジネス プロセスの適切な実行中インスタンスに送信されるようにするためのルーティング メカニズムです。 たとえば、注文書が処理のために取引先に送信された場合は、戻り時に、その注文書に対応するビジネス プロセスの正しいインスタンスが呼び出されることが重要になります。  
  
-   **servicelinktype です。** このデータ型のセットを定義する**porttype**ビジネス プロセスで使用するポートの論理的な一貫性のグループを形成する値。 サービス リンクを使用することによって、実行時にポートのグループの動的な割り当てを可能にする強力なメカニズムが提供されます。 これによって、複数の取引先とやり取りするために使用できる 1 つのビジネス プロセスを定義できます。  
  
## <a name="see-also"></a>参照  
 [XLANG のステートメント](../core/xlang-s-statements.md)   
 [XLANG の変数および演算子](../core/xlang-s-variables-and-operators.md)   
 [XLANG の式](../core/xlang-s-expressions.md)   
 [XLANG s の予約語](../core/xlang-s-reserved-words.md)   
 [XLANG-s BPEL4WS 型への変換から](../core/xlang-s-to-bpel4ws-type-conversions.md)