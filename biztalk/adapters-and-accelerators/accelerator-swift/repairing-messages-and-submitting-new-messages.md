---
title: メッセージの修復と新しいメッセージの送信 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages
- Message Repair and New Submission
- submitting, messages
- submitting, Message Repair and New Submission
- messages, Message Repair and New Submission
- messages, submitting
- Message Repair and New Submission. about Message Repair and New Submission
ms.assetid: 6abcce90-f611-422a-b3c8-e25f1e75b039
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569d1da0e402d088f9b220f0d7645202dd83f832
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530213"
---
# <a name="repairing-messages-and-submitting-new-messages"></a>メッセージの修復と新しいメッセージの送信
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] Message Repair and New Submission を使用すると、XML またはビジネス ルール エンジンの検証が失敗したメッセージを修復できます。 修復処理には、精度とメッセージの修復の妥当性を保証する検証と承認の手順が含まれます。 このプロセスは Microsoft を使用して実行[!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR サイト内のフォームです。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] このプロセスを使用して新しいメッセージを送信することもできます。 作成者は、メッセージを送信して、ワークフローは、修理会社、検証機能をおよびメッセージ修復のように同じタスクを実行する承認者を含めることができます。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 各タスクを実行する別のユーザーを割り当てることで、このプロセスのセキュリティを確保します。 適切な修復を割り当てるかを確認するには、これらのユーザーの各ロールの承認を実行して、各ユーザーは、特定の証明書を使用してタスクを実行する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 修復と送信されたメッセージの処理には、部門の使用をサポートしています。 各部門には、特定のメッセージ セットで実行するタスクの特定のワークフローが含まれます。 作成のような修復、検証、または、メッセージを送信するときに、手順を承認[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BRE 検証を呼び出すし、ユーザーが適切な部門のメンバーであることを確認します。 メッセージの修復と新しい送信の詳細については、次を参照してください。[メッセージ修復 and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)します。  
  
 Message Repair、未解析メッセージの受信および New Submission は、メッセージとエラーの説明が表示されます。 場合、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]が形成され、メッセージを印刷したり、ファイルに保存することができます。 修復し、メッセージを再送信します。 ただし、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] BRE 検証を呼び出すまたは修復が未解析メッセージを送信するときに、部署内のメンバシップを確認しません。 さらに、未解析の再送信されたメッセージが検証されません、または承認は。 未解析メッセージの詳細については、次を参照してください。[未解析メッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)します。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [メッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [メッセージの検証](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [メッセージの承認](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [未解析メッセージの処理](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [新しいメッセージの作成と送信](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [新しいメッセージ テンプレートの作成](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)