---
title: "HL7 バージョン |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HL7, standards
- HL7, versions
ms.assetid: 47299c6f-55c3-4434-8170-5ad73fe9a84c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c7edcfa6c44467c0660efd8a9b4b02df7010de6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="hl7-versions"></a>HL7 のバージョン
HL7 バージョン 2 は、1 つの標準ではなく、密接に関連する標準のファミリです。 HL7 組織には、これらの標準 HL7 間のバージョンの互換性規則のアプリケーションを介して下方互換性があること、設計しました。 これらの規則はの境界内にバージョン 2、HL7 のバージョンの規則の下で定義されたインターフェイスがまだ機能する後続のバージョンの定義内を保証します。 受信側システムでは、実装と、送信を分断することがなく以降のバージョンからのメッセージを受信できるように、システムはできなければ以降のバージョンをサポートしている受信者にメッセージを送信し続けます。  
  
 重要な点は[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
-   バージョン 2.5 をバージョン 2.1 からすべてのライブ HL7 バージョンをサポートしています  
  
-   HL7 バージョン間でマップするために必要な機能を提供し、1 つのサイトに複数のバージョンの相互運用が可能  
  
-   Z セグメントをサポートすることでローカライズをサポートしていると、代替の意味との間のマッピングを有効または標準のメッセージの使用  
  
 ことが重要メッセージングの標準のバージョンの違いに注意してください。  
  
-   バージョン 1 は、概念実証としても機能していません。  
  
-   バージョン 2 のアプリケーション間のメッセージ交換をサポートするためにメッセージ仕様のコレクションを提供します。  
  
-   バージョン 3 はさまざまな相互運用性のニーズをサポートする仕様のモデル ベースの統合セットを提供します。  
  
 基本的には、バージョン 2 について重点的に一貫性ととしてのメッセージ仕様の本文の長期的な機能拡張を確保することに重点を置いています Version 3 中に指定したタスクは、実行するために必要な仕様をユーザーに提供する実際的なアプローチを整数。  
  
 医療のドキュメント アーキテクチャでは、標準 XML を使用して治療のドキュメントの形式を導入することにより、HL7 標準に大幅な拡張機能を提供します。  
  
 次の表は、HL7 標準的な開発の流れを示します。  
  
|イベント|年|詳細|  
|-----------|----------|-------------|  
|HL7 設立されました|1987|最初のミーティング スタンフォード、CA では、12 参加者を含まれています。|  
|V1.0|1987|下書き HL7 plenary ミーティングに提示します。|  
|バージョン 2.0|1988|下書き HL7 plenary ミーティングに提示します。|  
|公開されたバージョン 2.1 以降|1990|最初にバージョン広く実装されています。|  
|公開されたバージョン 2.2|1994||  
|パブリッシュされた V.2.3|1997|ANSI の承認|  
|パブリッシュされた V2.3.1|1999|ANSI の承認|  
|パブリッシュされた V2.4|2000|ANSI の承認|  
|ドキュメントのアーキテクチャ|2000|ANSI の承認|  
|パブリッシュされた V2.5|2003|HL7、承認のための ANSI に送信内での承認を完了します。|  
|進行中の V3.0|2003||  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/message-modes.md)   
 [HL7 メッセージ](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)