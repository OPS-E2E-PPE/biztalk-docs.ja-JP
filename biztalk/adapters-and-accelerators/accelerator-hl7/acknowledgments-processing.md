---
title: 受信確認処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb8bf0620c3e336317382cbeb299cf2d6d17faa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969467"
---
# <a name="acknowledgments-processing"></a>受信確認処理
HL7 仕様では、2 つの形式のメッセージの交換をサポートしています。  
  
- 要請されていない更新プログラムとその確認 (ACK)  
  
- クエリとその応答  
  
  発信側アプリケーションからのメッセージに対しては、応答側のアプリケーションは、データまたはエラーを示す値を含むメッセージを返します。 発信側アプリケーションを応答側のアプリケーションでしたメッセージが正しく表示されないことを示す応答側アプリケーションから拒否状態があります。 どちらの場合も、メッセージ交換のプロセスには、2 つのエンティティ、発信側と応答のアプリケーションが含まれます。 各は、送信者とメッセージの受信側の両方です。 発信側アプリケーションでは、最初に送信し、受信、応答してシステムの受信、送信中。  
  
## <a name="unsolicited-updates"></a>要請されていない更新プログラム  
 要請されていない更新プログラムでは、基幹業務 (LOB) のアプリケーションがメッセージを発行またはトリガー イベントが発生したときに、情報の転送を開始するときに発生します。 たとえば、患者の実験の結果が使用できる場合は、実験結果を他のいくつかのシステムに送信する必要があります。 これらの更新プログラムは、ACK が応答する要請されていない更新プログラムです。  
  
## <a name="queries"></a>クエリ  
 場合は、クエリ情報を必要とするアプリケーションでは、別のアプリケーションにクエリを送信し、受信側アプリケーションがクエリに応答します。 たとえば、薬局用アプリケーションは注文エントリ (組織) システムの患者の ID 番号を含む要求メッセージの送信し、注文の処理を許可するように、必要なデータを含む応答を受信可能性があります。 この要求を行ったトランザクションは、クエリであり、要請していない更新プログラムとは異なります。 2 つのアプリケーション間で行われる情報は、応答に含まれます。 応答自体では、4 番目のメッセージの受信確認は必要ありません。 ただし、ACK で応答する一部の環境で変更することができます。 Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) ように構成されている場合は、ACK で応答します。 クエリ/応答の交換の例は、次を参照してください。 [Interrogative チュートリアル](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [メッセージの検証](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [ACK メッセージ モード](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [ACK プロセス モデル](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)