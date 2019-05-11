---
title: Xlang-s データ型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- Orchestration Designer, managing data
- Orchestration Designer, variables
- orchestrations, variables
- Orchestration Designer, expressions
ms.assetid: 5b08aaa6-1533-4bac-a76d-f9162e39bf4f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cc0d20336169ec1198c21dcbe932ff5a823a568
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394712"
---
# <a name="xlang-s-data-types"></a>Xlang-s データ型
XLANG/秒の反射効果が標準値の型を定義します。 そのC#の対応します。 以下の**ブール**、**バイト**、 **Char**、 **Decimal**、**二重**、 **Int16**、 **Int32**、 **Int64**、 **SByte**、**単一**、**文字列**、 **UInt16**、 **UInt32**、および**UInt64**します。 XLANG/秒では、1 次元の配列をサポートしていますが、配列リテラルがサポートされません。  
  
 XLANG/秒では、メッセージの処理の豊富なサポートもあります。 メッセージは、スキーマ、.NET クラス、Web メッセージの種類 (WSDL)、または複雑なメッセージの種類に基づいて作成できます。 XLANG/秒には、次の複合データ型がサポートされています。  
  
-   **メッセージの種類。** このデータ型は、データ要素および XSD ベースのメッセージの組み合わせとして定義されているマルチパート メッセージの種類およびメソッド メッセージの種類 (クラスまたはインターフェイスのメソッドのシグネチャの形式に一致するメッセージ) を定義します。  
  
-   **porttype。** このデータ型は、その種類のポートのインスタンスが対処できるポート operations のコレクションを定義します。  
  
-   **correlationsettype.** このデータ型は、関連付けセット変数の任意のインスタンスで使用されるデータを定義します。 関連付けセットのデータは、システムを移動するメッセージがビジネス プロセスの適切な実行中のインスタンスにディスパッチされることを確認するためのルーティング メカニズムです。 たとえば、注文書を処理するため、取引先に送信する場合、その発注に対応するビジネス プロセスの適切なインスタンスが、戻り値で呼び出される命令型は。  
  
-   **servicelinktype.** このデータ型のセットを定義する**porttype**ビジネス プロセスで使用されるポートの論理的に一貫したグループを形成する値。 サービス リンクの使用は、実行時にポートのグループに動的に割り当てることができる強力なメカニズムです。 これにより、複数の取引先パートナーとの対話に使用できる 1 つのビジネス プロセスを定義することができます。  
  
## <a name="see-also"></a>参照  
 [Xlang-s ステートメント](../core/xlang-s-statements.md)   
 [Xlang-s の変数および演算子](../core/xlang-s-variables-and-operators.md)   
 [Xlang-s 式](../core/xlang-s-expressions.md)   
 [Xlang-s の予約語](../core/xlang-s-reserved-words.md)   
 [XLANG-s から BPEL4WS への種類の変換](../core/xlang-s-to-bpel4ws-type-conversions.md)