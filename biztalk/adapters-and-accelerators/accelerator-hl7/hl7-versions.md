---
title: HL7 バージョン |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HL7, standards
- HL7, versions
ms.assetid: 47299c6f-55c3-4434-8170-5ad73fe9a84c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bc04fb6656a3e01c876afd94b76643bf39be3d5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292953"
---
# <a name="hl7-versions"></a>HL7 のバージョン
HL7 バージョン 2 は、1 つの標準ではなく、密接に関連する標準のファミリです。 HL7 の組織が、これらの標準 HL7 のバージョン間の互換性規則の適用を上方に対応するように設計されています。 これらの規則は、バージョン 2 の範囲内で HL7 のバージョンの規則の下で定義されたインターフェイスはまだ機能の後継バージョンの定義内でを保証します。 受信側のシステムはその実装と、送信を損なうことがなく、以降のバージョンからのメッセージを受信できるように、システムは引き続き以降のバージョンをサポートしている受信者にメッセージを送信することになります。  
  
 これは注意して、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)])。  
  
- バージョン 2.5 をバージョン 2.1 からすべてのライブ HL7 バージョンをサポートしています  
  
- HL7 のバージョン間でマップするために必要な機能を提供し、1 つのサイトに複数のバージョンの相互運用が可能  
  
- Z セグメントをサポートすることによりローカライズをサポートしている代替の解釈の間のマッピングを有効または標準のメッセージの使用  
  
  メッセージングの標準のバージョンの違いに注意する必要があります。  
  
- バージョン 1 は、概念実証としても機能していません。  
  
- バージョン 2 は、アプリケーション間のメッセージ交換をサポートするためにメッセージの仕様のコレクションを提供します。  
  
- バージョン 3 は、モデル ベースの統合された一連のさまざまな相互運用性のニーズをサポートする仕様  
  
  基本的には、バージョン 2 は、バージョン 3 は、一貫性ととして実行されるメッセージの仕様の本文の長期的な拡張性を確保することに重点を置いています中に指定されたタスクを実行するために必要な仕様をユーザーに提供する実用的な手法で焦点を当てます、。整数。  
  
  臨床のドキュメント アーキテクチャでは、XML を使用して医療のドキュメントの表現の標準を導入することで、HL7 標準に大幅な拡張機能を提供します。  
  
  次の表では、HL7 標準的な開発の進行状況を示します。  
  
|イベント|年|詳細|  
|-----------|----------|-------------|  
|HL7 設立|1987|最初のミーティング スタンフォード、CA では、12 の参加者を含まれています。|  
|V1.0|1987|下書きが HL7 plenary ミーティングに提示します。|  
|V2.0|1988|下書きが HL7 plenary ミーティングに提示します。|  
|発行バージョン 2.1 以降|1990|最初のバージョンを広く実装します。|  
|発行バージョン 2.2|1994||  
|V.2.3 の発行|1997|ANSI の承認|  
|V2.3.1 の発行|1999|ANSI の承認|  
|V2.4 の発行|2000|ANSI の承認|  
|電子カルテ アーキテクチャ|2000|ANSI の承認|  
|発行 V2.5|2003|承認のために、ANSI に送信された HL7 以内に承認を完了します。|  
|進行中の V3.0|2003||  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [HL7 2.X スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [HL7 2. XML スキーマの使用](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/message-modes.md)   
 [HL7 メッセージング](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)