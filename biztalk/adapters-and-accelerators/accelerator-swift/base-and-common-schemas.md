---
title: ベースと一般的なスキーマ |Microsoft Docs
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
ms.openlocfilehash: 5512c9233e292fdafa232db5c36ac6ff14de53cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378794"
---
# <a name="base-and-common-schemas"></a>ベースと一般的なスキーマ
Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]レコードと別のスキーマ内の個々 のメッセージ スキーマを構成する要素を実装します。 このアプローチでは、フィールドと形式のこのような変更からのメッセージ スキーマの保護の更新プログラムを提供する 1 つの場所を提供します。  
  
 基本スキーマ (**SWIFT 基本 Types.xsd**) メッセージ スキーマを参照する共通のレコードと要素定義が含まれています。 共通のレコードと要素の定義は、SWIFT FIN メッセージ フィールドに対応します。 このスキーマのメッセージ スキーマを使用するプロジェクトを追加する必要があります。 基本スキーマは、規則と共通の関数について説明し、A4SWIFT を適切なメッセージ インスタンスの検証に使用する形式を定義します。 SWIFT ベース Types.xsd スキーマ XSD を定義する**simpleType**と SWIFT のフィールドの複雑な要素です。 SWIFT が定義されている**simpleType**量、速度、価格、およびフィールドの多くで SWIFT を使用して具合など、すべての基本フィールドの要素。 SWIFT ベース Types.xsd スキーマでは、カスタムの多くが含まれるフィールドの XSD の複雑な要素も定義します**simpleTypes**スキーマで定義されています。 たとえば、 **BankIdentifierCode**複雑な要素は、銀行コード、国コード、市外局番、およびブランチのコードを使用します。 ユーザーが新規に追加できる**simpleTypes**と複雑な要素であり、ミラー SWIFT フィールドと、既存の型を変更することができます。 注意が必要、ただし、ビジネス ルール エンジン (BRE) の検証および XML の検証機能は、これらの定義された型に依存するために既存の型を変更するとします。  
  
 共通のスキーマ (**SWIFT 共通データ Types.xsd**) ベースのスキーマのフィールドに適切な文字セットを定義します。 SWIFT で参照されるよう、これらの文字セットを定義する、 *SWIFT ユーザー向けハンドブック*します。 また、共通のスキーマをスキーマ プロジェクトに追加する必要があります。  
  
## <a name="see-also"></a>参照  
 [スキーマの操作](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)