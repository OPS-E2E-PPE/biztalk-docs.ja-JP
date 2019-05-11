---
title: Z オブジェクト HL7 2.X スキーマの拡張 |Microsoft Docs
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
ms.openlocfilehash: 514df3e1676e08d33be3a9fb00c61e47925b7b6d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267849"
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a>Z オブジェクト HL7 2.X スキーマの拡張
HL7 組織定義 HL7 2.X スキーマの場合を認識し、組織が定義したようにこれらのスキーマを使用して、すべての送信者と受信者が必要ですが、します。 相互運用性により、スキーマに準拠しています。 HL7 標準では、既存の HL7 をカスタマイズできるように、特定のローカル目的 2.X スキーマ。 まったく新しいスキーマおよびオブジェクトを定義することもできます。 そのためにはどのような HL7 標準呼び出し Z オブジェクト。  
  
 HL7 標準では、Z のオブジェクトの値は定義しません。 パブリッシュされた HL7 スキーマでは、それらは含まれません。 それらをローカルで定義をローカルのすべてのパーティとの契約によりそれらを使用します。 HL7 の組織では、すべてのメッセージの種類、トリガー イベント、セグメント、データ型、およびこのローカルで使用する"Z"で始まるテーブルの名前を予約します。 ため、プレフィックスは、HL7 標準は、これらのサイト定義オブジェクト Z オブジェクトを呼び出します。  
  
> [!NOTE]
>  Z オブジェクトを既存の HL7 定義スキーマに追加すると、そのスキーマの複数のバージョンと最終的する可能性があります。 これらの複数のバージョンを処理する最善の方法が Namespace 機能を使用して、[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]します。 この機能を見つけることができます、**検証**] タブの [ [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (パーティ レベル) でエクスプ ローラーを構成します。 また、そのプロジェクトを配置するスキーマ内で名前空間プロパティを変更する必要があります。  
  
 作成またはオブジェクトの処理 Z、Z オブジェクトの HL7 組織が設定される規則を従う必要があります.  
  
 既存のスキーマを Z オブジェクトを追加または新しい Z メッセージ スキーマを作成するときに[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]スキーマを Z オブジェクトと共に HL7 でエンコードされたメッセージの処理に使用します。 この種類の Z オブジェクトは、宣言された Z オブジェクトです。 メッセージ スキーマに従って統合エンジンは処理されませんの宣言されていない Z セグメントを使用することもできます。 この種類の Z セグメントの詳細については、次を参照してください。 [Z セグメントの宣言されていない処理](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [宣言された Z セグメントの作成](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [スキーマでのカスタム データ型の作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [スキーマでのカスタム テーブルの作成](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [列挙の拡張](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [Z オブジェクト経由のメッセージのカスタマイズ](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)