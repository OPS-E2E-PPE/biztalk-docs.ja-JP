---
title: ベースと一般的なスキーマ |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base schemas
- schemas, common schemas
- schemas, base schemas
- common schemas
ms.assetid: 60eb24f6-cc4f-4c6d-ab15-9e3a6b4ed376
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ca51abfcdbfe965bc3da8deeb97f72df736903
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209178"
---
# <a name="base-and-common-schemas"></a>ベースと一般的なスキーマ
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]レコードと別のスキーマ内の個々 のメッセージ スキーマを構成する要素を実装します。 この方法は、フィールドと形式の変更によってこのようなメッセージ スキーマを切り離すことの更新プログラムを提供する 1 つの場所を提供します。  
  
 基本のスキーマ (**SWIFT 基本 Types.xsd**) メッセージ スキーマを参照する共通のレコードと、要素定義が含まれています。 共通のレコードと、要素の定義は、SWIFT FIN メッセージ フィールドに対応します。 このスキーマは、メッセージ スキーマを使用する他のプロジェクトを追加する必要があります。 基本のスキーマは、共通の関数と規則について説明し、A4SWIFT が適切なメッセージ インスタンスの検証に使用する形式を定義します。 SWIFT ベース Types.xsd スキーマ XSD を定義する**simpleType**および SWIFT フィールドの複雑な要素です。 SWIFT が定義されている**simpleType**量、レート、価格、およびに SWIFT をフィールドの多くで使用するなど、すべての基本フィールド用の要素。 SWIFT ベース Types.xsd スキーマ フィールドを含む、カスタムの多くの複雑な要素を XSD でも定義**simpleTypes**スキーマで定義します。 たとえば、 **BankIdentifierCode**複合型の要素は、銀行コード、国番号、市外局番、および分岐のコードを使用します。 ユーザーが新規に追加できる**simpleTypes**と複雑な要素であり、ミラー SWIFT フィールドと既存の型を変更できます。 注意してください、ただし、ビジネス ルール エンジン (BRE) の検証および XML の機能がこれらに定義された型に依存しているために、既存の型を変更するときにします。  
  
 共通のスキーマ (**SWIFT 共通データ Types.xsd**) ベースのスキーマのフィールドに適切な文字セットを定義します。 SWIFT で参照しているこれらの文字セットを定義する、 *SWIFT ユーザー マニュアル*です。 また、共通のスキーマをスキーマ プロジェクトに追加する必要があります。  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)