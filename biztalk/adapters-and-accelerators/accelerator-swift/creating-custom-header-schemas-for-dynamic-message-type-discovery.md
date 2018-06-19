---
title: 動的なメッセージの種類の探索用のカスタム ヘッダーのスキーマの作成 |Microsoft ドキュメント
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
ms.openlocfilehash: c87ba83961b9daac07028a994d7c01add0c11a73
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004331"
---
# <a name="creating-custom-header-schemas-for-dynamic-message-type-discovery"></a>動的なメッセージの種類の探索用のカスタム ヘッダーのスキーマの作成
ほとんどのシナリオでは、SWIFT、逆アセンブラーの SWIFT ヘッダー スキーマ構成プロパティの既定の SWIFT ヘッダー スキーマ (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) を指定してください。 SWIFT の逆アセンブラーでは、既定の SWIFT ヘッダー スキーマを使用して、SWIFT の標準仕様に準拠しているメッセージ ヘッダーを解析しが、必要な昇格されたプロパティを動的スキーマの解決 (と「デュアル型」のサブ型解決を容易にします。SWIFT メッセージなど、MT574_IRSLST MT574_W8BENO)。 既定の SWIFT ヘッダー スキーマおよび SWIFT の逆アセンブラーがスキーマの解決を実行する方法を理解する詳細については、次を参照してください。[動的メッセージ型の検出とスキーマの解決](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)です。  
  
 メッセージに SWIFT 非標準ヘッダー データが含まれているその他のシナリオのヘッダーの解析および動的なメッセージの種類の探索カスタム ヘッダー スキーマを使用することができます。 作成し、動的スキーマの解決のカスタム ヘッダー スキーマを使用するには、次の操作を行います。  
  
1.  SWIFT の逆アセンブラーが構造的にデータの形式が求められるヘッダーの解析に使用できるカスタム スキーマを作成します。  
  
2.  メッセージの種類を示す値を保持するスキーマのどのフィールドを識別します。  
  
3.  "プロパティ スキーマの一覧に"カスタム ヘッダー スキーマ A4SWIFT プロパティ スキーマ (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) を追加し、次を使用してメッセージの種類を示す適切なフィールドを昇格[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]プロパティ。  
  
    -   **A4SWIFT_MessageType**  
  
    -   **A4SWIFT_MessageType2** (省略可能な場合**A4SWIFT_MessageTypes**を使用)  
  
    -   **A4SWIFT_SecondaryMessageType** (省略可能)  
  
4.  構築し、カスタム ヘッダー スキーマを展開します。  
  
5.  カスタム ヘッダーのスキーマに SWIFT の逆アセンブラー (の受信パイプライン プロジェクト) の SWIFT ヘッダー スキーマ構成プロパティを設定します。  
  
 これらおよびその他の昇格させたプロパティの詳細については、次を参照してください。 [A4SWIFT_ * 昇格されたプロパティ](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)です。 BizTalk エディターを使用して作成およびスキーマを編集、プロパティ スキーマを使用してプロパティを昇格させるとビルドおよびスキーマ プロジェクトを配置する方法の詳細については、BizTalk Server ヘルプを参照してください。  
  
## <a name="see-also"></a>参照  
 [SWIFT 逆アセンブラーおよびアセンブラーの操作](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)