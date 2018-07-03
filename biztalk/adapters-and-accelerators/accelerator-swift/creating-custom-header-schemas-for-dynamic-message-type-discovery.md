---
title: 動的メッセージ型の探索用のカスタム ヘッダー スキーマの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, dynamic resolution
- schemas, message types
- schemas, custom headers
- header schemas
ms.assetid: 0c936c57-b533-47ca-9258-576b021fd016
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf73b5cf02d6fa25fdea1347e56573ff023d934a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009123"
---
# <a name="creating-custom-header-schemas-for-dynamic-message-type-discovery"></a>動的メッセージ型の探索用のカスタム ヘッダー スキーマの作成
ほとんどのシナリオでは、SWIFT 逆アセンブラーの SWIFT ヘッダー スキーマ構成プロパティの既定のヘッダーを SWIFT スキーマ (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) を指定してください。 SWIFT 逆アセンブラーでは、既定の SWIFT ヘッダー スキーマを使用して、SWIFT の標準仕様に準拠しているメッセージ ヘッダーを解析しが必要な昇格プロパティを動的スキーマの解決 (と「デュアル型」のサブ型解決を容易にSWIFT メッセージなどの MT574_IRSLST MT574_W8BENO)。 SWIFT 逆アセンブラーがスキーマの解決を実行する方法を理解して既定のヘッダーを SWIFT スキーマについての詳細については、次を参照してください。[動的メッセージ型の探索とスキーマの解決](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)します。  
  
 その他のシナリオでのメッセージには、SWIFT 非標準ヘッダー データが含まれます。 ヘッダーの解析および動的メッセージ型の探索、カスタム ヘッダー スキーマを使用できます。 作成して、動的スキーマの解決のためのカスタム ヘッダー スキーマを使用するには、次の操作を行います。  
  
1. SWIFT 逆アセンブラーは、構造的に予想されるヘッダーのデータ形式を解析に使用できるカスタム スキーマを作成します。  
  
2. メッセージの種類を示す値を保持するは、スキーマ内のフィールドを識別します。  
  
3. A4SWIFT プロパティ スキーマ (Microsoft.Solutions.A4SWIFT.Property.PropertySchema)、プロパティ スキーマの「リスト」カスタム ヘッダー スキーマを追加し、次を使用してメッセージの種類を示す適切なフィールドを昇格[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]プロパティ。  
  
   -   **A4SWIFT_MessageType**  
  
   -   **A4SWIFT_MessageType2** (省略可能な場合**A4SWIFT_MessageTypes**使用)  
  
   -   **A4SWIFT_SecondaryMessageType** (省略可能)  
  
4. 構築し、カスタム ヘッダー スキーマを展開します。  
  
5. カスタム ヘッダーのスキーマに (受信パイプライン プロジェクト) で SWIFT 逆アセンブラーの SWIFT ヘッダー スキーマ構成プロパティを設定します。  
  
   これらおよびその他の昇格させたプロパティの詳細については、次を参照してください。 [a4swift _ * 昇格プロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)します。 BizTalk エディターを作成、スキーマを編集して、プロパティ スキーマを使用してプロパティを昇格し、ビルド、およびスキーマ プロジェクトの配置の使用に関する詳細については、BizTalk Server のヘルプを参照してください。  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラーおよびアセンブラーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)