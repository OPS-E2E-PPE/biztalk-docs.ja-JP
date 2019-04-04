---
title: 宣言のカスタマイズ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- declared customizations
- Z objects, declared customizations
- customizing, Z objects
- customizing, declared customizations
ms.assetid: 484655e9-8bfa-4643-bbe6-4ef69cbd83ad
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 091612d1ad15f7ea841b5936beba1fcf7fc26ddf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988267"
---
# <a name="declared-customizations"></a>宣言済みのカスタマイズ
宣言済みのカスタマイズには、変更または HL7 メッセージへの追加の柔軟性があります。 メッセージの新しい型を定義することもできます。 これは、次の方法のいずれかで行います。  
  
- 新しいメッセージ型、またはトリガー イベントを定義することで、メッセージの定義を変更します。  
  
- 既存のメッセージ型への新しいセグメントの追加  
  
- (セグメント、フィールド、コンポーネントまたはサブコンポーネント)、既存のメッセージ部分のデータ型の変更  
  
- 既存のメッセージ部分で使用できる潜在的な値を変更します。  
  
  > [!NOTE]
  >  宣言された Z オブジェクトまたは HL7 スキーマの標準的なオブジェクトで使用する列挙値を変更することができます。 これを行うを参照してください。[列挙型の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)します。  
  
  変更または追加、保守、および現在定義されているメッセージ型のカスタム オブジェクトを関連付けることによって、HL7 メッセージに追加します。 HL7 標準は「Z オブジェクト」これらのカスタム オブジェクトを呼び出し、HL7 標準に準拠している既存のオブジェクトと区別するためです。 Z オブジェクトを定義するのにには、BizTalk エディターを使用します。 BizTalk エディターを使用しても、すべてのトリガー イベントで Z オブジェクトへの更新を反映する機能とそれを含む抽象メッセージを使用します。 Z オブジェクトの作成方法の詳細については、[Z オブジェクトで拡張 HL7 2.X スキーマ](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)を参照してください。  
  
  Z オブジェクトを使用すると、HL7 標準で指定されていない方法で使用するセグメントをローカルの定義を提供します。 これらに変更を加えるスキーマを BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セットアップ ウィザードのコンピューターにインストールします。 他のこれらの変更済みスキーマを共有できます[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージの交換をインストールします。  
  
## <a name="types-of-z-objects"></a>Z オブジェクトの種類  
 HL7 標準 (2.X) は、現在、次の種類のカスタマイズをサポートします。  
  
-   **カスタムのトリガー イベントです。** ローカル エリアと新しいメッセージの構造では、必要時かは、標準でも含まれないトリガー イベントをサポートする場合は、Z プレフィックス、Z05 などを使用して新しいトリガー イベントを作成できます。 この場合は、抽象メッセージと含まれているセグメントのパターンを定義することで新しいローカルのメッセージ スキーマを作成する必要があります。  
  
-   **カスタムのセグメント。** 既にサポートされているトリガー イベントの追加のデータが必要なコンテキストでのローカル領域にある場合は、新しいセグメントまたはセグメントを作成し、セグメント内の必要なデータ要素が含まれます。 HL7 の既存のデータ型を使用して、セグメント内の要素を指定する必要があります。 Z セグメントのカスタム BizTalk エディターでは、スキーマに新しいレコードを作成して作成できます。 詳細については、[宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)を参照してください。 また、Access データベース、メッセージの構造をその Z セグメントを追加して Z セグメントを追加できます。 詳細については、[データベース エラーの解決](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)を参照してください。  
  
-   **カスタム データのサブタイプ。** HL7 など、サポートされているデータ型の一覧を提供するには、書式設定されたテキスト、イメージ、オーディオ データをスキャンします。 ただし、追加のデータ型を定義する場合、"Z"を使用するニーモニックを付けることで Z データを作成するための入力を実行できます。  
  
    > [!NOTE]
    >  許容される、新しいデータ型を作成するか、既存のセグメントの要素を追加する、標準の範囲内ではありません。 まだ小から大を指定できるは、現在使用されていない要素を取るをいくつか追加の目的を満たすように再定義することです。 その一方で、従来のインターフェイスをサポートする組織は、このようなプラクティスに対応する必要があります。  
  
-   **カスタム テーブル。** メッセージ内の多くの既存のオブジェクトでは、HL7 の一般的なスキーマで定義されているテーブルの列挙体で定義されている特定の値の制限の範囲があります。 Z テーブルを作成して追加の値を有効にするこれらの列挙体を変更することができます。  
  
## <a name="see-also"></a>参照  
 [未宣言のカスタマイズ](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)   
 [Z オブジェクト HL7 2.X スキーマの拡張](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)