---
title: "カスタマイズ設定の宣言 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- declared customizations
- Z objects, declared customizations
- customizing, Z objects
- customizing, declared customizations
ms.assetid: 484655e9-8bfa-4643-bbe6-4ef69cbd83ad
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 767fdd543b1cb5d87bf3ec1c1943ac81d91c6ea4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="declared-customizations"></a>宣言のカスタマイズ
宣言のカスタマイズでは、変更または HL7 メッセージへの追加の柔軟性があります。 新しいメッセージの種類でも定義できます。 これは、次のような方法で行います。  
  
-   新しいメッセージ型、またはトリガー イベントを定義することで、メッセージの定義を変更します。  
  
-   既存のメッセージ型への新しいセグメントの追加  
  
-   既存のメッセージ パーツ (セグメント、フィールド、コンポーネントまたはサブコンポーネント) のデータ型を変更します。  
  
-   既存のメッセージ部分で使用できる可能性のある値を変更します。  
  
    > [!NOTE]
    >  宣言されている Z オブジェクトまたは HL7 スキーマの標準的なオブジェクトで使用する列挙値を変更することができます。 これを行うには、次を参照してください。[列挙型の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)です。  
  
 変更、または追加する HL7 メッセージに追加すること、保守、および現在定義されているメッセージ型の中でカスタム オブジェクトを関連付けることです。 HL7 標準は「Z オブジェクト」これらのカスタム オブジェクトを呼び出す HL7 標準に準拠している既存のオブジェクトと区別するためです。 BizTalk エディターを使用して、Z のオブジェクトを定義します。 また、BizTalk エディターを使用するには、すべてのトリガー イベントの Z オブジェクトへの更新を伝達する機能とそれが含まれる抽象のメッセージを操作します。 Z オブジェクトの作成の詳細については、次を参照してください。 [Z オブジェクトで 2.X スキーマを拡張する HL7](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)です。  
  
 Z オブジェクトを使用すると、HL7 標準で指定されていない方法で使用するセグメントにローカルの定義を提供します。 これらを変更するスキーマを BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) セットアップ ウィザードが、コンピューターにインストールします。 他のこれらの変更済みスキーマを共有することができますし、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]メッセージを交換するインストールします。  
  
## <a name="types-of-z-objects"></a>Z オブジェクトの種類  
 HL7 標準 (2.X) には、現在のカスタマイズの次の形式がサポートしています。  
  
-   **カスタムのトリガー イベントです。** ローカルの領域と、新しいメッセージ構造を必要時か、標準ヘッダーに含まれないトリガー イベントをサポートするために必要な場合は、Z プレフィックス、Z05 などを使用して新しいトリガー イベントを作成できます。 ここでは、抽象メッセージと含まれているセグメントのパターンを定義することによって新しいローカルのメッセージ スキーマを作成する必要があります。  
  
-   **カスタムのセグメント。** 追加データは、必要な既にサポートされているトリガー イベントのコンテキストでのローカル領域がある場合は、新しいセグメントまたはセグメントを作成し、セグメント内の目的のデータ要素が含まれます。 HL7 の既存のデータ型を使用して、セグメント内の要素を指定する必要があります。 スキーマに新しいレコードを作成することでは、BizTalk エディターでカスタム Z セグメントを作成できます。 詳細については、次を参照してください。[宣言されている Z のセグメントを作成する](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)です。 また、Access データベース、メッセージの構造をその Z セグメントを追加して Z セグメントを追加できます。 詳細については、次を参照してください。[データベース エラーの解決](../../adapters-and-accelerators/accelerator-hl7/resolving-database-errors.md)です。  
  
-   **カスタム データのサブタイプ。** HL7 など、サポートされているデータ型の一覧を提供するには、書式付きテキスト、イメージ、オーディオ データをスキャンします。 ただし、追加のデータ型を定義する場合は、行うことができます、"Z"と共に使用ニーモニックをプレフィックスとして付けることは、それによって Z データを作成する入力します。  
  
    > [!NOTE]
    >  新しいデータ型を作成または既存のセグメントの要素を追加する、標準の境界内に、許容されることはできません。 まだ小さいは許容されるは、現在使用されていない要素を取得しをいくつか追加の目的を満たすように再定義することです。 その一方で、従来のインターフェイスをサポートする組織は、このようなプラクティスに対応する必要があります。  
  
-   **カスタム テーブル。** メッセージ内の多くの既存のオブジェクトでは、HL7 の一般的なスキーマで定義されているテーブルでの列挙で定義されている特定の値の範囲が制限されているがあります。 Z テーブルを作成することで追加の値を有効にするこれらの列挙体を変更することができます。  
  
## <a name="see-also"></a>参照  
 [宣言されていないカスタマイズ](../../adapters-and-accelerators/accelerator-hl7/undeclared-customizations.md)   
 [Z オブジェクトと HL7 2.X スキーマを拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)