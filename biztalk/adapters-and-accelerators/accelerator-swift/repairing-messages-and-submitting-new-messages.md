---
title: "メッセージの修復し、新しいメッセージを送信する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59ece524ce06430492a3927c0cd1437eef4b216d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="repairing-messages-and-submitting-new-messages"></a>メッセージの修復し、新しいメッセージを送信します。
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Message Repair and New Submission を使用すると、XML またはビジネス ルール エンジンの検証に失敗したメッセージを修復できます。 修復処理には、精度とメッセージの修復の妥当性を確保するための検証と承認の手順が含まれます。 使用して、このプロセスが実行される[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsOfficeNoVersion](../../includes/btsofficenoversion-md.md)] [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] MRSR サイト内のフォームです。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]このプロセスを使用して、新しいメッセージを送信することもできます。 作成者が、メッセージを送信して、ワークフローは、修理会社の検証機能、およびメッセージの修復と同様に同じタスクを実行する承認者を含めることができます。  
  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]各タスクを実行する別のユーザーに割り当てることで、このプロセスのセキュリティを確保します。 適切な修復を割り当てるまたはことを確認するには、これらのユーザーの各ロールの承認を実行して、各ユーザーは、特定の証明書を使用してタスクを実行する必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]修復と送信されたメッセージの処理には、部門の使用をサポートしています。 各部門には、特定のメッセージ セットで実行されるタスクの特定のワークフローが含まれます。 作成のいずれか、修復、ことを確認する、または、メッセージを送信するときに、手順についてを承認[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]BRE 検証を呼び出すし、ユーザーが適切な部門のメンバーであることを確認します。 メッセージの修復と新しい送信の詳細については、次を参照してください。[メッセージ修復 and New Submission](../../adapters-and-accelerators/accelerator-swift/message-repair-and-new-submission.md)です。  
  
 メッセージが表示される未解析、Message Repair および New Submission メッセージとエラーの説明を表示する場合、[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]が形成され、メッセージを印刷またはファイルに保存することができます。 修復し、メッセージを再送信します。 ただし、 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] BRE 検証を呼び出すまたは修復する未解析のメッセージを送信するときに、部署内のメンバーシップを確認しません。 さらに、未解析の再送信されたメッセージまたはされていないことを確認を承認します。 未解析のメッセージの詳細については、次を参照してください。[未解析のメッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md)です。  
  
 このセクションには、次のトピックが含まれています。  
  
-   [メッセージの修復](../../adapters-and-accelerators/accelerator-swift/repairing-a-message.md)  
  
-   [メッセージの検証](../../adapters-and-accelerators/accelerator-swift/verifying-a-message.md)  
  
-   [メッセージを承認します。](../../adapters-and-accelerators/accelerator-swift/approving-a-message.md)  
  
-   [未解析のメッセージの処理](../../adapters-and-accelerators/accelerator-swift/handling-an-unparsed-message.md)  
  
-   [作成して、新しいメッセージを送信します。](../../adapters-and-accelerators/accelerator-swift/creating-and-submitting-a-new-message.md)  
  
-   [新しいメッセージ テンプレートの作成](../../adapters-and-accelerators/accelerator-swift/creating-a-new-message-template.md)