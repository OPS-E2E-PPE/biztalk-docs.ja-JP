---
title: Z オブジェクトと HL7 2.X スキーマを拡張 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, Z objects
- Z objects, extending 2.X schemas
ms.assetid: 0980d919-eb81-4c65-b0f7-f17f7cfef6b3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27ef2bea3e13904f04449a5b77d05672c2b2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204658"
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a>Z オブジェクトと HL7 2.X スキーマを拡張します。
HL7 組織定義 HL7 2.X スキーマを認識し、組織を定義すると、これらのスキーマを使用して、すべての送信者と受信者を想定します。 相互運用性により、スキーマに準拠しています。 HL7 標準では、既存の HL7 をカスタマイズすることできます、特定のローカルの目的の 2.X スキーマです。 まったく新しいスキーマとオブジェクトを定義することもできます。 ためにはどのような HL7 標準呼び出し Z オブジェクト。  
  
 標準 HL7 では、Z のオブジェクトの値は定義しません。 パブリッシュされた HL7 スキーマでは、それらは含まれません。 それらをローカルに定義し、ローカルのすべてのパーティとの契約して使用します。 HL7 組織では、すべてのメッセージの種類、イベントのトリガー、セグメント、データ型、およびこのローカルに使用する"Z"で始まるテーブル名を予約します。 により、そのプレフィックスは、HL7 標準は、これらのサイト定義オブジェクト Z オブジェクトを呼び出します。  
  
> [!NOTE]
>  既存の HL7 定義スキーマに Z オブジェクトを追加するときになる場合がありますそのスキーマの複数のバージョン。 これらの複数バージョンを処理する最善の方法は Namespace 機能を使用する[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]です。 この機能を見つけることができます、**検証**] タブの [ [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (パーティ レベルでエクスプ ローラーを構成します。 そのプロジェクトを配置するスキーマ内で名前空間プロパティを変更する必要があります。  
  
 作成または処理 Z オブジェクトでは、Z オブジェクト用 HL7 組織に設定が規則に従う必要があります.  
  
 既存のスキーマに Z オブジェクトを追加または新しい Z メッセージ スキーマを作成するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]Z オブジェクトと HL7 でエンコードされたメッセージを処理するスキーマを使用します。 この種類の Z オブジェクトは、宣言されている Z オブジェクトです。 メッセージ スキーマに従って統合エンジンは処理されませんの宣言されていない Z セグメントを使用することもできます。 この種類の Z セグメントに関する詳細については、次を参照してください。[宣言されていない Z セグメントの処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)です。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [宣言されている Z セグメントを作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [スキーマでカスタム データ型を作成します。](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [スキーマのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [列挙型を拡張します。](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [Z オブジェクト経由でメッセージをカスタマイズします。](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)